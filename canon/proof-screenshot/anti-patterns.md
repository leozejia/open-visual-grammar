# Proof Screenshot Anti-Patterns

## Fabricated UI

Generated screenshots are not proof. If exact UI state matters, use a real
screenshot or deterministic render.

## Callout clutter

Many arrows, circles, and labels make the screenshot harder to trust.

## Secret leakage

Do not publish screenshots with account emails, tokens, request IDs, internal
URLs, customer data, billing records, or private workspace names.

## Full-window laziness

A full browser or terminal window often hides the important state. Crop to the
decision surface.
