# Visual Grammar Evals

Visual Grammar Evals are the long-term calibration system for Open Visual
Grammar.

They do not rank images. They test whether a pattern can repeatedly turn a
visual problem into useful generated candidates across topics, channels, and
operators.

## Purpose

Use evals to decide whether a pattern is:

- stable enough to stay public;
- too narrow and needs sharper boundaries;
- missing runtime adapters or anti-patterns;
- ready to receive a reviewed example;
- not yet a pattern and should stay in incubation.

## What evals test

Every eval run should test the full path:

```text
visual problem -> pattern -> score -> runtime prompt -> three candidates -> operator judgment -> grammar improvement
```

The grammar is the durable object. Runtime prompts are execution artifacts.

## Repository boundary

Open Visual Grammar stores:

- eval cases;
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

## Required eval run

For each case:

1. Select one pattern.
2. Produce a short visual score.
3. Compile the score for one runtime.
4. Generate exactly three candidates.
5. Attach a short rationale to each candidate.
6. Let an operator choose, reject, or request another run.
7. Record what the run teaches the pattern.

The three candidates must be meaningfully different strategies, not minor
palette or texture variants.

## Minimum suite

A first stability pass should include at least five cases:

- conflict X cover;
- concept explainer X cover;
- documentation hero;
- proof screenshot or proof-led tutorial visual;
- non-coding agent use case.

This gives the suite enough range to test conflict, abstraction, trust,
proof, and cross-audience transfer.

## Stability criteria

A pattern can be considered stable when it has passed:

- at least three different topics;
- at least two delivery contexts or aspect ratios;
- at least three real generation runs;
- at least one operator-selected production candidate;
- at least one documented anti-pattern or adapter improvement from real use;
- enough clarity that another agent can apply it without private context.

## Failure criteria

An eval fails when:

- the pattern cannot create a strong first read;
- the candidates collapse into generic AIGC templates;
- the runtime prompt becomes the source of truth;
- the pattern needs private brand context to make sense;
- the operator cannot explain why one candidate is better;
- the output is attractive but does not solve the visual problem.

Failure is useful. Convert repeated failures into boundaries, anti-patterns,
adapters, or case revisions.

## Run record template

Consuming projects should record eval runs with this structure:

```text
# Visual Grammar Eval Run

## Case
## Pattern Used
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
