# Score: Elegant Classic — Signature Variant

Status: draft — pending production validation

## Visual Score

```text
Viewer:      Upscale restaurant, hotel dining room, or steakhouse owner. Wants
             the menu to signal occasion and ceremony — something a guest would
             handle with a sense of formality.

Job:         Deliver a one-page menu that reads as refined, ceremonial, and
             print-serious. The design should feel like it was typeset for a
             dining room that takes the ritual of eating seriously.

Pattern:     print-menu-layout

First read:  Restaurant name, large, in a high-contrast display serif on a dark
             ground. The name should feel like it was set in a print shop, not
             on a screen.

Tension:     The menu must carry the weight of occasion without becoming heavy
             or oppressive. The dark ground must feel like a dining room, not
             a tech product. The gold must feel like a hairline, not a badge.

Metaphor:    Print ceremony. A formal menu card from a hotel dining room. The
             gold hairline is the only ornament — it does the work of all the
             decoration other directions use.

Composition: Frame — a gold hairline border defines the page. Interior rules
             are also gold hairlines. The restraint of the ornament is the
             signature.

Density:     Medium (standard menu, single column).
             Dense menus switch to two columns with the same dark tokens.

Temperature: Quiet to cold. The register of a place where the service is
             unhurried and the menu is a document, not a list.

Runtime:     Deterministic layout (HTML/CSS or equivalent typesetting engine).
             PNG 2550 × 3300 + US Letter PDF.

Forbidden:   Any warm or bright colors. Rounded corners. Bold or heavy weights
             for body text. Any element that reads as casual or approachable.
```

## Compiled Spec

```text
Output format:     PNG + PDF
Output dimensions: 2550 × 3300 px / US Letter portrait

Hierarchy:
  Level 1 (restaurant name):     176 px, Didot or Bodoni 72, regular, tracking -0.02em
  Level 2 (section labels):      36 px, Avenir Next sans, light, tracking 0.1em uppercase
  Level 3 (item names + prices): 48 px, Hoefler Text or Palatino serif, regular, tabular nums
  Level 4 (descriptions):        33 px, Hoefler Text or Palatino serif, italic, muted color

Style direction:   elegant-classic
  Background:      #12120f
  Surface:         #232317
  Text:            #f4e8cc
  Muted:           #c3b387
  Accent:          #cba258
  Secondary accent: #3c321f
  Rule color:      #a98a4d
  Heading font:    Didot, 'Bodoni 72', Georgia, serif
  Body font:       'Hoefler Text', Palatino, Georgia, serif

Composition model: Frame
Signature detail:  Gold hairline — a 1px or 0.5pt rule in accent color as the
                   outer page border and as section dividers. The hairline is
                   the only gold element. No fills, no badges, no thick rules.

Density:           Standard (≤12 items), single column
Dense behavior:    Two columns, dense type scale (146/31/40/27 px)
```

## What to Validate

When this score produces a real output, check:

- Does the dark ground feel like a dining room, not a dark-mode UI?
- Is the gold hairline the only gold element — no fills, no thick rules?
- Does the display serif feel like Didot or Bodoni, not like Georgia used as
  a fallback?
- Does the light tracking on section labels feel ceremonial, not generic?
- Would a guest at a formal dinner feel comfortable holding this menu?
