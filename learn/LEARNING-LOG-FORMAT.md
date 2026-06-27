# Learning Log Format

Learning-log entries live in `./learning-log/` and use sequential numbering: `0001-slug.md`, `0002-slug.md`, etc. Create the directory lazily — only when the first entry is written.

The learning log is the skill's **episodic memory** — its record of where the learner's comfort zone currently sits. In the theory of `basic_learning_principles/`, learning is *pushing the comfort zone (model ②) outward*; the log tracks the location of that boundary over time, so each session can pick up at the right edge instead of re-teaching the known or overshooting into the unlearnable.

Entries are the learning equivalent of architectural decision records: they capture non-obvious, decision-grade facts that should steer future sessions — not a session-by-session diary.

## Template

```md
# {Short title of what shifted}

{1-3 sentences: what was learned, established, corrected, or decided — and why it changes what to do next session.}
```

That is the whole format. An entry can be one paragraph. The value is recording _that_ the comfort-zone boundary moved and _why_ it changes the next move — not in filling out sections.

## Optional sections

Include only when they add genuine value; most entries won't need them.

- **Status** frontmatter (`active | superseded by LL-NNNN`) — when an earlier understanding turns out wrong and is replaced.
- **Evidence** — how the learner demonstrated it (link the passing `checks/` entry, the prior experience cited). Use when the claim might be revisited.
- **Implications** — what this unlocks or rules out for the zone of proximal development. Worth recording when non-obvious.

## When to write an entry

Write one when any of these is true:

1. **The learner demonstrated genuine understanding of something non-trivial** — evidence (a passing check), not mere exposure. This raises the floor of what to teach next. Link the check.
2. **The learner disclosed prior knowledge** — "I already know X." Record it (and the depth claimed) so future sessions don't re-teach it.
3. **A misconception was corrected** — the learner believed something wrong and now sees why. These are the highest-value entries: they predict future stumbling blocks in related areas.
4. **A route decision was made** — top-down (project-first) vs bottom-up (foundations-first) for this stretch, and why. Future sessions should honor or consciously revisit it.
5. **The map or mission shifted in response to learning** — the learner found the framework was wrong/thin, or discovered they cared about something different. Cross-link to `MAP.md` / `MISSION.md` and update them.

### What does _not_ qualify

- Material merely covered. Coverage is not learning — wait for output/evidence.
- Anything already captured tersely in `GLOSSARY.md` as a definition. Don't duplicate.
- A blow-by-blow of the session. The log holds decision-grade insight, not activity.

## Zone of proximal development

The log is read at the start of each session to locate the learner's edge. Calibrate difficulty from it: a run of passing checks with no corrections means the edge has moved and the next session should reach further out; repeated gaps on the same point mean back up and rebuild (often via a sensory anchor or a stronger source).

## Supersession

When a later entry contradicts an earlier one (understanding deepened or corrected), mark the old one `Status: superseded by LL-NNNN` rather than deleting it. The history of how the comfort zone moved is itself useful signal.
