# Conflict Poster

Conflict Poster is a high-signal cover canon for public feeds.

It makes one argument visible before the viewer reads the article.

## Use when

- The channel is X, newsletter, or another scroll-heavy surface.
- The article has a real conflict, mistake, warning, or counterintuitive lesson.
- The cover needs to be readable on a phone.
- The image is a hook, not the whole tutorial.

## Do not use when

- The article is a quiet reference document.
- Exact UI proof matters more than opinion.
- The claim is subtle and should not be exaggerated.
- The output must look like official product documentation.

## Visual problem

The viewer should feel: "I know what this argues, and I want the explanation."

The poster must compress the article into one visible collision:

```text
claim vs reality
promise vs cost
tool name vs runtime behavior
more context vs dirtier state
```

## Invariants

- One core title, usually short Chinese or short English.
- One visual metaphor.
- Big type is the skeleton, not a caption.
- Supporting text is optional and must stay secondary.
- The composition should still work when heavily downscaled.
- The poster should not become an infographic.

## Composition model

Use one of these models:

- Compression: the title is squeezed, bent, weighed down, or overloaded.
- Collision: two forces meet at the center.
- Meter: a gauge, counter, bill, cache, or warning surface reveals the hidden cost.
- Fracture: a clean surface breaks in one meaningful place.

## Information density

Low to medium.

The first read should be the title or central conflict. Details can exist, but
they should behave like texture.

## Emotional temperature

Warm-hot.

This canon can carry attitude, but it should not become clickbait. The conflict
must come from the article's real point.

## Runtime compile slots

When compiling into an image prompt, define:

- target channel and exact aspect ratio;
- title text;
- audience;
- conflict pair;
- one metaphor;
- composition model;
- color temperature;
- forbidden elements;
- safe area.

When compiling into deterministic layout, keep generated imagery as background
or metaphor and set final text manually.

## Good fit

- X Article covers.
- Single-image post hooks.
- Public tutorial covers with a strong opinion.

## Bad fit

- Long-lived documentation hero images.
- Legal, pricing, or policy pages that need institutional calm.
- Screenshots that must prove an exact UI state.
