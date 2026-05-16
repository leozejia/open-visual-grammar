# Anti-Patterns: Print Menu Layout

These are the failure modes that appear most often when generating print menu
layouts. Each one has a name, a description of what goes wrong, and a correction.

## 1. Label Stack

**What it looks like:** The restaurant name is set at the same size as the
section labels. The page reads as a list of equal-weight items with no anchor.

**Why it happens:** The generator treats all text as content and sizes it
proportionally to the canvas without establishing a dominant element.

**Correction:** The restaurant name must be at least 3× the size of section
labels. It anchors the composition. Everything else descends from it.

---

## 2. Price Orphan

**What it looks like:** Prices float to the right of item names without a
clear visual connection. The eye has to search to match item to price.

**Why it happens:** The layout uses a simple flex row without tabular numerals
or a consistent price column.

**Correction:** Use tabular numerals for all prices. Align prices to a
consistent right column. The gutter between item name and price should be
visually clear, not just a space.

---

## 3. Description Noise

**What it looks like:** Descriptions are set at the same weight and color as
item names. The menu reads as a wall of equal-weight text.

**Why it happens:** The generator applies one text style to all menu content.

**Correction:** Descriptions must be visually subordinate: smaller size, muted
color, lighter weight. A customer scanning for an item should be able to skip
descriptions without losing their place.

---

## 4. Decoration Without Direction

**What it looks like:** The menu has ornamental elements (borders, rules,
dividers, corner marks) that do not belong to any named style direction. They
feel generic or mismatched.

**Why it happens:** The generator adds decoration to fill space or signal
"designed," without grounding the decoration in a specific visual tradition.

**Correction:** Every decorative element must be part of the named style
direction's signature. If the direction is Warm Cafe, the divider is a brush
rule. If the direction is Elegant Classic, the rule is a gold hairline. If an
element cannot be named as part of the direction, remove it.

---

## 5. Web Scale Typography

**What it looks like:** The menu looks correct on screen but prints too small.
Item names are 14–18 px on a 2550 × 3300 canvas, which reads as 1–2 pt at
print scale.

**Why it happens:** The generator uses web UI font sizes instead of print-scale
sizes.

**Correction:** On a 2550 × 3300 canvas, item names must be 46–52 px minimum.
See the typography size table in `PATTERN.md`. Always QA output at print scale,
not screen scale.

---

## 6. Clipped Content

**What it looks like:** The last section or item is cut off at the bottom of
the page. The contact line is missing or partially visible.

**Why it happens:** The layout does not account for variable content length.
A menu with 20 items overflows a layout designed for 10.

**Correction:** The renderer must switch to dense layout (two columns, smaller
type) when item count exceeds the standard threshold. The contact line must
always be reserved space at the bottom of the composition, not placed after
the last item.

---

## 7. Style Drift Across Variants

**What it looks like:** The four variants of one style direction look like four
different styles. The Compact variant uses different colors than the Signature
variant.

**Why it happens:** Variants are generated independently without sharing a
token base.

**Correction:** All four variants of a direction must share the same color
tokens, font role mapping, and signature detail. Variants differ only in
spacing, type scale, and decoration density — not in color or typeface.

---

## 8. Centered Everything

**What it looks like:** Every element — restaurant name, section labels, item
names, prices, contact — is centered. The page has no left edge to scan.

**Why it happens:** Centering is the default alignment when no composition
model is specified.

**Correction:** Most menu layouts should be left-aligned or use a clear
two-column structure. Centering is appropriate only for the restaurant name
in ceremonial directions (Elegant Classic) and only when the rest of the
layout provides a clear left-aligned scanning path.

---

## 9. Host Font Drift

**What it looks like:** The same order looks refined on the designer's Mac but
generic or metrically different on the Linux production server. Line breaks,
title width, and section rhythm shift even though the tokens did not change.

**Why it happens:** The renderer relies on system fonts or broad fallback
stacks. Local output uses faces such as Didot, Hoefler Text, Avenir Next, or
Cooper Black, while production substitutes unrelated fonts.

**Correction:** Package the selected open-source fonts and load them from an
explicit runtime font path. Treat missing primary fonts as a QA failure. Do not
promote a menu direction until local and production PNG/PDF output use the same
font files.
