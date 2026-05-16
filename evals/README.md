# Evals

This directory contains reusable evaluation cases and rubrics for Open Visual
Grammar.

Evals are not image rankings and not model benchmarks. They are controlled
situations that reveal whether a visual pattern is stable, transferable, and
useful.

## Directory Map

```text
cases/      Fixed reproduction scenarios.
rubrics/    Judgment guides for operator review.
```

## How To Use

1. Choose one case from `cases/`.
2. Use the pattern named by that case.
3. Produce a visual argument stack.
4. Produce a task-specific score.
5. Compile it into the target runtime.
6. Generate three candidates in the consuming project.
7. Judge with the rubrics.
8. Feed stable learning back into the pattern.

Runtime prompts, generated images, and rejected candidates belong in the
consuming project's work folder, not here.

## First Suite

Start with:

```text
cases/big-character-poster-reproduction.md
```

This first suite tests whether the big-character poster method can reproduce
the historical GanFan / SorryCode cover quality across old and new topics.

Judge it with:

```text
rubrics/visual-argument.md
rubrics/first-read.md
rubrics/visual-tension.md
rubrics/anti-ai-template.md
rubrics/pattern-transfer.md
```

Keep this suite narrow. Add new suites only when they have their own source
contract, target runtime, and operator judgment criteria.
