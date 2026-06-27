# CHECK.md Format

Checks live in `./checks/` and use sequential numbering: `0001-slug.md`, `0002-slug.md`, etc. Create the directory lazily — only when the first check is written.

A **check** is one turn of the Phase-2 feedback loop made durable. It is how the skill fights the central failure mode from `basic_learning_principles/`: **one-way input creates the illusion of understanding.** Reading and nodding feel like learning; only *output* reveals whether the model is real. A check captures that output, the gap it exposed, and what closed the gap.

Three kinds of check (the `Type` field):
- **Feynman output test** — the learner explains a concept in plain words to an imagined novice (or writes it down). The stuck/vague/circular point *is* the finding.
- **Minimum viable practice** — the learner makes the concept work once in reality ("Hello World"; analyze last month's spending; one rule-of-thirds photo).
- **Examiner quiz** — the agent generates questions that separate deep understanding from memorization; wrong answers become feedback.

## Template

```md
# {What was checked}

- **Type:** Feynman output test | Minimum viable practice | Examiner quiz
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
- **Close the loop in the file.** A check that finds a gap is only half-done until Resolution names what fixed it or what the next session will do. An open check is a standing item for the next session.
- **Checks feed the map.** When a check shows the map was wrong or thin, update `MAP.md` and cross-link the check from a `learning-log/` entry. The feedback loop is what keeps model ② honest.
- **Desirable difficulty.** Prefer checks that require retrieval from memory over recognition; space them out over sessions; for skills, interleave related concepts rather than testing one in isolation.
