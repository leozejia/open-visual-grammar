# Runtime: Deterministic Layout

Deterministic layout is good at exact text, exact hierarchy, exact dimensions,
and repeatable output from structured input.

Use this runtime when the visual idea depends on precision:

- a menu that must be printable at 300 DPI;
- a document where every price must align to a column;
- a page where the hierarchy must be unambiguous at any scale;
- an artifact that must be identical across every generation from the same input.

Engines in this category: HTML/CSS (browser or headless), Typst, LaTeX, any
fixed-format typesetting tool. The grammar does not prescribe the engine. The
consuming project chooses the engine that fits its output contract.

## What This Runtime Is Good At

- Exact text rendering with no hallucination risk.
- Tabular alignment (prices, data columns, structured lists).
- Fixed output dimensions (US Letter, A4, square, custom).
- Repeatable output: same input always produces the same file.
- Print-safe typography at high DPI.
- Hierarchy enforced by token values, not by model judgment.

## What This Runtime Is Bad At

- Mood, atmosphere, and material texture (use image generation for these).
- Continuous motion and field behavior (use shader for these).
- Organic or hand-drawn visual qualities.
- Layouts where the visual idea depends on unpredictable composition.

## Compile a Score into a Deterministic Layout Spec

Use these slots:

```text
Output format:
Output dimensions:
Viewer:
Job:
Pattern:
First read:
Hierarchy:
  Level 1 (dominant):
  Level 2 (structural):
  Level 3 (body):
  Level 4 (subordinate):
Content:
Style direction:
  Background:
  Surface:
  Text:
  Muted:
  Accent:
  Rule:
  Heading font:
  Body font:
Typography scale:
  Level 1 size:
  Level 2 size:
  Level 3 size:
  Level 4 size:
Composition model:
Signature detail:
Density:
Forbidden:
```

## Rules

**Hierarchy before decoration.** Define all four hierarchy levels before
choosing any decorative element. Decoration that does not serve hierarchy is
noise.

**Tokens, not hard-coded values.** Every color, size, and spacing value must
come from a named token. Hard-coded values make the style direction
non-transferable.

**Print scale, not screen scale.** If the output is a print document, size
all typography for the output canvas, not for a browser viewport. A 2550 × 3300
canvas is not a 1440px screen.

**Exact dimensions are a contract.** The output format and dimensions are part
of the deliverable contract. They must be enforced by the engine, not assumed.

**Signature detail is one thing.** Each style direction has one element that
makes it memorable. Define it explicitly. Do not add decoration beyond it.
