# SYLLABUS.md Format

`SYLLABUS.md` is the **route** for a large topic — the ordered path a learner walks through the territory that `MAP.md` describes. It exists only for **complex topics** (see "Sizing the topic" in `SKILL.md`); a small, bounded topic does not need one and should go straight from map to expedition.

Keep the two artifacts distinct (this is the whole reason both exist):

- **`MAP.md` is the territory** — the compressed framework, "how to think about this field." It answers *"how should I think about this?"*
- **`SYLLABUS.md` is the route** — the ordered sequence of teachable **units**, pitched so each builds on the last, that carries the learner across the map to the mission. It answers *"in what order do I walk it, and how do I know each step landed?"*

The guiding belief (from `basic_learning_principles/`): the syllabus is the **minimal path that reaches the mission**, not a table of contents of the field. Compression applies at the curriculum scale too — the best syllabus is the *shortest ordered set of units* that gets the learner to felt knowledge of what the mission needs. Everything the mission does not need is left off the route.

A unit is the curriculum-scale version of the learning loop: each one is a small map→test→feedback cycle. **A unit is finished only when a `checks/` entry passes** — never when a lesson is merely delivered. The success criterion for every unit is therefore an *output the learner produces*, not a topic "covered."

## Template

```md
# Syllabus: {Topic}

**Mission:** {one line} — see `MISSION.md`
**Maps onto:** `MAP.md` (this route walks that territory)
**Route shape:** top-down (project-first) | bottom-up (foundations-first) | mixed
**Why this order:** {2-4 sentences. The dependency chain and the zone-of-proximal-development logic — why each unit has to come before the next. If the order is driven by a real project (top-down), name it.}

## Units

| # | Unit | Objective (→ mission) | Felt-knowledge proof (the output test) | Key sources | Prereqs | Status |
|---|------|----------------------|----------------------------------------|-------------|---------|--------|
| 0 | The framework (the Basics) | Install the basic mental model — the one framework everything else is a variation on | State or draw the whole framework / big picture in your own words, **and** give a first-principles reason the field's central bet works at all | {RESOURCES.md entries} | — | active |
| 1 | {name} | {what the learner will be able to do/think, traced to the mission} | {the concrete thing they must PRODUCE to pass — a Feynman explanation, a tiny working artifact, an examiner quiz} | {RESOURCES.md entries} | 0 | pending |
| 2 | {name} | {…} | {…} | {…} | 1 | pending |
| … | | | | | | |

## Open route questions
{Where the route is uncertain or might need to change — units that may split, an ordering you're unsure of, a place you suspect the mission may shift. The honest edge of the plan; the source of the next re-discussion with the learner.}
```

**Status legend:** `pending` (not started) · `active` (being taught now — exactly one at a time is the norm) · `passed` (its check passed — felt knowledge demonstrated) · `remediating` (a check found a gap; being re-taught, often re-sized or with a new sensory anchor) · `dropped` (the mission no longer needs it).

## Rules

- **The route always opens with Unit 0 — the framework.** Every syllabus begins with the framework lesson: the Basics, the one structure everything else is a variation on, taught wide-and-shallow to install the mental model the learner will think *with* (see "Lessons" in `SKILL.md`). It is `active` first; no other unit starts until its check — *state or draw the framework in your own words* — passes. Uniquely, this lesson also runs a **First-principles probe**: a block of open "fundamental questions" probing why the field's central bet works at all, worked through Socratically (not a label-recall quiz). Units 1..n are the variations that hang off it, each depending on it.
- **Agree before you build.** Draft the syllabus, then *discuss it with the learner and reach agreement* before writing the file and teaching from it. The learner co-owns the route; an imposed curriculum is a mission you cannot see. Re-agree whenever the route changes materially.
- **Minimal path, not full coverage.** The syllabus is the shortest ordered set of units that reaches the mission — not the field's table of contents. If a unit does not serve the mission, drop it. A bloated syllabus is the curriculum-scale version of a bloated map: a failed one.
- **Every unit ends in an output test.** The "Felt-knowledge proof" column is required and must name something the learner *produces* (a Feynman explanation, a minimum-viable practice, an examiner quiz). "Read chapter 4" is not a proof. The unit's status becomes `passed` only when a `checks/` entry passes — never on lesson delivery alone.
- **One unit ≈ one working-memory-sized chunk.** Size each unit so it can be taught and tested without overloading the learner. If a unit keeps producing gaps, it is too big — split it (`remediating`), don't push harder.
- **Order by dependency and the zone of proximal development.** Each unit should sit just past the edge of what the previous units established. Record the route shape (top-down vs bottom-up) and the *why* — future sessions honor it or consciously revise it (log the decision; see `LEARNING-LOG-FORMAT.md`).
- **Each unit targets a sensory anchor.** Per the Feynman stance, name (in the lesson, anchored in `MAP.md`) the way the learner will *see / feel / run* the unit's core idea. A unit that stays purely verbal is not yet felt.
- **The syllabus is alive.** Revise it in place as checks reveal reality: split an over-large unit, insert a remediation unit, reorder when a dependency was wrong, drop what the mission outgrew. Update statuses as units pass. A stale route silently misdirects every session that follows it.
- **Build it from strong sources.** Each unit points at the `RESOURCES.md` entries it teaches from. If a unit has no good source, that is a gap to fill (often with parallel source research) before teaching it — never teach a unit from parametric memory.
- **The map deepens as the route is walked.** `MAP.md` starts high-level (enough to plan the route); each passed unit deepens its slice of the map. The syllabus drives *when* each part of the territory gets surveyed in detail.
