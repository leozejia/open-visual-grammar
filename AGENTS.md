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

Then choose one canon. Do not read every canon by default.

## Operating principles

- Visual taste is subjective, but generation needs constraints.
- Name the visual problem before naming a style.
- A prompt is a compiled artifact, not the source of truth.
- A canon enters this repository only after it has references, boundaries, and repeatable structure.
- Keep examples public-safe. Do not include credentials, private screenshots, user data, or internal account details.

## Progressive disclosure

1. Read `README.md` for the vocabulary.
2. Read only the relevant `canon/*/FRAMEWORK.md`.
3. Read `treatments/*` only after a canon is selected and surface treatment matters.
4. Read `methods/*` only when a specific visual decision is unclear.
5. Read `runtimes/*` only for the target output medium.
6. Avoid loading reference-heavy folders unless the task requires visual comparison.

## Canon requirements

Every canon must include:

- `FRAMEWORK.md`
- `anti-patterns.md`
- `refs/` with at least one public-safe reference image or a note explaining why references are pending

Every framework should define:

- use cases;
- visual problem;
- invariants;
- composition model;
- information density;
- emotional temperature;
- runtime compile slots;
- boundaries and failure modes.

## Storage rules

Do not store one-off prompts here.

Store a generated prompt only when it is part of a reviewed example that explains
why it worked or failed. Otherwise, temporary prompts belong in the consuming
project's work folder.
