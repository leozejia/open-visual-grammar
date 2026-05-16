# Print Menu Layout

Status: candidate

Print Menu Layout is a fixed-format typesetting pattern for single-page food
and beverage menus delivered as print-ready PNG or PDF.

It turns a structured list of items into a readable, printable artifact. The
restaurant name is not a label at the top of a table. The restaurant name is
the anchor of the composition. Everything else — sections, items, prices,
contact — descends from it in a clear hierarchy.

## Use When

- The output is a single-page US Letter or A4 portrait document.
- The content is a structured list: sections, item names, descriptions, prices.
- The deliverable must be printable or postable without editing.
- The buyer has no design skill and needs a finished artifact, not a template.
- The style direction has a named visual tradition (warm paper, print ceremony,
  diner energy, editorial restraint).

## Do Not Use When

- The menu spans more than one page (multi-page brochure is a different pattern).
- The output is a digital-only screen menu (different density and interaction
  model).
- The content has no price structure (poster or flyer pattern is more
  appropriate).
- The buyer needs to edit the output after delivery (editable template is a
  different product).

## Visual Problem

The viewer should be able to read the menu and make a decision without effort.

The layout must solve three problems simultaneously:

1. **Identity**: the restaurant name and style direction must be recognizable
   within one second.
2. **Scanning**: a customer must be able to find any item and its price without
   searching.
3. **Printability**: the composition must hold at 300 DPI on physical paper,
   not just on screen.

## Invariants

- One dominant restaurant name. It defines the top of the hierarchy.
- Section labels are clearly subordinate to the name but clearly superordinate
  to items.
- Item names and prices are visually paired; the eye must move between them
  without ambiguity.
- Descriptions are subordinate to item names; they add texture, not structure.
- Contact information is present when provided and legible, but does not compete
  with the menu content.
- The composition holds at both full print size (2550 × 3300 px) and scaled
  preview size.
- No MyPromptist branding appears in the deliverable.
- No decorative elements that are not part of the named style direction.

## Composition Models

Use one of these models per style direction. Do not mix.

- **Column**: items and prices in two columns with a clear gutter. Use for
  dense menus and editorial directions.
- **Rule**: horizontal rules separate sections. The rule style (weight, color,
  ornament) carries the style signature.
- **Field**: the background material (color, texture, paper) is the primary
  style signal. Typography is set against it without additional decoration.
- **Frame**: a border or outer rule defines the page boundary. The interior
  is clean. Use for formal and ceremonial directions.

## Typography Role

The restaurant name should behave like a headline, not a label:

- large enough to anchor the composition;
- set with negative tracking at display sizes;
- placed with enough margin that it breathes;
- in the style direction's heading font, not a fallback.

Section labels are structural markers. They should be visually distinct from
item names but not compete with the restaurant name.

Item names and prices must be typeset with tabular numerals for price alignment.
Descriptions are set smaller and in a muted color.

Print-scale sizes (on a 2550 × 3300 canvas):

| Element | Standard menu | Dense menu |
| --- | --- | --- |
| Restaurant name | 168–182 px | 140–150 px |
| Section labels | 36–42 px | 31–34 px |
| Item names and prices | 46–52 px | 38–42 px |
| Descriptions | 30–34 px | 25–28 px |

## Information Density

Medium for standard menus (up to ~12 items). High for dense menus (13–20
items). Dense menus switch to a two-column layout and smaller type scale.

The density level is determined by item count, not by style direction.

## Emotional Temperature

Determined by the style direction, not by the pattern itself.

| Direction | Temperature |
| --- | --- |
| Warm paper (cafe, brunch) | Warm |
| Editorial restraint (wine bar, tasting menu) | Quiet to neutral |
| Diner energy (burger, BBQ, diner) | Hot |
| Print ceremony (fine dining, hotel) | Quiet to cold |

## Style Directions

Each style direction is a named visual tradition. See
`grammar/design-references.md` for the vocabulary.

A style direction defines:

- background material and surface color
- text and muted text colors
- accent and secondary accent
- rule color and weight
- heading, body, and accent font stacks
- signature detail (the one element that makes the direction memorable)
- composition model

The four initial directions for Restaurant Menu:

| Direction | Tradition | Signature detail |
| --- | --- | --- |
| Warm Cafe | Warm paper | Hand-marked or brush divider |
| Clean Modern | Editorial restraint | Thin editorial rule system |
| Retro American | Diner energy | Ticket border and star ornaments |
| Elegant Classic | Print ceremony | Gold hairline and serif hierarchy |

## Runtime Adapter Slots

When compiling into a Typst template or deterministic renderer, define:

- output dimensions (2550 × 3300 px PNG, US Letter PDF)
- style direction and variant (Signature, Compact, Feature, Quiet)
- restaurant name, cuisine type, tagline
- sections and items (name, description, price, featured flag)
- contact information
- layout density (standard or dense, determined by item count)
- composition model for this direction
- signature detail implementation
- font stacks with system fallbacks
- color tokens (background, surface, text, muted, accent, secondary accent, rule)

## Variants

Inside a concrete style direction, four variants are generated:

| Variant | Purpose |
| --- | --- |
| Signature | Balanced version with the direction's strongest visual identity |
| Compact | Tighter spacing for longer menus while keeping price scanning clear |
| Feature | Stronger treatment for featured or hero items |
| Quiet | Reduced decoration for a calmer printable version |

## Good Fit

- Cafe, brunch, and bakery menus.
- Food truck and bar menus.
- Small restaurant menus with up to 20 items.
- Any single-page food or beverage list that needs to look designed.

## Bad Fit

- Multi-page restaurant brochures.
- Digital-only screen menus with interactive elements.
- Menus with more than 20 items (layout breaks down).
- Menus that need photography as the primary visual element.
