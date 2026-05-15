# Open Visual Grammar / 开放视觉语法

Open Visual Grammar 是一套把视觉直觉翻译成可执行生成结果的方法。

它不是 prompt 库。Prompt 只是某个 runtime 的编译结果。真正值得沉淀的资产，是视觉语法：一个视觉意图如何变成张力、构图、密度、隐喻和执行约束。

## 为什么需要它

AIGC 让生产图片、PPT、网页、视频、shader 变得便宜。

但它没有让视觉判断变便宜。

很多失败的生成，问题都出在同一个地方：还没说清楚视觉问题，就先开始要风格。

Open Visual Grammar 的顺序更靠前：

1. 观众第一眼应该理解什么？
2. 画面里的张力是什么？
3. 信息密度应该多高？
4. 隐喻应该离主题多远？
5. 最后由哪个 runtime 执行？

## 核心概念

| 概念 | 含义 |
| --- | --- |
| Grammar / 语法 | 跨 pattern 的底层视觉语言：张力、层级、密度、隐喻、节奏、温度。 |
| Pattern / 范式 | 可复用视觉范式，内部持有边界、参考图、adapter 和案例。 |
| Canonical / 正典状态 | 一个 pattern 的成熟度状态，不作为顶层目录。 |
| Score / 谱面 | 单次任务的视觉计划，可以编译成 prompt、shader spec、deck layout 或 scene brief。 |
| Runtime / 执行器 | 生成落地的媒介：图像模型、HTML/CSS、PPT、shader、视频、游戏引擎。 |

## 仓库结构

```text
grammar/     跨 pattern 的视觉语法。只有具体决策需要时再读。
patterns/    稳定视觉范式。一次只加载一个。
runtimes/    跨 pattern 的执行约束。
evals/       可复用评测用例和判断标准。
docs/        协议和操作说明。
decisions/   架构说明和项目决策记录。
```

案例跟随对应 pattern 存放。一次性生产 prompt 不进入这个仓库。

## Agent 使用原则

渐进披露，不要一次把所有上下文塞进去：

1. 读 `AGENTS.md`。
2. 从 `patterns/` 里选择一个范式。
3. 只读这个范式的 `PATTERN.md`。
4. 需要时再读它的参考图、adapter、反例或案例。
5. 写出本次任务的 visual score。
6. 按目标 runtime 编译成 prompt / shader spec / layout spec。

## 当前稳定范式

| Pattern | 适用场景 |
| --- | --- |
| `conflict-poster` | 信息流封面需要一个强冲突和清晰第一眼。 |
| `documentation-hero` | 公共文档或教程需要可信、清楚、长期可用。 |

候选范式先留在内部孵化区。只有拥有参考图、边界和至少一个有用生产案例后，才进入公开仓库。

## Evals / 评测

用 `docs/evaluation-protocol.md` 和 `evals/` 测试一个 pattern 是否能在真实生成中保持稳定。

Evals 不是图片排行榜。它是一组固定场景，用来检查第一眼、视觉张力、反 AI 模板能力、pattern 迁移能力，以及真实 operator 能否从三张有策略差异的候选图里做判断。

生成候选图和 runtime prompt 留在调用方项目的工作目录。只有经过复盘的稳定经验，才回流到本仓库，成为 anti-pattern、adapter 或 pattern 内案例。

## 什么应该进入这个仓库

- 稳定视觉范式；
- 能说明范式的参考图；
- 反例和失败模式；
- runtime adapter 和编译规则；
- 能讲清楚方法的 pattern 内案例。
- 能测试语法的评测用例和判断标准。

## 什么不应该进入这个仓库

- 一次性生产 prompt；
- API 诊断日志；
- 没有分析的失败图；
- 私有品牌材料；
- 带密钥、账号、客户数据或内部信息的截图；
- 未验证的风格词表。

一次性的生产过程应该留在调用方项目的 `_work/` 里，而不是进入这个语法仓库。
