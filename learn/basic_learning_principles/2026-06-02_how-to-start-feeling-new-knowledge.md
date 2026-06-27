# How To Start Feeling New Knowledge

Source: [raw/how_to_start_feeling_new_knowledge (ingested).jpg](<../../raw/how_to_start_feeling_new_knowledge (ingested).jpg>)

Related note filed 2026-06-08: user-provided LLM learning workflow referencing [How an MIT student compressed a semester of learning into 48 hours](https://sinapti.ca/post/en/how-an-mit-student-compressed-a-semester-of-learning-into-48-0zrzqxjb).

Date ingested: 2026-06-02

## Summary

This image is a whiteboard sketch about a personal method for learning a new thing until it starts to become felt knowledge, not merely remembered information. It is separate from the Reality Transurfing material: the topic here is learning methodology.

The flow begins by choosing a topic and asking what problem it solves, including the motivation and background behind the topic. From there, the learner should establish a map or mental model before diving into details. The map should include the basic framework, the big picture, an overview, a system block diagram, and the highest useful level of abstraction.

A later clarification sharpens the meaning of "mental model": a mental model answers the question "how should I think about this problem?" It has two sides. The first is know what, or concept understanding: what the concepts mean, how they relate, and what structure makes the topic intelligible. The second is know how, or practical operation: coding frameworks, implementations, workflows, and concrete ways to make the concept work. When summarizing the mental model of a topic or problem, the user can therefore organize around these two dimensions.

Once that map exists, learning can proceed through two different paths. Top-down learning means first building the most basic working mental model, then going directly into a project and learning while doing. Bottom-up learning means first studying the foundations and getting the basics solid, then moving into projects. The contrast is not abstract versus practical; it is project-first with a minimal working model versus foundation-first before doing.

A later clarification adds an essential feedback loop. One-way input, such as reading books or watching videos, can create the illusion that the learner understands. To test whether the knowledge is real, the learner should produce an explanation or a tiny practice result. The Feynman-style output test is to explain a newly learned concept in one's own words to someone who knows nothing about the field, or write that explanation into a document. If the explanation gets stuck, that stuck point reveals what is not yet understood. Minimum viable practice serves the same function: write the first "Hello World" program, analyze last month's spending in a budgeting app, or take one photo that deliberately uses the rule of thirds.

A later LLM-assisted version adds a way to accelerate the map-building and feedback-loop stages. First, feed the LLM high-quality foundational material for the topic: textbooks, lecture slides, video scripts, papers, or other serious sources. Then ask questions that reveal the field's landscape: the fundamental mental models shared by experts, the main points where experts disagree, the best argument from each side, and the cutting-edge open problems. After the map exists, use the LLM as an examiner rather than only as an explainer: generate questions that distinguish deep understanding from memorized facts, answer them, and turn each incorrect answer into immediate feedback by asking why it is wrong and what is missing.

## Key Ideas

- Start with a topic, then ask what problem it solves.
- Motivation and background matter because they explain why the topic exists.
- Before collecting details, establish a map or mental model.
- A useful map includes frameworks, big-picture overviews, system diagrams, and high-level abstractions.
- A mental model answers "how should I think about this problem?"
- A mental model has two sides: know what, meaning concept understanding, and know how, meaning practical frameworks, implementations, and workflows.
- Top-down learning means build a basic working mental model, then start a project and learn as the project exposes gaps.
- Bottom-up learning means learn the basics first, strengthen the foundations, then start doing projects.
- Top-down learning and bottom-up learning are complementary, but they have different entry points.
- One-way input can create a knowledge illusion: it can feel like understanding before understanding has been tested.
- Use Feynman output to test understanding: explain the concept in plain words to a non-expert, or write it down clearly.
- If the explanation gets stuck, the stuck point is useful feedback about what is not yet understood.
- Use minimum viable practice to get immediate feedback from reality.
- When using an LLM, first give it strong source material rather than asking it to explain from generic memory.
- Use the LLM to map the field's landscape: shared expert mental models, live disagreements, best arguments on each side, and open problems.
- Use the LLM as an examiner: generate questions that expose whether understanding is deep or merely memorized.
- Treat wrong answers as valuable signals, then immediately ask what is wrong and what is missing.
- "Feel knowledge" emerges after enough context has accumulated and the learner has produced or simulated something concrete.
- Implementation, simulation code, product-making, or hints from real practice help turn abstract structure into intuition.

## LLM-Assisted Landscape Mapping

The LLM-assisted version begins by narrowing the information diet. The learner does not ask the model for a generic overview of a topic. Instead, they first feed it foundational material that serious learners or practitioners would respect: textbooks, lecture notes, papers, video scripts, or other primary learning sources.

From that corpus, the first goal is to see the landscape before drowning in details. Useful prompts include:

- What are the five fundamental mental models shared by every expert in this field?
- Where do experts in this field fundamentally disagree?
- What is the best argument from each side of those disagreements?
- What are the cutting-edge open problems in this topic?

This extends the earlier "mental model" idea. A topic becomes more navigable when the learner can see both the consensus structure and the fault lines. Expert disagreement is especially useful because it reveals where the field is alive, uncertain, or still being argued over.

The second goal is to test whether the learner's understanding is real. Instead of asking the LLM for more explanation, the learner asks it to generate questions that would distinguish someone who truly understands the topic from someone who has only memorized facts. Each answer becomes a diagnostic event. If the answer is wrong, the next prompt is not simply "give me the right answer," but "explain why this is wrong and what I am missing."

This turns the LLM into a feedback machine. Its best role is not to replace the learner's understanding, but to expose the exact places where the learner's map is vague, brittle, or borrowed.

## Feedback And Output Checks

The method needs an active test against the illusion of understanding. Passive input is useful, but it is not enough. Reading and watching can feel fluent because the material is already organized by someone else. Output forces the learner to reconstruct the concept from inside their own model.

The Feynman output check is simple: take one newly learned concept and explain it in one's own words to a person who knows nothing about the field, or write the explanation into a document. The point is not polish; the point is to expose missing links. Any place where the explanation becomes vague, circular, or stuck becomes the next learning target.

Minimum viable practice gives the same kind of feedback through action:

- Programming: type a tiny program and make the screen print "Hello World".
- Personal finance: use a budgeting app to analyze the structure of last month's spending.
- Photography: take one phone photo that deliberately follows the rule of thirds.

These tiny outputs turn learning from "I consumed the explanation" into "I can make the concept work at least once."

## Relevance To Inner Core And World Model

For the inner core, this source suggests that learning feels alive when the user can locate a subject inside a coherent map and then test it through concrete practice. A topic becomes satisfying when it is not just known as vocabulary, but felt as a navigable space with causes, purposes, levels, examples, and feedback from output.

For the world model, it implies that understanding a field requires asking why it exists, what problem it solves, and how its parts fit together. The user distinguishes two viable learning routes: a top-down route that builds just enough working model to enter a project quickly, and a bottom-up route that builds foundations first before doing. The shared goal is not just completion of a project or mastery of basics, but enough context, output, and contact with the material for intuition to form.

The LLM-assisted addition reinforces a specific belief about good learning technology: AI is most valuable when it helps build a better map and creates sharper feedback, not when it merely produces more fluent input. Feeding the model strong sources, asking for expert mental models and disagreements, and then using adversarial understanding questions all keep the learner in an active position.

## Provisional Notes

- Some handwriting in the lower part of the image is difficult to read, so the exact transcription is less certain than the conceptual structure.
- The main durable insight is methodological: feeling new knowledge depends on enough context, a usable mental model, a good choice between project-first and foundation-first learning routes, and feedback loops that reveal whether the learner can explain or do something with the knowledge.
- The LLM-assisted workflow is treated as a useful learning pattern, not as proof that any single anecdotal claim about compressed learning time is reliable.
- This should not be treated as a fixed learning doctrine; it is a compact snapshot of one currently visible learning pattern.
