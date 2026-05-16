# Open Visual Grammar / 开放视觉语法

Open Visual Grammar 是一套把视觉直觉翻译成可执行生成结果的方法。

它不是 prompt 库。Prompt 是某个 runtime 的编译结果。真正值得沉淀
的资产，是视觉语法：一个视觉意图如何变成张力、层级、密度、隐喻、
材料和执行约束。

## 为什么需要它

AIGC 让生产图片、PPT、网页、视频、shader 变得便宜。

但它没有让视觉判断变便宜。

很多失败的生成，问题都出在视觉不变量太弱。

Open Visual Grammar 的顺序更靠前：

1. 观众第一眼应该理解什么？
2. 画面里的张力是什么？
3. 跨主题复用时，什么必须保持不变？
4. 信息密度应该多高？
5. 最后由哪个 runtime 执行？

## 核心概念

| 概念 | 含义 |
| --- | --- |
| Grammar / 语法 | 跨 pattern 的底层视觉语言：张力、层级、密度、隐喻、节奏、温度。 |
| Pattern / 范式 | 可复用视觉抽象，内部持有稳定不变量、迁移边界、参考图、adapter 和案例。 |
| Canonical / 正典状态 | 一个 pattern 的成熟度状态，不作为顶层目录。 |
| Score / 谱面 | 单次任务的视觉计划，可以编译成 prompt、shader spec、deck layout 或 scene brief。 |
| Runtime / 执行器 | 生成落地的媒介：图像模型、HTML/CSS、PPT、shader、视频、游戏引擎。 |

## 仓库结构

```text
grammar/     跨 pattern 的视觉语法。只有具体决策需要时再读。
patterns/    稳定视觉范式。一次只加载一个。
runtimes/    跨 pattern 的执行约束。
evals/       测试 pattern 稳定复现能力的用例和判断标准。
docs/        协议和操作说明。
decisions/   架构说明和项目决策记录。
```

案例跟随对应 pattern 存放。一次性生产 prompt 不进入这个仓库。

Pattern slug 使用英文 kebab-case，保证路径、工具调用和 GitHub 链接稳定。
面向人的 `PATTERN.md` 采用单文件中英双语：中文和英文都是一等工作语言。

## Agent 使用原则

渐进披露，不要一次把所有上下文塞进去：

1. 读 `AGENTS.md`。
2. 从 `patterns/` 里选择一个范式。
3. 只读这个范式的 `PATTERN.md`。
4. 需要时再读它的参考图、adapter、反例或案例。
5. 写出本次任务的 visual score。
6. 按目标 runtime 编译成 prompt / shader spec / layout spec。

## 当前稳定范式

| Pattern | 状态 | 不变量 |
| --- | --- | --- |
| `big-character-poster` | canonical | 大标题、公共态度、具体证据、粗粝印刷感、强第一眼。 |

候选范式可以留在 `patterns/` 里作为 seed。只有拥有参考图、边界和至少一个
有用生产案例后，才进入 canonical 状态。

当前 seed：

| Pattern | 不变量 |
| --- | --- |
| `eastern-texture-handdrawn` | 宣纸肌理、松弛手绘线条、低饱和、隐喻和留白。 |
| `pixel-retro` | 像素块、复古游戏逻辑、清晰轮廓、极客工具气质。 |
| `narrative-journal-infographic` | 手绘时间线、对比、流程、注释、可读结构。 |
| `whimsical-journal-sketch` | 水彩速写、马克笔、拼贴、轻松温暖。 |
| `flowing-gaze-minimal-cover` | 单一主体、负空间、独特视角、钢笔/蚀刻质感。 |
| `minimal-handdrawn-linework` | 干净线稿、克制反差、低饱和、高级克制。 |

## Evals / 评测

用 `docs/evaluation-protocol.md` 和 `evals/` 测试一个 pattern 能否跨
主题稳定复现。

Evals 不是图片排行榜，也不是通用模型能力测试。它测试的是视觉方法是否有
稳定不变量，另一个 agent 能否不靠私有上下文复用，以及三张候选图是否是
同一语法下的三种结构解法。

生成候选图和 runtime prompt 留在调用方项目的工作目录。只有经过复盘的
稳定经验，才回流到本仓库，成为 anti-pattern、adapter 或 pattern 内案例。

## 什么应该进入这个仓库

- 稳定视觉范式；
- 能说明范式的参考图；
- 反例和失败模式；
- runtime adapter 和编译规则；
- 能讲清楚方法的 pattern 内案例；
- 能测试方法稳定性的评测用例和判断标准。

## 什么不应该进入这个仓库

- 一次性生产 prompt；
- API 诊断日志；
- 没有分析的失败图；
- 私有品牌材料；
- 带密钥、账号、客户数据或内部信息的截图；
- 一次性、未验证的词表；
- 通用图片模型跑分套件。

一次性的生产过程应该留在调用方项目的 `_work/` 里，而不是进入这个语法仓库。
