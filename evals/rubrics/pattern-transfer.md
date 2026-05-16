# Rubric: Pattern Transfer

Pattern transfer tests whether a pattern works beyond one lucky article.

## Strong

- The same pattern can support multiple topics without becoming repetitive.
- The argument stack changes by topic while the pattern invariants remain stable.
- The pattern survives different aspect ratios with clear adaptation.
- The score can compile into more than one runtime.
- Another operator can apply the pattern from the documented rules.

## Weak

- The pattern only works for one phrase or one brand context.
- Every output looks like the same image with different text.
- The pattern transfers style but loses argument quality.
- The pattern breaks when the channel size changes.
- The runtime prompt contains hidden decisions not present in the score.

## Operator questions

- What changed between topics and what stayed invariant?
- Did the new topic receive a fresh visual argument?
- Did the pattern guide decisions or merely name a style?
- Can the result be adapted to another channel?
- What should be promoted into the pattern after this run?
