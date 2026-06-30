# 🗺️ Basic Learning Principles — Knowledge Map

> A wiki / Map-of-Content (MOC) for everything in this folder.
> These notes are the **first-principles foundation** for building an *agentic learning system* — a system that helps a learner learn new things.
> Each entry below has a one-paragraph summary, key ideas, and a relative markdown link to the file.

**The one-sentence thesis that ties everything together:**
Learning is a finite-resource **agent** continuously updating its **internal world model** from **experience**, extracting generalizable patterns to **predict** better and therefore **act** better. Everything else in this folder is either *what that means* (theory), *how to stand toward it* (mindset), or *how to actually do it* (method).

---

## How the pieces fit

```
            ┌─────────────────────────────────────────────┐
            │   I. THEORY — what learning fundamentally is │
            │   what_is_learning_GPT · what_is_learning    │
            │   (agent ⇄ env, two models, prediction)      │
            └───────────────────┬─────────────────────────┘
                                │ defines the target:
                                │ a better internal "mental model"
                ┌───────────────┴───────────────┐
                ▼                                ▼
   ┌─────────────────────────┐     ┌────────────────────────────┐
   │  II. MINDSET — the       │     │  III. METHOD — how to build │
   │  stance toward unknowing │     │  the model in practice       │
   │  feynman-learning-stance │◄───►│  how-to-start-feeling-...    │
   │  (sensory model, play)   │     │  (map first, output test)    │
   └─────────────────────────┘     └────────────────────────────┘
            shared bridge: the "Feynman output test" + "mental model" + "feel / intuition"
```

- **Theory** says the *goal* of learning is an accurate, compressed internal model that predicts the environment.
- **Mindset** says that model only becomes real understanding when it is built from **sensory simulation** and approached with **playful honesty** about not-knowing.
- **Method** gives the **concrete workflow** for building that model: map first, choose a learning route, and close the loop with output tests.

