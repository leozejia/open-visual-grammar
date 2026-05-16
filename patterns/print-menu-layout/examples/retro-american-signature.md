# Score: Retro American — Signature Variant

Status: draft — pending production validation

## Visual Score

```text
Viewer:      Diner, burger joint, BBQ spot, or food truck owner. Wants the menu
             to feel energetic, appetite-forward, and fun — something that fits
             the personality of the place.

Job:         Deliver a one-page menu that reads as bold, confident, and full of
             diner energy. The design should feel like it belongs on the wall of
             a place that takes its food seriously but not itself.

Pattern:     print-menu-layout

First read:  Restaurant name, large, in a heavy display font. The name should
             feel like it was stamped or printed with intention.

Tension:     The menu must carry bold visual energy without becoming illegible
             or chaotic. The border and ornaments must feel like they belong to
             a specific American vernacular tradition, not like clip art.

Metaphor:    Diner ticket. Mid-century American commercial print. The border is
             a ticket stub edge. The stars or arrows are section markers from
             that tradition.

Composition: Frame — a thick outer border defines the page boundary. Section
             ornaments (stars, arrows, or ticket marks) punctuate the interior.

Density:     Medium (standard menu, single column).
             Dense menus switch to two columns with the same bold tokens.

Temperature: Hot. Appetite-forward. The register of a place that wants you to
             be hungry before you finish reading.

Runtime:     Deterministic layout (HTML/CSS or equivalent typesetting engine).
             PNG 2550 × 3300 + US Letter PDF.

Forbidden:   Thin or delicate rules. Serif body text. Muted or desaturated
             colors. Any element that reads as refined or restrained.
```

## Compiled Spec

```text
Output format:     PNG + PDF
Output dimensions: 2550 × 3300 px / US Letter portrait

Hierarchy:
  Level 1 (restaurant name):     168 px, Cooper Black or Arial Black, tracking -0.01em
  Level 2 (section labels):      40 px, Arial Black, tracking 0.04em uppercase
  Level 3 (item names + prices): 46 px, Arial Black, regular, tabular nums
  Level 4 (descriptions):        30 px, Arial Narrow, regular, muted color

Style direction:   retro-american
  Background:      #c9281d
  Surface:         #fff0c7
  Text:            #17120e
  Muted:           #5b5145
  Accent:          #c9281d
  Secondary accent: #f0b12d
  Rule color:      #17120e
  Heading font:    'Cooper Black', 'Arial Black', Georgia, serif
  Body font:       'Arial Black', 'Arial Narrow', sans-serif

Composition model: Frame
Signature detail:  Thick outer border (14px) in rule color with rounded corners
                   (34px radius). Star or arrow ornaments as section dividers —
                   three stars or a single arrow in accent color. No other
                   decorative elements.

Density:           Standard (≤12 items), single column
Dense behavior:    Two columns, dense type scale (140/34/38/25 px)
```

## What to Validate

When this score produces a real output, check:

- Does the thick border feel like a ticket stub edge, not a generic box?
- Does the restaurant name feel stamped or printed, not typed?
- Do the star or arrow ornaments feel like they belong to the tradition, not
  like clip art additions?
- Is the yellow-on-cream surface readable at print scale?
- Does the overall energy feel appetite-forward without being chaotic?
