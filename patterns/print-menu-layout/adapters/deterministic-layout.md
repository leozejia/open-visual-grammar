# Adapter: Deterministic Layout

This adapter compiles a `print-menu-layout` Visual Score into a spec for a
deterministic layout engine (HTML/CSS, Typst, or equivalent).

## Output Contract

```text
Format:    PNG + PDF
Dimensions: 2550 × 3300 px (US Letter at 300 DPI)
PDF:       US Letter portrait, single page
Text:      Exact — no model-generated text in the final output
```

These are fixed. The consuming project's engine must enforce them.

## Compile Slots

```text
Output format:     PNG + PDF
Output dimensions: 2550 × 3300 px / US Letter portrait

Viewer:
Job:
Pattern:           print-menu-layout

First read:        [restaurant name — the dominant element]

Hierarchy:
  Level 1 (restaurant name):   [size, font, weight, tracking]
  Level 2 (section labels):    [size, font, weight]
  Level 3 (item names + prices): [size, font, tabular numerals]
  Level 4 (descriptions + contact): [size, font, muted color]

Content:
  Restaurant name:
  Cuisine type:
  Tagline:
  Sections:        [section title → items → name / description / price]
  Featured items:
  Contact:

Style direction:   [warm-cafe | clean-modern | retro-american | elegant-classic]
  Background:
  Surface:
  Text:
  Muted:
  Accent:
  Secondary accent:
  Rule color:
  Display font:     [packaged primary family]
  Body font:        [packaged primary family]
  Accent font:      [packaged primary family]
  Font package:     [source, license, runtime path]

Typography scale:  [standard | dense — determined by item count]
  Restaurant name:
  Section labels:
  Item names + prices:
  Descriptions:

Composition model: [rule | column | field | frame]
Signature detail:  [one named element — brush divider, editorial rule, ticket border, gold hairline]

Density:           [standard (≤12 items) | dense (13–20 items)]
  Dense behavior:  two-column layout, smaller type scale

Forbidden:
  - MyPromptist branding in the output file
  - decorative elements outside the named style direction
  - web-scale font sizes on a print canvas
  - centered alignment except where the direction requires it
  - host system fonts as the intended primary appearance
  - runtime network font fetching for customer deliverables
```

## Density Switch Rule

Item count determines layout density. The style direction does not change.

| Item count | Layout | Type scale |
| --- | --- | --- |
| ≤ 12 | Single column | Standard |
| 13–20 | Two columns | Dense |

The engine must apply the dense scale automatically. The operator does not
choose density manually.

## Price Alignment Rule

All prices must use tabular numerals and align to a consistent right column
within each section. The gutter between item name and price must be visually
unambiguous — not just a space character.

## Font Packaging Rule

The renderer must load the exact font files selected by the visual score. A
font stack is not a permission to accept whatever happens to exist on the host.
For production deliverables, a missing primary font is a QA failure.

Consuming projects should vendor the font files, keep license/source metadata
with them, load them from an explicit runtime font path, and disable system
font lookup when the engine supports that. Local, CI, and production output
must be rendered with the same font package.

The launch font contract for this pattern lives in `../typography.md`.

## Signature Detail Rule

Each style direction has exactly one signature detail. It must appear in the
output. It must not be multiplied or varied across variants.

| Direction | Signature detail |
| --- | --- |
| Warm Cafe | Brush or hand-marked section divider |
| Clean Modern | Thin editorial rule system (hairline weight) |
| Retro American | Ticket border and star or arrow ornaments |
| Elegant Classic | Gold hairline rules and serif hierarchy |

## Variant Behavior

All four variants of a direction share the same color tokens, font role mapping, and
signature detail. Variants differ only in spacing, type scale, and decoration
density.

| Variant | What changes |
| --- | --- |
| Signature | Baseline — strongest visual identity |
| Compact | Tighter spacing, slightly smaller type |
| Feature | More visual weight on featured items |
| Quiet | Reduced decoration, calmer overall |
