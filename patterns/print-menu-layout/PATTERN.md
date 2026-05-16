# Print Menu Layout

```yaml
id: print-menu-layout
status: candidate
artifact_kinds:
  - deterministic-layout
runtimes:
  - html-css
  - typst
  - pdf
when_to_use: Single-page restaurant menus that must become print-ready PNG/PDF or deterministic HTML/Typst output.
avoid_when: Multi-page brochures, digital-only screen menus, unpriced posters, or editable customer templates.
requires_grammar:
  - typography
load_next:
  deterministic-layout: adapters/deterministic-layout.md
  typography: typography.md
  font-packaging: ../../runtimes/font-packaging.md
```

中文名：印刷菜单版式
English name: Print Menu Layout

Status: candidate

## Definition / 定义

Print Menu Layout is a fixed-format typesetting pattern for single-page food
and beverage menus delivered as print-ready PNG or PDF.

It turns a structured list of items into a readable, printable artifact. The
restaurant name is not a label at the top of a table. The restaurant name is
the anchor of the composition. Everything else — sections, items, prices,
contact — descends from it in a clear hierarchy.

印刷菜单版式是一种固定格式排版范式，用来把单页餐饮菜单交付成可打印的 PNG 或 PDF。

它把结构化菜单条目变成可读、可打印的成品。餐厅名不是表格顶部的一个标签，而是整个构图的锚点。章节、菜品、价格和联系方式都从这个锚点向下形成清晰层级。

## Recommended Cases / 推荐场景

- The output is a single-page US Letter or A4 portrait document.
- The content is a structured list: sections, item names, descriptions, prices.
- The deliverable must be printable or postable without editing.
- The buyer has no design skill and needs a finished artifact, not a template.
- The style direction has a named visual tradition (warm paper, print ceremony,
  diner energy, editorial restraint).

- 输出是单页 US Letter 或 A4 竖版文档；
- 内容是结构化列表：章节、名称、描述、价格；
- 交付物需要直接打印或发布，不再编辑；
- 购买者没有设计能力，需要成品而不是模板；
- 风格方向有明确视觉传统，例如暖纸、印刷仪式感、美式 diner 能量、编辑克制感。

## Weak Fit / 不适合

- The menu spans more than one page (multi-page brochure is a different pattern).
- The output is a digital-only screen menu (different density and interaction
  model).
- The content has no price structure (poster or flyer pattern is more
  appropriate).
- The buyer needs to edit the output after delivery (editable template is a
  different product).

- 多页菜单或宣传册；
- 纯数字屏幕菜单；
- 没有价格结构的内容；
- 交付后还需要用户自行编辑的模板型产品。

## Visual Problem / 视觉问题

The viewer should be able to read the menu and make a decision without effort.

The layout must solve three problems simultaneously:

1. **Identity**: the restaurant name and style direction must be recognizable
   within one second.
2. **Scanning**: a customer must be able to find any item and its price without
   searching.
3. **Printability**: the composition must hold at 300 DPI on physical paper,
   not just on screen.

观看者应该能不费力地阅读菜单并做出选择。

版式必须同时解决三个问题：

1. **Identity / 识别**：餐厅名和风格方向必须在一秒内被识别。
2. **Scanning / 扫读**：顾客不用搜索就能找到菜品和价格。
3. **Printability / 可打印性**：构图必须在 300 DPI 实体纸张上成立，而不只是屏幕预览好看。

## Invariants / 不变量

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

- 一个支配性的餐厅名，定义最高层级；
- 章节标签低于餐厅名，但高于菜品；
- 菜品名和价格必须形成清楚视觉配对；
- 描述文字低于菜品名，只增加质感，不承担结构；
- 有联系方式时必须清楚可读，但不能抢菜单内容；
- 构图在完整打印尺寸和缩略预览中都成立；
- 交付物不能出现 MyPromptist 品牌；
- 不加入命名风格方向之外的装饰元素。

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

## Avoid / 避免

- Mixing multiple composition models in one menu;
- making the restaurant name behave like a table label;
- price alignment that forces the eye to search;
- decoration that does not belong to the named style direction;
- layouts that only work on screen and fail at print size.

- 一个菜单里混用多个构图模型；
- 把餐厅名做成表格标签；
- 价格对齐含糊，让眼睛到处找；
- 加入不属于命名风格方向的装饰；
- 只在屏幕上成立、打印尺寸失效的版式。

## Typography Role

The restaurant name should behave like a headline, not a label:

- large enough to anchor the composition;
- set with negative tracking at display sizes;
- placed with enough margin that it breathes;
- in the style direction's packaged display font, not a host fallback.

Section labels are structural markers. They should be visually distinct from
item names but not compete with the restaurant name.

Item names and prices must be typeset with tabular numerals for price alignment.
Descriptions are set smaller and in a muted color.

Typography is part of the visual grammar, not an implementation afterthought.
For the launch font contract and runtime packaging rules, see `typography.md`.
The consuming project must use packageable open-source fonts as primary
rendering assets and must not rely on macOS, Windows, or Linux system fonts for
the intended appearance.

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
- display, body, and accent font roles
- signature detail (the one element that makes the direction memorable)
- composition model

The four initial directions for Restaurant Menu:

| Direction | Tradition | Launch typography | Signature detail |
| --- | --- | --- | --- |
| Warm Cafe | Warm paper | Fraunces + Source Sans 3 | Hand-marked or brush divider |
| Clean Modern | Editorial restraint | Newsreader + IBM Plex Sans | Thin editorial rule system |
| Retro American | Diner energy | Bowlby One SC + Archivo | Ticket border and star ornaments |
| Elegant Classic | Print ceremony | Bodoni Moda + Cormorant Garamond | Gold hairline and serif hierarchy |

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
- packaged display, body, and accent font roles
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
