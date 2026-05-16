# Image Generation Adapter

Use this adapter when an agent needs to turn `big-character-poster` judgment
into an image-generation prompt.

This adapter is a meta-prompt protocol. It does not provide a universal prompt
template.

## Before Writing The Prompt

The agent should answer, in its own words:

```text
What is this image for?
What source is driving the image?
What should the viewer feel in one second?
What false belief is being challenged?
What correction must become visible?
What concrete evidence object makes the pain real?
How does the title behave as part of the picture?
What physical action carries the argument?
What should be left to the image model's taste?
What must be checked after generation?
```

These answers are planning material. They do not need to appear verbatim in the
final prompt.

## Compile Posture

Write the final prompt for the current article, model, and channel.

The prompt should invite a finished editorial poster, not a neutral background
asset. It should give the model enough visual material to design with:

- the exact or intended headline;
- the article-specific pain;
- one concrete evidence object;
- one physical action;
- the desired poster temperament;
- the visual materials and texture;
- the channel size or aspect ratio;
- any real-world details that make the image less generic.

The agent may choose concise phrasing, descriptive phrasing, bilingual phrasing,
or reference-led phrasing. The pattern does not require one wording shape.

## Candidate Direction

When making multiple candidates, vary the visual idea, not just the labels.

Useful axes:

- evidence object: bill, receipt, handoff note, command slip, bridge, plug,
  archive card;
- title relationship: stamped, crushed, cut open, wrapped, weighed, blocked;
- visual temperature: rough newspaper, wall poster, receipt collage, propaganda
  print, editorial magazine;
- metaphor distance: literal evidence, near metaphor, more editorial metaphor.

Keep the same article argument across candidates, but allow the agent to choose
which visual language best carries it. Three candidates do not need to map to a
fixed list of composition models.

## Review After Generation

Judge the image, not the prompt.

Ask:

- Is this a finished poster?
- Does the headline have visual force?
- Is the evidence object specific enough?
- Does the image make the article's correction visible?
- Does it avoid generic AI/software banner energy?
- Would the operator be willing to publish it without explaining the prompt?

If the image fails, revise the visual judgment. Do not keep adding prompt
clauses just to satisfy a checklist.
