# Example: Token Economics Conflict Poster

This example shows the difference between a feed cover and a documentation hero.

## Source problem

The article argues that high cache hit rate is useful but not free, and that
long agent sessions can accumulate hidden cost and dirty state.

## Selected canon

`canon/conflict-poster`

## Visual score

```text
Viewer: Agent-tool user who thinks cached tokens are basically free
Job: Stop the scroll and create a cost question
Canon: conflict-poster
First read: Context is not free
Tension: 95% cache hit vs real bill
Metaphor: Huge cached context pressing on a cost meter
Composition: Compression or meter
Density: Low-medium
Temperature: Warm-hot
Runtime: Image generation for X Article cover
Forbidden: fake dashboard, random English, full pricing table, official-looking logos
```

## Runtime

Image generation with a 5:2 cover target, followed by manual inspection.

If the title text is wrong, typeset it deterministically rather than trusting the
image model.

## References

See:

```text
canon/conflict-poster/refs/
```
