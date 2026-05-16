# Case: Big Character Poster Reproduction

## Job

Test whether `big-character-poster` can reproduce a proven visual method across
multiple article topics.

This case does not test whether an image model can draw many kinds of images.
It tests whether a visual method survives topic changes.

The eval target is one deliverable at a time. Before each run, define the
visual job and input contract. For example, an X-cover reproduction run should
use the X draft or X hook as the primary source; related documentation drafts
are boundary material only if they are needed for factual accuracy.

## Pattern

`patterns/big-character-poster/PATTERN.md`

## Historical References

Use the existing pattern references as method references:

```text
patterns/big-character-poster/refs/agent-runtime-cost-x-cover.png
patterns/big-character-poster/refs/context-token-economics-x-cover.png
```

The reference images teach structure, not copying.

## Topics

Run at least three topics in one pass:

- Agent runtime cost: `能跑 GPT / 不等于划算`
- Context token economics: `上下文不是越多越好`
- Session recovery: `丢了会话 / 不等于丢了记录`
- Plugin status confusion: `灰掉的插件 / 不等于不能用`
- One unseen SorryCode tutorial topic chosen by the operator

## Required Score Fields

- Visual job
- Primary source
- Supporting sources
- Source inclusion rule
- Viewer
- Job
- Pattern
- Reader pain
- False belief
- Correction
- Stakes
- First read
- Conflict pair
- Concrete evidence
- Visual action
- Why it bites
- Poster temperament
- Title relationship
- Visual language notes
- Density
- Temperature
- Runtime
- Review questions

## Runtime Target

Final X Article cover output:

```text
1500x600
```

## Three-Card Requirement

For each topic, generate exactly three candidates.

They should share the same article argument and source contract, but they do
not need to map to a fixed list of composition labels. Let each candidate choose
a different way to make the article pain concrete.

Useful variation axes:

- evidence object;
- title relationship;
- poster temperament;
- metaphor distance;
- material language.

All three candidates must share the same reader pain, false belief, correction,
and source contract. If the three cards solve three different article arguments,
the run is invalid.

## Pass Signals

- The title is the main visual object.
- The visual action attacks the false belief.
- A concrete evidence object makes the article pain specific.
- The image clearly serves the declared visual job.
- The first read works at feed size.
- The conflict is visible without surrounding article text.
- The metaphor serves the title instead of replacing it.
- The image feels like the same visual method across topics without becoming a
  template swap.

## Fail Signals

- The title becomes a small caption over an illustration.
- The prompt starts from topic plus style without an argument stack.
- The source scope is unclear or too broad for the asset job.
- The visual action is only a generic object.
- The evidence object is generic enough to fit many unrelated AI posts.
- The image turns into a dashboard, fake UI, or infographic.
- Three candidates are just style variants or compliance variations.
- The result looks like a generic AI/software banner.
- The output looks good but the method cannot be explained.
