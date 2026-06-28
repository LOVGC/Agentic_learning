# MAP.md Format

`MAP.md` is the **central artifact** of this skill. It is the learner's *mental model of the field made explicit* — the thing [knowledge-map](basic_learning_principles/knowledge-map.md) calls model ②. Everything in Phase 1 (Cartography) builds it; everything in Phase 3 (Expedition) pressure-tests and extends it.

**Map vs syllabus — territory vs route.** The map is the **territory**: the compressed framework, "how to think about this field." A complex topic also gets a `SYLLABUS.md` (format: [SYLLABUS-FORMAT.md](./SYLLABUS-FORMAT.md)) — the **route**, an ordered sequence of teachable units *through* this territory. They are complementary: the map says how to think; the syllabus says in what order to walk. For a complex topic the map is built **high-level first** (enough to plan the route) and then **deepened unit by unit** as the syllabus is walked — so "minimal working map first" is doubly true at the start of a large topic.

The guiding belief (from `basic_learning_principles/`): a field becomes learnable once you find its **Basics — one framework of which almost everything else is just an implementation or adaptation.** The map is not a summary of the field; it is the *smallest structure that makes the rest of the field predictable.* Compression is the goal, not coverage.

A map answers one question: **"How should I think about this?"** It has two sides — **know-what** (the concepts) and **know-how** (how to make them work) — plus a view of the field's **landscape** (where it is settled, where it is alive, where it is unknown).

## Template

```md
# Map: {Topic}

## The framework (the Basics)
{2-5 sentences. The single organizing idea or structure of the field. State it so that the rest of the topic reads as variations on it. If you cannot compress the field to a paragraph yet, the map is not done — say so explicitly in Open edges.}

## Big picture
{A system block diagram or a short ASCII sketch: the main parts and how they connect / flow. The highest useful level of abstraction — no detail that does not change the shape.}

## Know-what — the concepts
{The handful of concepts that carry the field, and how they relate. Not definitions (those live in GLOSSARY.md) — relationships. "X is a special case of Y." "A trades off against B." Aim for ~5-9; if there are more, the framework above is probably too weak.}

| Concept | Why it matters | Relates to |
|---|---|---|
| {…} | {…} | {…} |

## Know-how — making it work
{The concrete ways the concepts get used: workflows, methods, tools, implementations, moves. What a practitioner actually does. This is what keeps the map from being inert vocabulary.}

## Sensory anchors
{For each core concept, one way to SEE / touch / imagine / run it as an internal simulation (the Feynman move). "Picture X as…" A map you can only say in words is not yet felt.}

## Landscape
### Consensus — what every expert shares
- {Mental models experts take for granted}

### Live disagreements — where the field is alive
- {Disagreement} — **Best argument each side:** {A} vs {B}

### Open problems — the frontier
- {Cutting-edge unsolved questions}

## Open edges
{What this map does NOT yet cover, where it feels thin or borrowed, and the next thing that would most strengthen it. This is the link back into Phase 1 and the source of the next expedition.}
```

## Rules

- **Compression over coverage.** The map's value is how much of the field it lets you *predict or derive*, not how much it lists. A longer map is usually a worse map. If it runs past ~2 screens, the framework is too weak — keep hunting for the Basics.
- **Build it from strong sources, never from parametric guesses.** Every non-obvious claim in the map should trace to something in `RESOURCES.md`. Cite inline where it matters.
- **Know-what and know-how both, always.** A map with only concepts produces the illusion of understanding; a map with only how-to produces brittle recipes. The skill builds both columns.
- **The landscape is what makes a map navigable.** Consensus tells the learner what to trust; disagreements show where the field is still being argued (the most useful places to think); open problems show the edge. Use parallel source research to populate it.
- **Sensory anchors are required, not decorative.** Per the Feynman stance, a concept the learner cannot visualize or simulate is not yet understood. If no anchor exists for a core concept, that is a flagged gap in Open edges.
- **The map is alive.** Revise it in place as understanding deepens; when a Phase-2 check reveals the map was wrong or thin, update it and record *why* in a `learning-log/` entry. A stale map silently misdirects every future session.
- **Minimal working map first.** Phase 1 ends when the map is *good enough to act on*, not when it is complete. Completeness comes from the expedition, not before it.
