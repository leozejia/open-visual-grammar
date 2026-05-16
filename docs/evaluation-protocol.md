# Visual Grammar Evals

Visual Grammar Evals are the long-term calibration system for Open Visual
Grammar.

They do not rank images and do not benchmark image-model capability. They test
whether a visual method can be reproduced across topics by another operator.

## Purpose

Use evals to decide whether a pattern is:

- stable enough to stay public;
- too broad and needs sharper invariants;
- missing runtime adapters or anti-patterns;
- ready to receive a reviewed example;
- not yet a pattern and should stay in incubation.

## What Evals Test

Every eval run should test the full path:

```text
visual method -> visual job -> input contract -> visual argument -> score -> runtime prompt -> three candidates -> operator judgment -> grammar improvement
```

The grammar is the durable object. Runtime prompts are execution artifacts.

## Repository Boundary

Open Visual Grammar stores:

- reproduction cases;
- rubrics;
- promotion rules;
- public-safe reviewed examples;
- pattern improvements discovered from evals.

Consuming projects store:

- article briefs;
- task-specific visual scores;
- runtime prompts;
- generated candidates;
- rejected images;
- production delivery assets;
- operator notes for a specific run.

Do not store one-off production prompts or raw generated candidates in this
repository unless they become reviewed pattern-local examples.

## Required Eval Run

For each topic:

1. Select one pattern.
2. Define the visual job and input contract.
3. Produce a visual argument stack from the primary source.
4. Produce a short visual score.
5. Compile the score for one runtime.
6. Generate exactly three candidates.
7. Make the three candidates different visual-language solutions for the same
   article argument.
8. Let an operator choose, reject, or request another run.
9. Record what the run teaches the pattern.

The three candidates should preserve the same source contract and article
argument, but they may vary evidence object, title relationship, poster
temperament, metaphor distance, and material language.

The visual argument must stay constant across the three candidates. A run that
changes the claim for each candidate is testing ideas, not pattern stability.

The input contract must also stay constant across the three candidates. A run
that quietly changes source scope between candidates is testing context luck,
not pattern stability.

## First Stability Suite

The first public stability pass focuses on one method:

```text
patterns/big-character-poster/
```

Use `evals/cases/big-character-poster-reproduction.md`.

This suite exists to answer one question:

```text
Can the big-character poster method reproduce the historical cover quality
across old and new topics?
```

It should not expand into documentation heroes, proof screenshots, non-coding
agent adoption, or other visual jobs until the first pattern is stable.

## Stability Criteria

A pattern can be considered stable when it has passed:

- at least three different topics;
- at least two real generation runs;
- at least one unseen topic;
- at least one operator-selected production candidate;
- at least one documented anti-pattern or adapter improvement from real use;
- enough clarity that another agent can apply it without private context.

## Failure Criteria

An eval fails when:

- the visual job or primary source is unclear;
- the pattern cannot create a strong first read;
- the topic was compiled before a visual argument existed;
- the visual action is a generic object instead of a verb;
- the title becomes a caption instead of the visual structure;
- candidates collapse into generic AIGC templates;
- three candidates are merely style variants;
- the runtime prompt becomes the source of truth;
- the operator cannot explain why one candidate is better;
- the output is attractive but does not preserve the method's invariants.

Failure is useful. Convert repeated failures into boundaries, anti-patterns,
adapters, or case revisions.

## Run Record Template

Consuming projects should record eval runs with this structure:

```text
# Visual Grammar Eval Run

## Pattern
## Visual Job
## Input Contract
## Visual Argument
## Visual Score
## Runtime
## Three Candidates
## Operator Choice
## Why It Passed Or Failed
## Workflow Issues
## Grammar Issues
## Proposed Grammar Change
```

Do not turn this run record into a prompt library.