The concept **"mental model"** is the spine running through all three — see [Through-lines](#through-lines--shared-concepts) below.

---

## I. Theoretical Frameworks
*First principles: what learning fundamentally* is.

### 📐 What Is Learning — first-principles derivation
- **File:** [what_is_learning_GPT](what_is_learning_GPT.md) · *(markdown, step-by-step reasoning, bilingual)*
- **Summary:** A ten-step deduction that strips away every educational / psychological / neuroscience definition of "learning" until only the irreducible core remains. Starting from a universe with a single agent facing an environment, it argues: learning must mean *the past changes future behavior*; it exists because **evolution is too slow** for a changing world; what it actually updates is not memory but an **internal world model**; its real product is **better prediction**, which serves **better action and survival**; and achieving this requires **compression / abstraction / generalization** — finding the minimum description of experience — which is only possible because the world has predictable structure. It converges on the same place as the Free Energy Principle, information theory, dynamic programming, and modern RL: **continually reducing future uncertainty (prediction error / surprise).**
- **Key ideas:**
  - Learning = *past experience changes future behavior* (no change → not learning).
  - Learning is **evolution's fast, in-lifetime, local version**.
  - It updates the **internal world model**, not a memory store.
  - **Prediction serves decision serves survival** — prediction is never the end goal.
  - **Compression = generalization**: from finite samples infer the infinite (10,000 cats → the concept "cat").
  - Pattern-finding only works because **the world is not random**.
- **The first-principles definition it lands on:**
  > *Learning is the process by which a finite-resource agent continuously updates its internal world model through experience, extracts generalizable patterns from environmental data to improve its prediction of the future, and thereby makes better decisions and adapts better.*
- **Open question it leaves:** If learning is building/correcting a world model, what is the relationship between **understanding** and **learning** — is understanding a *state* and learning a *process*, or is understanding itself a special form of learning?

### 🖼️ What Is Learning — the one-page diagram + author's insights
- **File:** [what_is_learning.html](what_is_learning.html) · *(self-contained HTML; an illustrated "first-principles" poster — open in a browser)*
- **Summary:** The visual companion to [what_is_learning_GPT](what_is_learning_GPT.md). It renders the same definition as a single RL-style diagram (FIG. 1): an **Agent ⇄ Environment** loop where the agent emits `action a` and the environment returns `(state s′, reward r)`. Crucially it places **two models inside the agent**: ① a **compression / abstraction** model (the *learner* — eats experience, outputs a model) and ② a **mental model** (the *learned thing* — takes `(state, action)`, predicts `(next state, reward)`, i.e. an internal mirror of the environment). The author then adds four personal reflections that reframe the whole picture.
- **Key ideas (the author's four reflections):**
  1. **The same loop runs at every scale** — a person, a nation, a single day, a whole lifetime, all of human evolution.
  2. **"Mental model" really means the *capacity to learn*** — it maps to model ① (compression/abstraction), and `mental model = compressed knowledge = abstractions = basic framework`. So to learn a field, **first find its Basics** — one framework of which almost everything else is just an implementation or adaptation.
  3. **An *already-built* mental model (②) = accumulated experience = the comfort zone.** Therefore: **learning = using ① (the ability to learn) to keep pushing ② (the comfort zone) outward.**
  4. **Learning has many layers** — at bottom a survival mechanism of life; at another, simply fun — but it is always *the same diagram*, only described in different words.
- **Closing line:** *"When you forget how to learn, come back to this diagram."*
- **Relation:** This is the **synthesis / mental-model** of the theory; [what_is_learning_GPT](what_is_learning_GPT.md) is its **derivation**.

---

## II. Mindset & Stance
*Not what to do, but how to* be *in front of the unknown.*

### 🧠 The Feynman Learning Stance
- **File:** [2026-06-24_feynman-learning-stance](2026-06-24_feynman-learning-stance.md) · *(distilled note)*
- **Summary:** A synthesis of Richard Feynman's view of how real thinking and learning work, organized around three interdependent themes. **(1) Names are not knowing** — Feynman's father naming a bird in four languages: you now know the labels but still know *nothing about the bird*; most "education" is learning labels, not what is actually happening. **(2) Sensory mental models** — always translate the abstract into something you can see, touch, or imagine (atoms colliding; being the size of an electron feeling charges); language is discrete, low-bandwidth, forgettable, but a sensory model runs as a continuous internal *simulator* — once you can run the simulation, you understand it and never forget it. **(3) The emotional stance toward not-knowing** — three deepening postures: **defense** (nodding/faking from shame, which stops all learning), **honest admission** ("I don't understand yet," the gateway), and **playful curiosity** (delighting in the unknown — the wobbling-plate story that idle play eventually fed his Nobel work).
- **Key ideas:**
  - Knowing the **name** of something ≠ knowing it; labels create an *illusion* of understanding.
  - **You cannot think clearly about what you cannot visualize** — build a sensory model that acts as an internal simulator.
  - Ask **"why" repeatedly, like a child**, until you reach the foundation.
  - **The smartest move is to admit you don't understand** — that is where thinking *begins*.
  - **The Feynman test:** if you can't explain it to a freshman / a child / a layperson, you don't yet understand it (and that's okay).
  - **Enjoy not-knowing** — treat the gap as an invitation to play, not a defect to hide.
  - Understanding is about **caring and persistence**, not raw intelligence.
- **Confucius parallel (the note's own cross-cultural anchor):**
  - 知之為知之，不知為不知，是知也 → cognitive honesty / admitting ignorance as the gateway.
  - 知之者不如好之者，好之者不如樂之者 → the three ascending tiers: *knowing → loving/curious → delighting/playing*, mirroring defense → honest admission → playful curiosity.
- **Why it sits in "mindset":** it adds the layer the theory omits — *the learner's felt relationship to the boundary between known and unknown*. A defensive posture blocks the loop in [what_is_learning](what_is_learning.html); a playful one accelerates it.

---

## III. Methods & Practice
*The concrete workflow for actually building the model.*

### 🛠️ How To Start Feeling New Knowledge
- **File:** [2026-06-02_how-to-start-feeling-new-knowledge](2026-06-02_how-to-start-feeling-new-knowledge.md) · *(method note, distilled from a whiteboard sketch + an LLM-assisted addendum)*
- **Summary:** A personal method for taking a new subject from *remembered information* to *felt knowledge*. **Start** by choosing a topic and asking what problem it solves (motivation + background = why it exists). **Then build a map / mental model before details** — framework, big picture, system block diagram, the highest useful level of abstraction. The note sharpens "mental model" as the answer to *"how should I think about this problem?"* with two sides: **know-what** (concepts, relations, structure) and **know-how** (frameworks, implementations, workflows). With a map in hand, choose a **route**: **top-down** (build a minimal working model, then jump into a project and learn by doing) or **bottom-up** (solidify foundations first, then build) — complementary, but different entry points. Finally, **close the feedback loop**, because one-way input creates the *illusion* of understanding: use the **Feynman output test** (explain in your own words to a non-expert, or write it down — stuck points reveal gaps) and **minimum viable practice** ("Hello World," analyze last month's spending, take one rule-of-thirds photo). An **LLM-assisted version** accelerates both stages.
- **Key ideas:**
  - Topic → **what problem does it solve?** (motivation & background first).
  - **Map before details:** frameworks, overview, system diagram, high-level abstraction.
  - A mental model = **know-what + know-how**.
  - **Top-down (project-first, minimal model)** vs **bottom-up (foundations-first)** — pick the entry point, not abstract-vs-practical.
  - **One-way input → knowledge illusion**; output is the test.
  - **Feynman output test** + **minimum viable practice** = immediate feedback from reality.
  - **"Feel knowledge"** emerges only after enough context + a concrete output/simulation.
- **LLM-assisted workflow (the addendum's contribution):**
  - **Feed strong sources first** (textbooks, lecture notes, papers, transcripts) — don't ask for a generic overview.
  - **Map the landscape:** the fundamental mental models every expert shares; where experts *disagree*; the best argument on each side; the cutting-edge open problems.
  - **Use the LLM as an examiner, not an explainer:** generate questions that separate deep understanding from memorization; turn each wrong answer into feedback ("why is this wrong, what am I missing?").
  - **Principle:** AI is most valuable when it builds a **better map** and gives **sharper feedback** — not when it produces more fluent input.
- **Why it sits in "method":** it is the operational procedure that produces the *better mental model* the theory targets, and it reuses the *Feynman output test* from the mindset note.

---

## Through-lines / shared concepts

The notes were written separately but converge on a few load-bearing ideas. This is the real value of the map — seeing the same concept refracted through theory, mindset, and method.

### "Mental model" — the spine
| Lens | What "mental model" means there | Source |
|---|---|---|
| **Theory** | The internal world model (model ②) that predicts `(s′, r)`; and the *capacity* to build it (model ①) = compression = "the Basics / framework" | [what_is_learning](what_is_learning.html), [what_is_learning_GPT](what_is_learning_GPT.md) |
| **Method** | The answer to *"how should I think about this problem?"* = **know-what + know-how**; the map you build before details | [2026-06-02_how-to-start-feeling-new-knowledge](2026-06-02_how-to-start-feeling-new-knowledge.md) |
| **Mindset** | A model is only real when built from a **sensory medium** (visualize, simulate) — language alone can't carry understanding | [2026-06-24_feynman-learning-stance](2026-06-24_feynman-learning-stance.md) |

### Other recurring threads
- **Prediction / world model** — the theoretical core ([what_is_learning_GPT](what_is_learning_GPT.md)) that the method and mindset are ultimately serving.
- **The Feynman output test** — appears as the *gateway to honesty* in [2026-06-24_feynman-learning-stance](2026-06-24_feynman-learning-stance.md) and as a *feedback mechanism* in [2026-06-02_how-to-start-feeling-new-knowledge](2026-06-02_how-to-start-feeling-new-knowledge.md). The bridge between mindset and method.
- **Names ≠ knowing / illusion of understanding** — Feynman's labels-vs-knowing ([2026-06-24_feynman-learning-stance](2026-06-24_feynman-learning-stance.md)) is the same failure the method warns about as *one-way-input knowledge illusion* ([2026-06-02_how-to-start-feeling-new-knowledge](2026-06-02_how-to-start-feeling-new-knowledge.md)).
- **Find the Basics first** — the author's "framework of which everything is a variant" ([what_is_learning](what_is_learning.html)) = the method's "map before details" ([2026-06-02_how-to-start-feeling-new-knowledge](2026-06-02_how-to-start-feeling-new-knowledge.md)).
- **"Feel" / intuition as the goal** — both method and mindset aim past *known-as-vocabulary* toward *felt-as-navigable-space*; the theory explains *why* this matters (a model you can run is a model that predicts).
- **Generalization over memorization** — explicit in [what_is_learning_GPT](what_is_learning_GPT.md), dramatized by Feynman's rote-reciting Brazilian students in [Feynman, mental model, feel](<Feynman, mental model, feel.md>).

---

## Suggested reading order
1. **[what_is_learning](what_is_learning.html)** — see the whole picture in one diagram (the map of the territory).
2. **[what_is_learning_GPT](what_is_learning_GPT.md)** — follow the reasoning that produced it.
3. **[2026-06-24_feynman-learning-stance](2026-06-24_feynman-learning-stance.md)** — adopt the stance that makes learning possible.
4. **[2026-06-02_how-to-start-feeling-new-knowledge](2026-06-02_how-to-start-feeling-new-knowledge.md)** — execute the workflow.
