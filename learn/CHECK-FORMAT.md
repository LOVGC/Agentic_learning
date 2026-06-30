# CHECK.md Format

Checks live in `./checks/` and use sequential numbering: `0001-slug.md`, `0002-slug.md`, etc. Create the directory lazily — only when the first check is written.

A **check** is one turn of the expedition's feedback loop made durable. It is how the skill fights the central failure mode from `basic_learning_principles/`: **one-way input creates the illusion of understanding.** Reading and nodding feel like learning; only *output* reveals whether the model is real. A check captures that output, the gap it exposed, and what closed the gap.

Four kinds of check (the `Type` field):
- **Feynman output test** — the learner explains a concept in plain words to an imagined novice (or writes it down). The stuck/vague/circular point *is* the finding.
- **Minimum viable practice** — the learner makes the concept work once in reality ("Hello World"; analyze last month's spending; one rule-of-thirds photo).
- **Examiner quiz** — the agent generates questions that separate deep understanding from memorization; wrong answers become feedback.
- **First-principles probe** — an open-ended question that interrogates the *premise the topic rests on* ("why do we even believe this is possible?"), not the content just taught. No single right answer; the learner reasons from the ground up and the agent pushes with more "why"s. The finding is where they substitute a label, a memorized fact, or circular reasoning for an actual reason. This is the **framework lesson's signature deep check** (Unit 0); it can also surface anytime a learner mistakes a name for understanding.

## Template

```md
# {What was checked}

- **Type:** Feynman output test | Minimum viable practice | Examiner quiz | First-principles probe
- **Date:** {YYYY-MM-DD}
- **Targets:** {the map concept(s) / skill being tested}
- **Result:** passed | partial | gap found

## Prompt
{The exact challenge: the question asked, the thing to explain, or the tiny task set.}

## Learner output
{What the learner actually produced — their explanation, answer, or result. Capture it faithfully, including where it broke down. Do not clean it up; the rough edges are the data.}

## Diagnosed gap
{Where the output went vague, circular, stuck, or wrong — and what that reveals is not yet understood. This is the single most valuable line in the file. "Could name it but could not say why it happens." If Result is passed, write "none — clean."}

## Feedback
{What was missing and why, in the learner's own terms. For a wrong answer: not just the right answer, but *why* the wrong one was tempting and what the model was missing.}

## Resolution
{What closed the gap (re-explanation, a sensory anchor, a source, a redo) — or, if still open, what the next session should do. Note any MAP.md / GLOSSARY.md / learning-log updates this triggered.}
```

## Rules

- **The gap is the point.** A check that finds nothing is fine occasionally, but a run of clean passes usually means the difficulty is too low — push the zone of proximal development outward (see `LEARNING-LOG-FORMAT.md`).
- **Capture the raw output.** Do not polish the learner's explanation before recording it. Vague, circular, and stuck phrasings are the diagnostic signal; smoothing them away destroys the data.
- **Output before verdict.** Never record a concept as understood on the strength of input alone. A `learning-log/` "understood" entry should point to a passing check as its evidence.
- **Feedback explains, it does not just correct.** Per the examiner principle: turn every wrong answer into "why is this wrong, what are you missing?" — not "here is the right answer."
- **A First-principles probe is graded by depth reached, not by a right answer.** It passes when the learner reasons down to bedrock; it finds a gap when they stop at a label or go circular ("it works because that's how it works"). Don't hand over *the* answer — there may not be one; the probe can legitimately end at an open question the field itself hasn't settled (cross-ref the `MAP.md` landscape). Keep it playful: a probe is an invitation to think, never an exam.
- **Close the loop in the file.** A check that finds a gap is only half-done until Resolution names what fixed it or what the next session will do. An open check is a standing item for the next session.
- **Checks feed the map.** When a check shows the map was wrong or thin, update `MAP.md` and cross-link the check from a `learning-log/` entry. The feedback loop is what keeps model ② honest.
- **Desirable difficulty.** Prefer checks that require retrieval from memory over recognition; space them out over sessions; for skills, interleave related concepts rather than testing one in isolation.
