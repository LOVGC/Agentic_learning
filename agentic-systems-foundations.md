# 🤖 How to Build an AI Agentic System — Foundations

> Background research for designing our own **agentic learning system** (see [[knowledge-map]] for the learning theory this will serve).
> This note is **general**: it captures how agentic systems are built in 2026, their components and patterns — *not* yet our specific design. The design comes next.

**TL;DR.** An "agent" is, at its core, a loop: a language model that **reasons**, **chooses tools/actions**, **observes the result**, **updates its memory**, and repeats until a goal is met. Everything else — planning strategies, memory types, multi-agent orchestration, guardrails — is structure layered on top of that loop. The dominant engineering lesson from the people who build these for a living: **start as simple as possible, add structure only when it measurably helps.**

---

## 1. The first decision: workflow vs. agent

Anthropic draws the cleanest line in the field ([Building Effective Agents](https://www.anthropic.com/research/building-effective-agents)):

- **Workflow** — LLMs and tools orchestrated through **predefined code paths**. *You* decide the control flow; the model fills in steps. Predictable, cheap, testable.
- **Agent** — the LLM **dynamically directs its own process and tool use**, deciding what to do next based on what it observes. Flexible, handles open-ended problems, but less predictable and more expensive.

This is a **spectrum**, not a binary. Most production "agentic systems" are mostly workflow with a few genuinely agentic steps. The guiding principle:

> Use the **most constrained** design that solves the problem. Reach for full autonomy only when the steps genuinely can't be hardcoded.

---

## 2. The foundational building block: the *augmented LLM*

Before any multi-step behavior, you need one well-equipped model call. The **augmented LLM** = a model enhanced with three capabilities it actively controls:

| Augmentation | What it does | The model decides… |
|---|---|---|
| **Retrieval** | Pull in external knowledge | what to search for |
| **Tools** | Act on the world (code, APIs, files) | which tool, with what arguments |
| **Memory** | Persist information | what to retain and recall |

If a single augmented LLM call solves the task, **you are done — don't build an agent.** This is the unit you compose everything else from.

---

## 3. The agent loop (the heart of it)

Every agentic system, under the hood, runs some version of this cycle:

```
        ┌──────────────────────────────────────────────┐
        │                                              │
        ▼                                              │
   ┌─────────┐   ┌──────────┐   ┌────────┐   ┌─────────────┐
   │ PERCEIVE│──▶│  REASON  │──▶│  PLAN  │──▶│   ACT       │
   │ (input/ │   │ (LLM     │   │ (pick  │   │ (call tool) │
   │  state) │   │  thinks) │   │  next) │   └──────┬──────┘
   └─────────┘   └──────────┘   └────────┘          │
        ▲                                            ▼
        │         ┌──────────────┐          ┌──────────────┐
        └─────────│ UPDATE MEMORY│◀─────────│   OBSERVE    │
                  └──────────────┘          │ (tool result │
                                            │  = feedback) │
                                            └──────────────┘
   Loop until: goal met · stop condition · or must ask a human.
```

The "agent" property doesn't come from the model alone — it **emerges from the infrastructure** that gives the model tools, memory, and the ability to run this observe-act loop and **gain ground truth from the environment at each step** ([Anthropic](https://www.anthropic.com/research/building-effective-agents); [cogitx overview](https://cogitx.ai/blog/ai-agents-complete-overview-2026)).

> 📌 Note for later: this loop is *structurally identical* to the agent⇄environment learning loop in [[what_is_learning]]. The agentic system we build will itself be an agent — and the **learner is its environment.**

---

## 4. The basic components (the anatomy)

Practitioners converge on roughly these building blocks ([orq.ai](https://orq.ai/blog/ai-agent-architecture), [redis](https://redis.io/blog/ai-agent-architecture/), [todaynews guide](https://todaynews.co.uk/2026/05/08/ai-agent-architecture-llm-core-memory-tools-and-planner-in-one-guide/)):

### a. Model / reasoning core
The LLM that interprets state and decides. Choose for capability vs. latency/cost; you can **route** easy steps to cheap models and hard steps to strong ones. Default to the most capable model for the reasoning-heavy parts.

### b. Instructions / policy
The system prompt that defines the agent's role, goals, constraints, and *how* to use its tools. This is where most behavior is actually shaped — far more than people expect.

### c. Planning & control
How the agent sequences actions. Main strategies:
- **ReAct** (Reason + Act): interleave a thought and an action each step. Best for dynamic, unpredictable tasks.
- **Plan-and-Execute**: write the whole plan up front, then execute. Better for predictable workflows; cheaper, more inspectable.
- **Reflection / self-critique**: the agent evaluates its own output and revises (see *evaluator-optimizer* below).
- Choice depends on your constraints around **latency, cost, and reliability** ([cogitx](https://cogitx.ai/blog/ai-agents-complete-overview-2026)).

### d. Tools / actions — the *Agent-Computer Interface (ACI)*
Tools are how the agent affects the world (run code, call APIs, read/write files, search). Anthropic argues you should invest in tool design as much as you'd invest in a human UI:
- **Pick formats that are natural** for the model to produce (minimal "overhead thinking").
- **Document thoroughly**: example usage, edge cases, clear boundaries between tools.
- **Poka-yoke** (mistake-proof) the arguments — e.g. require absolute file paths so the model can't get relative paths wrong.
- **Test on many inputs** and iterate on the model's actual mistakes.
- The open standard for connecting tools/data to agents today is **MCP (Model Context Protocol)**.

### e. Memory
Treated in 2026 as a **dedicated architectural component, separate from the context window** — not just "a longer prompt" ([mem0 state of memory](https://mem0.ai/blog/state-of-ai-agent-memory-2026), [MongoDB](https://www.mongodb.com/resources/basics/artificial-intelligence/agent-memory)):

| Memory                     | Horizon         | Holds                                          | Analogy                           |
| -------------------------- | --------------- | ---------------------------------------------- | --------------------------------- |
| **Working / short-term**   | this task       | conversation buffer, current state, scratchpad | what's in your head right now     |
| **Episodic** (long-term)   | across sessions | specific past experiences/events               | "last time I tried X, Y happened" |
| **Semantic** (long-term)   | across sessions | facts, concepts, relationships                 | textbook knowledge                |
| **Procedural** (long-term) | across sessions | learned skills/workflows run automatically     | riding a bike                     |

Long-term memory is usually backed by a **vector store** (Pinecone/Weaviate/Redis) for retrieval, while the context window manages short-term state. Long-term memory is what lets an agent **learn from outcomes and behave consistently over time** — which is exactly what a *learning* system needs.

### f. Orchestration
How many agents and how they relate (single agent, orchestrator + workers, peer agents). See §6.

### g. Environment & feedback
The source of **ground truth**. An agent without real feedback from its environment is just guessing. The tighter and more honest the feedback loop, the better the agent. (This echoes the "close the feedback loop" lesson in [[2026-06-02_how-to-start-feeling-new-knowledge]].)

### h. Guardrails & safety
Input/output validation, content screening, permission boundaries, sandboxing, human-in-the-loop checkpoints, and **stopping conditions** (max steps / budget) so loops can't run away.

### i. Evaluation & observability
You cannot improve what you can't see. Log every step (transparency), build evals against real tasks, and measure cost/latency/success. "Measure everything; add complexity only when it delivers measurable value."

---

## 5. The core design patterns

Five **workflow** patterns + the **autonomous agent**, from [Anthropic](https://www.anthropic.com/research/building-effective-agents) (each is just a few lines of code over the augmented-LLM block):

| Pattern | Shape | Use when |
|---|---|---|
| **Prompt chaining** | step → gate → step → step | task splits into fixed sequential subtasks; checkpoints improve accuracy |
| **Routing** | classify → send to specialist | distinct categories handled better separately (e.g. triage; cheap vs. expensive model) |
| **Parallelization** | fan-out → aggregate | independent subtasks (*sectioning*) or multiple tries for confidence (*voting*) |
| **Orchestrator–workers** | lead LLM decomposes → delegates → synthesizes | subtasks are **unpredictable** and input-dependent |
| **Evaluator–optimizer** | generate ↔ critique loop | clear eval criteria exist and iteration measurably improves output |
| **Autonomous agent** | open-ended observe-act loop | steps can't be hardcoded; needs sandboxing, guardrails, trust |

A real system usually **composes** these (e.g. route → orchestrator-workers → evaluator-optimizer on each piece).

---

## 6. Single-agent vs. multi-agent

The hype favors multi-agent; the evidence says **be selective**.

**When multi-agent wins:** problems that **decompose into independent sub-questions that don't share mutable state** — e.g. parallel research. Anthropic's multi-agent research system (lead Claude + parallel sub-agents) **outperformed a single-agent baseline by ~90%** on their internal research eval ([orchestration guide](https://atlan.com/know/multi-agent-system-orchestration/)).

**The costs and risks:**
- **Tokens:** agents use ~**4×** the tokens of a chat; multi-agent systems ~**15×** ([Anthropic, via search](https://www.augmentcode.com/guides/single-agent-vs-multi-agent-ai)).
- **Errors cascade** instead of cancelling on genuinely agentic tasks; coordination overhead grows with interaction depth ([single vs multi analysis](https://medium.com/@mjgmario/single-agent-vs-multi-agent-systems-when-coordination-helps-hurts-and-pays-off-57735ee7916d)).
- **Composition failure:** every agent can pass its own tests while the *system* fails ([Maxim on reliability](https://www.getmaxim.ai/articles/multi-agent-system-reliability-failure-patterns-root-causes-and-production-validation-strategies/)).
- Sometimes a 4% accuracy gain costs 4× the compute — not always worth it.

**Rule of thumb:** start single-agent. Split into multiple agents only when subtasks are genuinely parallel/independent, or need **isolated context** (separate "headspaces"), or distinct toolsets.

---

## 7. Context engineering (the discipline that's replacing "prompting")

As systems grow, the bottleneck shifts from *the prompt* to **what information is in the context window at each step**. Context engineering = deliberately curating that context: shared glossaries/definitions, retrieved memory, tool results, and state — as **infrastructure**, not ad-hoc strings ([context engineering](https://atlan.com/know/multi-agent-system-orchestration/)). Practically: keep context **relevant, compressed, and current**; give each agent only what it needs; make state explicit rather than buried in chat history.

---

## 8. The framework landscape (and a caution)

Common 2026 frameworks ([best frameworks 2026](https://gurusup.com/blog/best-multi-agent-frameworks-2026), [monday](https://monday.com/blog/ai-agents/ai-agent-frameworks/)):

- **LangGraph** — graph/state-machine control over agent flow; good for explicit, inspectable workflows.
- **CrewAI** — role-based teams of agents ("crew") with a coordinator.
- **AutoGen** (Microsoft) — conversational multi-agent.
- **OpenAI Agents SDK** / **Claude Agent SDK** — vendor-native agent loops, tool use, memory.
- **MCP** — not a framework but the connector standard for tools/data.

⚠️ **Anthropic's caution:** the best implementations often use **no heavy framework** — direct API calls with simple composable patterns. Frameworks add abstraction layers that hide what's really in the prompt and make debugging harder. Start with the raw loop; adopt a framework only when it earns its keep.

---

## 9. The engineering principles that matter most

From Anthropic and the broader field, in priority order:

1. **Simplicity first.** The right system, not the most sophisticated one. Single call → workflow → agent, in that order.
2. **Transparency.** Show the agent's plan and reasoning at every step; never a black box.
3. **Great tools (ACI).** Tool design is as important as model choice. Document, mistake-proof, and test them.
4. **Tight feedback / ground truth.** The agent must observe real consequences each step.
5. **Memory as architecture**, not as a longer prompt.
6. **Measure everything.** Evals + observability before complexity.
7. **Guardrails & stopping conditions** are not optional for autonomous loops.

---

## 10. Bridge → our agentic *learning* system

Mapping this onto the goal in [[knowledge-map]] (preview of the design step, not the design itself):

| General agent component            | In a learning system                                                                                                                                           |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Environment**                    | the **learner** (their current understanding, answers, mistakes)                                                                                               |
| **Goal**                           | move the learner from *information* to *felt knowledge* ([[2026-06-02_how-to-start-feeling-new-knowledge]])                                                    |
| **Reasoning core**                 | diagnose the learner's zone of proximal development                                                                                                            |
| **Tools**                          | source-finding, lesson/quiz generation, the "Feynman output test" as an examiner ([[2026-06-24_feynman-learning-stance]])                                      |
| **Memory**                         | learning records — episodic (what was tried), semantic (the field's map), procedural (skills practiced) — cf. `matt_teach_skill`                               |
| **Feedback loop**                  | output tests & minimum-viable-practice that reveal real gaps                                                                                                   |
| **The learner's own "two models"** | the system's job is to grow the learner's *mental model* (model ②) by exercising their *learning ability* (model ①) — exactly the loop in [[what_is_learning]] |

The existing `matt_teach_skill` is essentially a **workflow-style** learning agent (stateful files: mission, resources, learning-records, lessons). Our design question becomes: *which parts should stay structured workflow, and which should become genuinely agentic?*

---

## Sources
- Anthropic — [Building Effective Agents](https://www.anthropic.com/research/building-effective-agents) · [Writing tools for agents](https://www.anthropic.com/engineering/writing-tools-for-agents)
- [AI Agents: Complete Overview (2026) — cogitx](https://cogitx.ai/blog/ai-agents-complete-overview-2026)
- [AI Agent Architecture — orq.ai](https://orq.ai/blog/ai-agent-architecture) · [Redis](https://redis.io/blog/ai-agent-architecture/) · [LLM core/memory/tools/planner guide](https://todaynews.co.uk/2026/05/08/ai-agent-architecture-llm-core-memory-tools-and-planner-in-one-guide/)
- Memory: [State of AI Agent Memory 2026 — mem0](https://mem0.ai/blog/state-of-ai-agent-memory-2026) · [MongoDB agent memory](https://www.mongodb.com/resources/basics/artificial-intelligence/agent-memory) · [3 types of long-term memory — MLM](https://machinelearningmastery.com/beyond-short-term-memory-the-3-types-of-long-term-memory-ai-agents-need/)
- Orchestration & reliability: [Multi-agent orchestration — atlan](https://atlan.com/know/multi-agent-system-orchestration/) · [Single vs multi-agent — Augment](https://www.augmentcode.com/guides/single-agent-vs-multi-agent-ai) · [Reliability failure patterns — Maxim](https://www.getmaxim.ai/articles/multi-agent-system-reliability-failure-patterns-root-causes-and-production-validation-strategies/)
- Frameworks: [Best multi-agent frameworks 2026 — gurusup](https://gurusup.com/blog/best-multi-agent-frameworks-2026) · [Frameworks for teams — monday](https://monday.com/blog/ai-agents/ai-agent-frameworks/)
