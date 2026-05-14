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
| Grammar / 语法 | 底层视觉方法：张力、层级、密度、隐喻、节奏、温度。 |
| Canon / 范式 | 稳定视觉模式，有参考图、边界和反例。 |
| Treatment / 处理法 | 选定范式之后的表面处理，改变质感、媒介或完成度，不改变视觉问题。 |
| Score / 谱面 | 单次任务的视觉计划，可以编译成 prompt、shader spec、deck layout 或 scene brief。 |
| Runtime / 执行器 | 生成落地的媒介：图像模型、HTML/CSS、PPT、shader、视频、游戏引擎。 |

## 仓库结构

```text
canon/       稳定视觉范式。一次只加载一个。
treatments/  可选表面处理。必须在选择 canon 之后使用。
methods/     视觉方法短文。只有具体决策需要时再读。
runtimes/    如何把 score 编译到目标媒介。
examples/    完成案例和复盘，不收随机临时 prompt。
```

## Agent 使用原则

渐进披露，不要一次把所有上下文塞进去：

1. 读 `AGENTS.md`。
2. 从 `canon/` 里选择一个范式。
3. 只读这个范式的 `FRAMEWORK.md`。
4. 需要时再读参考图或反例。
5. 写出本次任务的 visual score。
6. 按目标 runtime 编译成 prompt / shader spec / layout spec。

## 什么应该进入这个仓库

- 稳定视觉范式；
- 能说明范式的参考图；
- 反例和失败模式；
- runtime 编译规则；
- 能讲清楚方法的完成案例。

## 什么不应该进入这个仓库

- 一次性生产 prompt；
- API 诊断日志；
- 没有分析的失败图；
- 私有品牌材料；
- 带密钥、账号、客户数据或内部信息的截图。

一次性的生产过程应该留在调用方项目的 `_work/` 里，而不是进入这个语法仓库。
