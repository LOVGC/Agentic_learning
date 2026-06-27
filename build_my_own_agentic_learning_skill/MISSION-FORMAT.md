# MISSION.md Format

`MISSION.md` lives at the workspace root. It captures the _reason_ the learner is learning this topic. Every decision the skill makes — what to map first, which sources to surface, which checks to run, where to set the zone of proximal development — should trace back to this document.

Beyond the personal "why," this skill insists on a second thing the learning theory in `basic_learning_principles/` treats as essential: **what problem does the topic itself solve, and what is its motivation and background?** A learner who knows why a *field* exists can place new ideas inside a purpose; a learner who doesn't is memorizing labels. So the mission grounds both the learner's goal and the topic's reason-for-being.

## Template

```md
# Mission: {Topic}

## Why I'm learning this
{1-3 sentences. The concrete real-world goal the learner is chasing. What changes in their life or work when they have this? Push past "to understand X" to the underlying outcome.}

## What problem this topic solves
{1-3 sentences. Why does this field/skill exist at all? What did the world look like before it, and what does it make possible? This frames every concept that follows as an answer to a real problem.}

## Success looks like
- {A specific, observable thing the learner will be able to do or feel}
- {Another — ideally one that requires producing or making something (output), not just recognizing}
- {…}

## Starting point
{What the learner already knows or can do here, and how they'd rate their depth. Sets the initial zone of proximal development. "Total beginner" is a fine answer.}

## Constraints
- {Time, budget, deadlines, learning preferences — anything that bounds the approach}

## Out of scope
- {Adjacent topics the learner explicitly does not want to chase right now — protects the zone of proximal development}
```

## Rules

- **One mission per workspace.** Two unrelated topics are two workspaces.
- **Concrete over abstract.** "Ship a Rust CLI to my team by August" beats "learn Rust." "Read a quantum-computing paper without getting lost" beats "understand quantum computing."
- **Always fill in 'What problem this topic solves.'** If neither the learner nor the sources can say why the field exists, that is the first thing to map — do not skip it. Motivation is load-bearing, not decoration.
- **Push back on vagueness.** If the learner cannot articulate why, interview them before writing anything. A bad mission is worse than no mission.
- **Capture the starting point honestly.** Over-claiming prior knowledge wastes sessions re-teaching; under-claiming bores. This is the anchor for difficulty calibration.
- **Revise when reality shifts.** Missions change as understanding grows (this is expected — see `LEARNING-LOG-FORMAT.md`). When the learner's goal moves, confirm, then update this file and log why — don't leave a stale mission steering future sessions.
- **Keep it short.** If `MISSION.md` runs past a screen, it has stopped being a compass and become a plan.
