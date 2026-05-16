# Visual Argument

A visual argument is the cover-level claim that sits between an article topic
and a visual pattern.

It is not the title. It is not the metaphor. It is the correction the image
must make visible.

Good image generation often fails when this step is skipped. The output can
look like the right style while saying almost nothing.

## Argument Stack

Before choosing a pattern or writing a runtime prompt, define the input
contract and fill this stack:

```text
Visual job:
Primary source:
Supporting sources:
Source inclusion rule:
Raw topic:
Reader pain:
False belief:
Correction:
Stakes:
Cover sentence:
Visual action:
Why it bites:
```

## Field Meanings

`Visual job` names the deliverable and channel, such as an X cover, a docs hero,
an article card, a slide opener, or a shader scene.

`Primary source` is the smallest source that should drive the visual judgment.
Use the channel draft, selected passage, brief, script, or scene notes that the
asset is actually serving.

`Supporting sources` are materials that materially change the audience, factual
boundary, visual claim, delivery constraint, or reuse target.

`Source inclusion rule` states why extra sources were included. If a source does
not affect the current asset's judgment, it is not part of the input contract.

`Raw topic` is what the article is about.

`Reader pain` is the concrete confusion, cost, fear, or mistake the reader has.

`False belief` is the simple belief the cover challenges.

`Correction` is the article's operational lesson.

`Stakes` is why the correction matters enough to open the article.

`Cover sentence` is the first-read sentence, often the title.

`Visual action` is the physical verb that makes the correction visible:

```text
weighs down
cuts open
peels back
collides with
bends under
leaks through
compresses
reveals
contaminates
```

`Why it bites` explains why the action is sharper than a generic metaphor.

## Good Visual Actions

A good visual action:

- is a verb, not just an object;
- attacks the false belief directly;
- makes the correction visible without a paragraph;
- is specific enough that it cannot fit ten unrelated AI posts;
- can be judged before generation.

## Input Discipline

More context is not automatically better visual direction.

If a project has multiple outputs from one thesis, define which output the image
serves before extracting the argument. A cover for a social post, a hero for
documentation, and a slide opener may need different visual arguments even when
they share the same topic.

Do not build the visual argument from a title alone when a primary source exists.
Start from the primary source. Add supporting sources only when they materially
change the asset's judgment.

## Weak Visual Actions

Weak actions usually look like this:

- a generic object beside a title;
- a dashboard showing the topic;
- a symbol that only restates the title;
- a metaphor so broad it could fit any article;
- a pretty scene with no correction.

## Examples

### Agent Runtime Cost

```text
Raw topic: Claude Code can call GPT through compatible runtime paths.
Reader pain: The user expects compatibility to mean roughly equivalent cost.
False belief: If it can run GPT, the runtime choice is mostly cosmetic.
Correction: Runtime path, cache behavior, and billing surfaces can change the economics.
Stakes: A working setup can still burn money fast.
Cover sentence: 能跑 GPT / 不等于划算
Visual action: A working bridge bends under a cost weight.
Why it bites: The bridge proves the tool works while the bend exposes the hidden price.
```

### Context Token Economics

```text
Raw topic: Long agent sessions can have high cache hit rates and still cost money.
Reader pain: The user sees high cache hit and assumes the session is healthy and cheap.
False belief: More retained context is always better if cache hit is high.
Correction: Cached context still has a price, and stale context can become state debt.
Stakes: A session that feels efficient can quietly become expensive and dirty.
Cover sentence: 上下文不是越多越好
Visual action: A polished context stack turns into a weight pressing the title onto a small ledger.
Why it bites: The same thing that looked like an asset becomes a liability.
```

### Codex History

```text
Raw topic: Codex local sessions can be recovered after the visible list changes.
Reader pain: The user thinks a missing session surface means the work is gone.
False belief: If the conversation disappeared from the visible history, the record is gone.
Correction: Local records may still exist and can be listed or resumed.
Stakes: The user may stop searching too early and lose usable work.
Cover sentence: 丢了会话 / 不等于丢了记录
Visual action: An empty history surface peels back to reveal a local record underneath.
Why it bites: It distinguishes surface disappearance from underlying storage.
```

### Codex Plugins

```text
Raw topic: Codex plugin state can look unavailable in one surface while actions exist elsewhere.
Reader pain: The user trusts a grey plugin entry and stops checking.
False belief: A grey plugin entry means the plugin cannot be used.
Correction: Runtime and input-box actions may reveal working plugin capability after setup.
Stakes: The user may abandon a working configuration because one surface looks disabled.
Cover sentence: 灰掉的插件 / 不等于不能用
Visual action: A grey status mask is cut open by a live input cursor.
Why it bites: It makes the visible state look like a misleading layer, not the whole truth.
```

## Gate

If the visual action is weak, do not generate.

Rewrite the argument stack first. A stronger image model will only polish a weak
argument.
