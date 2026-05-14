# Proof Screenshot

Proof Screenshot is a canon for visuals where the reader needs to see a real
state, not a designed metaphor.

## Use when

- A button is disabled, hidden, or newly enabled.
- A settings page has one important control.
- A command output proves success or failure.
- The tutorial depends on exact UI state.
- Trust comes from showing the real thing.

## Do not use when

- No real screenshot is available.
- The screenshot would expose private data.
- The visual only needs to create a mood.
- A generated metaphor can teach the concept more clearly.

## Visual problem

The viewer should feel: "This is the exact state I should look for."

The image should reduce uncertainty, not decorate the article.

## Invariants

- Use real screenshots or deterministic renders.
- Never ask an image model to invent a software screenshot.
- One screenshot should dominate.
- One callout is usually enough.
- Private data must be cropped, blurred, or removed.
- The caption should clarify the action or state, not restate the whole article.

## Composition model

Use one of these models:

- Focus frame: crop tightly around the relevant UI state.
- Annotated state: one arrow, box, or highlight points to the exact control.
- Before/after: only when contrast is essential.
- Terminal proof: show the relevant command and result, not the whole session.

## Information density

Medium to high, but only because the real UI may contain detail.

The annotation should create a clear first read.

## Emotional temperature

Cold-warm.

This canon should feel factual, calm, and helpful.

## Runtime compile slots

When compiling into an image asset, define:

- source screenshot path;
- private-data treatment;
- crop target;
- callout target;
- caption;
- channel size;
- forbidden edits.

When using image generation, restrict it to background or framing. Do not use it
to generate fake UI proof.
