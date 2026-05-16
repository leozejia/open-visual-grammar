# Score: Warm Cafe — Signature Variant

Status: draft — pending production validation

## Visual Score

```text
Viewer:      Small cafe or brunch spot owner who needs a menu to print tonight.
             No design background. Wants something that looks like it came from
             a real designer, not a template.

Job:         Deliver a one-page menu that reads as warm, approachable, and
             handcrafted — something a customer would pick up and feel good about.

Pattern:     print-menu-layout

First read:  Restaurant name, large, in a warm serif. The name anchors the page.

Tension:     The menu must feel hand-made and personal while being perfectly
             legible and price-scannable. Warmth without sloppiness.

Metaphor:    Warm paper. Ink that looks like it was applied with care. A divider
             that looks drawn, not rendered.

Composition: Rule — horizontal brush or hand-marked dividers separate sections.
             The divider style is the signature detail.

Density:     Medium (standard menu, single column).
             Dense menus switch to two columns with the same warm tokens.

Temperature: Warm. Approachable. The emotional register of a neighborhood cafe
             that knows its regulars.

Runtime:     Deterministic layout (HTML/CSS or equivalent typesetting engine).
             PNG 2550 × 3300 + US Letter PDF.

Forbidden:   Purple-blue gradients. Rounded SaaS cards. Emoji. Centered
             everything. Any element that reads as digital-first rather than
             print-first.
```

## Compiled Spec

```text
Output format:     PNG + PDF
Output dimensions: 2550 × 3300 px / US Letter portrait

Hierarchy:
  Level 1 (restaurant name):     182 px, Georgia serif, black, tracking -0.02em
  Level 2 (section labels):      42 px, Avenir Next sans, semibold
  Level 3 (item names + prices): 52 px, Avenir Next sans, regular, tabular nums
  Level 4 (descriptions):        34 px, Avenir Next sans, regular, muted color

Style direction:   warm-cafe
  Background:      #c7a46f
  Surface:         #f5ead2
  Text:            #2b1d13
  Muted:           #6f5338
  Accent:          #c0512f
  Secondary accent: #2f5b4f
  Rule color:      #4d3320
  Heading font:    Georgia, 'Iowan Old Style', serif
  Body font:       'Avenir Next', 'Trebuchet MS', sans-serif

Composition model: Rule
Signature detail:  Brush section divider — a thick, slightly irregular
                   horizontal rule in rule color that reads as hand-drawn.
                   One per section break. No other decorative elements.

Density:           Standard (≤12 items), single column
Dense behavior:    Two columns, dense type scale (150/34/42/28 px)
```

## What to Validate

When this score produces a real output, check:

- Does the restaurant name read as the dominant element within one second?
- Does the brush divider feel hand-marked or does it feel like a CSS border?
- Can a customer scan from item name to price without searching?
- Does the warm paper surface read as intentional, not as a beige background?
- Does the output look like something a cafe owner would be proud to hand to a customer?
