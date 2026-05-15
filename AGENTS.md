# AGENTS.md

Scope: the entire `open-visual-grammar` repository.

## Role

You are working on a public visual-generation method, not an image prompt dump.
Your job is to preserve reusable visual judgment and keep execution details
progressively disclosed.

## Entry point

Start with:

```text
README.md
```

Then choose one pattern. Do not read every pattern by default.

## Operating principles

- Visual taste is subjective, but generation needs constraints.
- Name the visual problem before naming a style.
- A prompt is a compiled artifact, not the source of truth.
- A pattern enters this repository only after it has references, boundaries, and repeatable structure.
- Candidate styles and one-off production prompts stay outside the public grammar.
- Keep examples public-safe. Do not include credentials, private screenshots, user data, or internal account details.

## Progressive disclosure

1. Read `README.md` for the vocabulary.
2. Read only the relevant `patterns/*/PATTERN.md`.
3. Read that pattern's `adapters/*`, `examples/*`, refs, or anti-patterns only when needed.
4. Read `grammar/*` only when a specific visual decision is unclear.
5. Read `runtimes/*` only for the target output medium.
6. Read `evals/*` only when testing or promoting a pattern.
7. Avoid loading reference-heavy folders unless the task requires visual comparison.

## Pattern requirements

Every public pattern must include:

- `PATTERN.md`
- `anti-patterns.md`
- `refs/` with at least one public-safe reference image

Every pattern should define:

- use cases;
- visual problem;
- invariants;
- composition model;
- information density;
- emotional temperature;
- runtime adapter slots;
- boundaries and failure modes.

Examples should live inside the pattern they belong to.

## Eval rules

Use `docs/evaluation-protocol.md` for long-term pattern evaluation.

Eval cases and rubrics belong here. Real generated candidates, runtime prompts,
API diagnostics, and rejected attempts belong in the consuming project's work
folder unless they become reviewed pattern-local examples.

## Storage rules

Do not store one-off prompts here.

Store a generated prompt only when it is part of a reviewed pattern-local
example that explains why it worked or failed. Otherwise, temporary prompts
belong in the consuming project's work folder.
