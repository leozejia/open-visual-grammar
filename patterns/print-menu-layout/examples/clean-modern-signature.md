# Score: Clean Modern — Signature Variant

Status: draft — pending production validation

## Visual Score

```text
Viewer:      Wine bar, tasting menu, or chef-led restaurant owner. Wants the
             menu to signal editorial taste and restraint — the kind of menu
             that gets photographed and posted.

Job:         Deliver a one-page menu that reads as precise, considered, and
             quietly confident. The design should feel like it was made by
             someone who has strong opinions about whitespace.

Pattern:     print-menu-layout

First read:  Restaurant name, large, in a refined serif. Set against a light
             neutral ground with generous margin.

Tension:     The menu must carry strong visual identity through restraint alone.
             No decoration except the rule system. The rules must do all the
             work that other directions do with color and ornament.

Metaphor:    Editorial print. A well-designed magazine feature page. The rule
             system is the only ornament.

Composition: Rule — thin editorial hairlines separate sections. The rule weight
             and spacing are the signature detail. No other decoration.

Density:     Medium (standard menu, single column).
             Dense menus switch to two columns with the same neutral tokens.

Temperature: Quiet to neutral. Confident without being cold. The register of a
             restaurant that does not need to announce itself.

Runtime:     Deterministic layout (HTML/CSS or equivalent typesetting engine).
             PNG 2550 × 3300 + US Letter PDF.

Forbidden:   Any border or frame around the page. Rounded corners. Color
             accents used more than twice. Any element that reads as decorative
             rather than structural.
```

## Compiled Spec

```text
Output format:     PNG + PDF
Output dimensions: 2550 × 3300 px / US Letter portrait

Hierarchy:
  Level 1 (restaurant name):     178 px, Baskerville serif, regular, tracking -0.02em
  Level 2 (section labels):      38 px, Avenir Next sans, semibold, tracking 0.06em uppercase
  Level 3 (item names + prices): 50 px, Avenir Next sans, regular, tabular nums
  Level 4 (descriptions):        34 px, Avenir Next sans, regular, muted color

Style direction:   clean-modern
  Background:      #e6e1d7
  Surface:         #faf7f2
  Text:            #1c1a17
  Muted:           #777069
  Accent:          #2f5b4f
  Secondary accent: #e8ece3
  Rule color:      #bbb0a4
  Heading font:    Baskerville, 'Iowan Old Style', Georgia, serif
  Body font:       'Avenir Next', Helvetica, sans-serif

Composition model: Rule
Signature detail:  Thin editorial hairline — a single-pixel or 0.5pt rule in
                   rule color above each section label. Generous space above
                   the rule. No other decorative elements.

Density:           Standard (≤12 items), single column
Dense behavior:    Two columns, dense type scale (150/32/42/28 px)
```

## What to Validate

When this score produces a real output, check:

- Does the page feel like it has more whitespace than a typical menu?
- Is the rule system the only decoration — nothing else competing?
- Does the section label uppercase tracking feel intentional, not generic?
- Can the output be mistaken for a designed artifact from a real studio?
- Does the restraint read as confidence, not as emptiness?
