# GLOSSARY.md Format

`GLOSSARY.md` is the canonical language for this workspace. All map entries, checks, and learning-log records should adhere to its terminology.

Building the glossary is itself an act of learning, and the skill treats it that way. The theory in `basic_learning_principles/` says learning *is* compression — turning many experiences into one abstraction (10,000 cats → "cat"). **A tight definition the learner can write in their own words is direct evidence the concept has been compressed, not just stored.** So a term earns its place here only once the learner can state it cleanly — the glossary is a record of understanding achieved, not a dictionary to study from.

## Structure

```md
# {Topic} Glossary

{One or two sentence description of the territory this glossary covers.}

## Terms

**Backpropagation**:
The algorithm that assigns blame for an error backward through a network's layers so each weight can be adjusted.
_Avoid_: "the learning bit", reverse pass

**Overfitting**:
When a model captures noise in the training data instead of the underlying pattern, so it predicts new cases worse.
_Avoid_: memorizing, too much training
```

## Rules

- **Add a term only when the learner can define it in their own words.** The glossary records compressed knowledge; it is not a list of terms to be read in order to learn them. If a concept was just introduced, wait until a check shows the learner can use it correctly, then promote it.
- **Be opinionated.** When several words name the same concept, pick the best one and list the rest as aliases to avoid. Choosing the canonical word is itself compression.
- **Keep definitions tight.** One or two sentences. Define what the term *is*, not how to do it (how-to lives in `MAP.md`'s know-how). If the learner can't compress it that far, they don't fully have it yet.
- **Use the glossary's own terms inside definitions.** Once a term is in, prefer it everywhere — including inside other definitions. This is what makes later, harder terms easier to grasp.
- **Group under subheadings** when natural clusters emerge. A flat list is fine when terms cohere.
- **Flag ambiguities explicitly.** If a term is used loosely in the wider field, note the resolution in this workspace: "Here, 'model' always means the learner's internal world-model, never an ML artifact."
- **Revise as understanding deepens.** A definition written in week one may be wrong by week six. Update in place; don't leave stale entries. A corrected definition is worth a `learning-log/` note about what changed.
