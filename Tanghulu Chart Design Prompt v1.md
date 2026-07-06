# Tanghulu Chart（糖胡芦图） Design Prompt

## Project Goal | 项目目标

Design and implement a brand-new financial chart called:

设计并实现一种全新的金融图表：

**Tanghulu Chart（糖胡芦图）**

The goal is to create a new visualization language that integrates price information and volume distribution into a single chart element.

目标是在单个图形元素中同时表达价格信息与成交量分布信息，探索一种新的金融可视化语言。

---

## Core Problem | 核心问题

Traditional candlestick charts only describe:

传统K线图只能表达：

* Open
* High
* Low
* Close

However, they cannot show:

但无法表达：

* Where trading activity actually occurred
* How volume was distributed across prices
* The dominant transaction price
* The primary value area
* 市场真正在哪里成交
* 成交量在价格区间中的分布
* 主要成交价格
* 主要价值区域

Two candles may have identical OHLC values while representing completely different market structures.

两根OHLC完全相同的K线，可能对应完全不同的市场成交结构。

---

## Fundamental Concept | 基本理念

Price alone is incomplete.

仅有价格是不完整的。

A chart should show:

图表不仅要表达：

* where price traveled

价格到过哪里

but also:

还要表达：

* where trading activity occurred

市场真正在哪里成交

The Tanghulu Chart attempts to encode volume distribution directly into the chart itself.

糖胡芦图尝试将成交量分布直接编码进图形本身。

---

## Important Constraint | 重要约束

The Tanghulu Chart is a **2D chart**.

糖胡芦图是一个二维图表。

It is NOT:

它不是：

* 3D chart
* 3D surface
* Mountain chart
* Volume landscape
* Volume terrain
* 三维图表
* 三维曲面
* 三维山峰图
* 地形图
* 体渲染图

The chart must remain within a standard financial chart coordinate system:

必须保持标准金融图表坐标体系：

X-axis = Time

Y-axis = Price

成交量分布必须编码在图形内部，而不是引入第三个维度。

Volume distribution must be encoded inside the chart element rather than using a third dimension.

---

## Data Model | 数据模型

Each trading session contains:

每个交易日包含：

* Date
* Open
* High
* Low
* Close
* Total Volume

In addition, volume must be distributed across multiple price levels.

同时需要构建价格区间内多个价格层对应的成交量分布。

The implementation may use:

实现阶段可以使用：

* Gaussian distribution
* Multi-modal distribution
* Skewed distribution

for simulation.

进行模拟。

The architecture should allow future replacement with real tick-by-tick trade data.

架构上应支持未来接入真实逐笔成交数据。

---

## Information That Must Be Visible | 必须表达的信息

For every trading session, users should be able to identify:

对于每个交易日，用户应能够识别：

1. Open
2. Close
3. High
4. Low
5. Volume Distribution
6. POC (Point Of Control)
7. Value Area

without reading numerical values.

尽量通过图形直接识别，而不依赖数值标签。

---

## Volume Distribution | 成交量分布

The most important innovation.

这是整个设计最重要的部分。

Different price levels should carry different visual weights according to traded volume.

不同价格层应根据成交量拥有不同视觉权重。

Higher volume regions should appear visually stronger.

成交量大的价格区域应更突出。

Lower volume regions should appear visually weaker.

成交量小的价格区域应弱化。

The exact visual encoding is open to exploration.

具体采用什么视觉编码方式由设计者自由探索。

---

## POC

Point Of Control

Definition:

The price level with the highest traded volume.

定义：

成交量最大的价格。

The chart must make the POC easy to locate.

图形必须让用户能够快速识别POC位置。

How to visualize it is intentionally left open.

具体视觉表现方式不做限制。

---

## Value Area

Definition:

The price range containing approximately 70% of total volume.

定义：

累计约70%成交量所在价格区间。

The chart must make this area identifiable.

图形必须能够体现这一价格区域。

Implementation details are open.

具体实现方式不做限制。

---

## Time Series Behavior | 时间序列行为

Display approximately 30 trading sessions.

展示约30个交易日。

Arrange them chronologically from left to right.

按时间顺序从左到右排列。

The chart should allow users to observe:

用户应能够观察：

* Trend changes
* Volume migration
* POC migration
* Value Area migration
* Structural changes in market participation
* 趋势变化
* 成交重心变化
* POC迁移
* Value Area迁移
* 市场结构变化

---

## Design Freedom | 设计自由度

Do NOT simply recreate a traditional candlestick chart.

不要简单复制传统K线。

The purpose of this project is to explore a new visual language.

目标是探索新的图形语言。

Feel free to experiment with:

鼓励探索：

* Shape
* Geometry
* Contours
* Density encoding
* Line structures
* Area structures
* Hybrid visual representations
* 新形状
* 新几何结构
* 新轮廓表达
* 密度表达
* 线结构
* 面结构
* 混合视觉编码

Any solution is acceptable if it communicates market structure more effectively than a traditional candlestick.

只要能够比传统K线更有效表达市场结构即可。

---

## Technical Requirements | 技术要求

Use:

使用：

* HTML
* CSS
* JavaScript

Implement directly in the browser.

直接在浏览器中运行。

Do not rely on specialized financial chart libraries.

不要依赖专业金融图表库。

Keep the architecture extensible.

代码结构应具备良好的扩展性。

---

## Deliverables | 输出内容

Provide:

请输出：

1. Complete runnable HTML source code，include chinese and english
2. Design explanation
3. Interpretation guide
4. Comparison with traditional candlesticks
5. Future extension ideas
6. 完整可运行HTML源码，同时包含中文和英文
7. 图表设计说明
8. 读图说明
9. 与传统K线对比分析
10. 后续扩展方向

The objective is to build a genuine prototype of the Tanghulu Chart rather than another variation of the traditional candlestick chart.

目标是构建糖胡芦图（Tanghulu Chart）的原型，而不是传统K线图的简单变种。
