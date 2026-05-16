# Big Character Poster

Status: canonical

Big Character Poster is a design language for public feed covers with a strong
point of view.

It is not a prompt template and not a layout recipe. It helps an agent enter
the right visual space before writing a one-off image prompt.

## Spirit

This style believes that a cover should take a position before it decorates a
topic.

The image should feel like an editorial poster pasted onto the feed: direct,
physical, opinionated, and a little rude. It should not feel like a SaaS banner,
dashboard collage, or neutral documentation hero.

The title has weight. The evidence has texture. The metaphor makes an argument.

## Visual Language

Use this vocabulary as material, not as a checklist:

- oversized Chinese headline type;
- ink, paper, wall paint, stamp, poster grain, rough print texture;
- red pencil marks, warning marks, torn paper, pressure marks, tape, labels;
- concrete evidence objects: bill, receipt, session card, command slip, bridge,
  plug, archive tag, handoff note, status surface;
- one physical action: bends, weighs down, cuts open, peels back, cracks,
  compresses, stains, blocks, exposes;
- warm paper, black ink, dirty off-white, warning red, one small accent color.

The best images combine a loud first read with one concrete object that proves
the article is about a real problem.

## What Gives It Force

The force comes from the relationship between title, object, and argument.

Good examples usually have:

- a short title that can act like the main object;
- a concrete pain the reader recognizes;
- one object that makes the abstract claim tangible;
- a visual action that changes the title or the object;
- enough roughness to feel argued, not polished by a template;
- details that reward inspection without becoming the first read.

The title, metaphor, and evidence should feel designed together. If the title
could be swapped onto another background without changing the image, the design
language has not arrived yet.

## Source Contract

Before writing a prompt, define the current asset:

```text
Visual job:
Primary source:
Supporting sources:
Source inclusion rule:
```

The primary source is the smallest material that should drive this image:
usually the channel draft, article hook, selected passage, or campaign brief.

Add supporting sources only when they materially change the audience, factual
boundary, visual claim, delivery constraint, or reuse target.

## Argument Questions

Answer these before prompting:

```text
Reader pain:
False belief:
Correction:
Stakes:
Cover sentence:
Concrete evidence:
Visual action:
Why it bites:
```

`Concrete evidence` matters. A poster about cost should probably contain a bill,
receipt, meter, ledger, or comparable evidence object. A poster about session
recovery should probably contain a session card, command slip, archive tag, or
resume path. The evidence object is not decoration; it is what makes the claim
feel real.

## Prompting Posture

Write a fresh prompt for the current image. Do not fill a universal template.

The final prompt may be short or long, literal or metaphorical, image-model
first or layout-first. The only requirement is that it preserves the design
language:

- the cover feels like a finished poster, not a neutral asset;
- the first read has attitude;
- the title is a designed force in the composition;
- concrete evidence carries the article's real pain;
- the visual action makes the correction visible;
- the image would be hard to reuse for ten unrelated AI posts.

Let the agent choose the prompt wording that fits the article, model, and
channel. The pattern should shape judgment, not replace it.

## References

Use references as taste anchors, not as things to copy pixel by pixel:

```text
refs/agent-runtime-cost-x-cover.png
refs/context-token-economics-x-cover.png
```

Ask what makes them work:

- Where is the attitude?
- What is the first read?
- Which object proves the pain is real?
- How does the title participate in the image?
- What detail would disappear first at phone size?
- What makes the image feel like a public argument rather than a generic tech
  banner?

## Fit

Good fit:

- X Article covers;
- single-image post hooks;
- public tutorials with one strong warning or correction;
- beginner-facing AI literacy posts that need one memorable first sentence.

Poor fit:

- calm product documentation hero images;
- exact UI proof;
- step-by-step tutorials where screenshots carry trust;
- brand pages that need product photography or institutional calm.

## Review Questions

Use these to judge the result:

- Does it have a point of view?
- Does the title dominate the first second?
- Is there a concrete evidence object, not just an abstract metaphor?
- Does the visual action make the correction visible?
- Does it feel article-specific?
- Would this still work if it were seen at phone-feed size?
- Does it feel like a finished editorial poster?

If the answer is weak, revise the visual judgment before revising the wording of
the prompt.
