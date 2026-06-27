# RESOURCES.md Format

`RESOURCES.md` is the curated set of trusted sources for this topic. It exists to enforce one rule from `basic_learning_principles/`: **feed strong sources first; never learn from parametric guesses.** Before the skill maps a field or answers a hard question, it draws on the material here — the kind of sources a serious practitioner would respect. Knowledge for the map comes from this file; wisdom comes from the communities in it.

## Structure

```md
# {Topic} Resources

## Knowledge
- [Book: _The Feynman Lectures on Physics_ — Feynman, Leighton, Sands](https://example.com)
  Foundational text built around physical intuition. Use for: the mechanics chapters when building sensory anchors.
- [Course: MIT 6.006 Introduction to Algorithms (OCW)](https://example.com)
  Rigorous, well-sequenced. Use for: the core data-structures framework in the map.
- [Paper: "Attention Is All You Need" — Vaswani et al.](https://example.com)
  The primary source for the transformer architecture. Use for: know-how once the high-level map exists.

## Wisdom (Communities)
- [r/{topic}](https://reddit.com/r/example)
  High-signal, well-moderated. Use for: critique of the learner's output, plateau troubleshooting.
- Local: {meetup / class / lab}
  Use for: real-time feedback that an agent cannot give.
```

## Rules

- **Strong sources first — this is the skill's core information diet.** Prefer primary sources, recognised experts, peer-reviewed work, canonical textbooks, and well-moderated communities. If a resource is marketing dressed as education, leave it out.
- **The map must be traceable to this file.** Non-obvious claims in `MAP.md` and `GLOSSARY.md` should point to a resource here. If a claim has no source, it is a guess — flag it, don't ship it.
- **Annotate every entry.** A bare link is useless in three months. One line: what it covers and *when to reach for it* (mapping vs. know-how vs. sensory anchors vs. practice).
- **Group by Knowledge / Wisdom.** Knowledge builds the map and the concepts; Wisdom (communities) is where the learner tests skills against real people — the thing an agent cannot replace. A resource may appear in only one group.
- **Surface gaps explicitly.** If no good resource exists for an area the mission needs, add a `## Gaps` section listing what is missing. This drives the next round of (often parallel) source research.
- **Prune ruthlessly.** A source that turned out to be wrong, shallow, or off-mission is removed, not buried. Five sharp sources beat thirty mediocre ones — and fewer, better sources compress the map.
- **Record community preferences.** If the learner has opted out of joining communities, note it here so future sessions stop proposing them.
