# Design References

Design references are named visual traditions that an operator can invoke when
writing a Visual Score. They are not style presets. They are shorthand for a
cluster of visual decisions: proportion, weight, restraint, temperature, and
signature detail.

A reference name in a score means: apply the judgment this tradition represents,
not its surface aesthetics.

## How to Use

In a Visual Score, a reference belongs in the `Temperature` or `Metaphor` field
as a modifier, or in a free `Reference` field when the operator wants to name
the tradition explicitly.

Do not use a reference name as a substitute for naming the visual problem. The
score must still define tension, first read, and composition model independently.

## Reference Vocabulary

### Information Architecture

**Swiss Grid (Müller-Brockmann)**
Mathematical column structure. Every element earns its position by grid logic.
Whitespace is structural, not decorative. Use when the content has inherent
hierarchy that should be made visible without ornamentation.
Temperature: cold to neutral. Density: medium.

**Editorial Restraint (Build)**
Luxury whitespace. 70%+ of the surface is breathing room. One typographic
decision carries the whole composition. Use when the deliverable must signal
premium without decoration.
Temperature: quiet. Density: low.

**Typography as Object (Experimental Jetset)**
The headline is not placed over a background. The headline is the image.
Scale, weight, and position define the composition. Use when the text has
enough visual mass to stand alone.
Temperature: cold. Density: low to medium.

### Hospitality and Print

**Warm Paper (cafe menu tradition)**
Tactile surface. Warm off-white or cream ground. Ink that reads like it was
applied by hand or letterpress. Rules and dividers that feel drawn, not
rendered. Use for food, hospitality, and small-business print deliverables
where warmth and approachability matter more than precision.
Temperature: warm. Density: medium.

**Print Ceremony (fine dining menu tradition)**
Dark ground, light type, gold or cream accent. Generous margins. Hierarchy
that reads like a formal document. Use when the deliverable must signal
occasion, not everyday utility.
Temperature: quiet to cold. Density: low to medium.

**Diner Energy (American vernacular print)**
Bold borders, high contrast, appetite-forward color. Rules and ornaments that
reference ticket stubs, diner signage, and mid-century American commercial
print. Use when the deliverable should feel energetic and appetite-cuing.
Temperature: hot. Density: medium to high.

### Gentle Technology

**Organic Precision (Takram)**
Natural material colors. Curves that feel grown, not drawn. Precision in
detail but warmth in overall impression. Use when the deliverable must feel
both trustworthy and human.
Temperature: warm to neutral. Density: medium.

**Emptiness as Design (Kenya Hara)**
Absence is the primary material. What is removed defines the composition more
than what remains. Use when the deliverable must communicate refinement through
reduction.
Temperature: quiet. Density: low.

## Anti-References

These are visual traditions to avoid unless the brief explicitly requires them:

- **Default SaaS gradient** (purple→blue, blue→cyan): signals AI-generated
  output, not design judgment.
- **Rounded card with colored left border**: the canonical AI dashboard tile.
  Drop either the radius or the border.
- **Emoji as icons**: signals consumer app, not designed artifact.
- **Centered-everything symmetry**: reads as template, not composition.
- **Indigo as accent** (`#6366f1` family): the most common AI color default.

## Absorbed From

These references were distilled from:

- Open Design craft rules (`craft/anti-ai-slop.md`, `craft/typography.md`,
  `craft/color.md`) — for the anti-reference vocabulary and craft discipline
- Huashu-Design design philosophy schools (`references/design-styles.md`) —
  for the named tradition vocabulary (Pentagram, Build, Takram, Kenya Hara,
  Müller-Brockmann)
- Restaurant Menu style direction briefs in MyPromptist — for the hospitality
  and print traditions

These sources are external references. The vocabulary above is Open Visual
Grammar's own distillation. Do not treat the source documents as authoritative
within this repository.
