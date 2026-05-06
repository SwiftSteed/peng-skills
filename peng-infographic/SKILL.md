---
name: peng-infographic
description: 基于 HTML+CSS 的信息图生成器。保留 baoyu-infographic 的 20+ 布局 × 21 风格系统，用纯 HTML/CSS 替代生图。输出为单文件 HTML，适用于高密度信息可视化、数据报告、知识总结等场景。当用户需要"信息图"、"infographic"、"可视化"、"数据图"时使用。
version: 0.1.0
---

# HTML Infographic Generator

将结构化内容转化为**单文件 HTML** 信息图。核心设计：

- **高密度信息可视化** — 忠实保留源数据，不概括不改写
- **20+ 布局 × 21 风格** — 布局决定信息结构，风格决定视觉美学，自由组合
- **纯 HTML+CSS 实现** — 无需生图，浏览器打开即可预览和使用
- **多比例支持** — landscape (16:9)、portrait (9:16)、square (1:1) 及自定义

## 与 baoyu-infographic 的关系

| 维度 | baoyu-infographic | peng-infographic |
|------|------------------|------------------|
| 输出 | 单张 PNG | 单文件 HTML |
| 布局 | 20+ 种 → 提示词描述 | 20+ 种 → CSS 布局 |
| 风格 | 21 种 → 视觉提示词 | 21 种 → CSS 变量 |
| 内容 | 结构化 → 嵌入提示词 | 结构化 → 嵌入 HTML |
| 使用 | 插图/分享 | 浏览器预览 → 截图/导出/嵌入 |

## 语言

用中文回应用户，技术标记保留英文。

## 选项

| 选项 | 描述 |
|------|------|
| `--layout <name>` | 布局类型（20+ 选 1） |
| `--style <name>` | 视觉风格（21 选 1） |
| `--aspect <ratio>` | 比例：landscape / portrait / square / 自定义 W:H |
| `--lang <code>` | 输出语言（en, zh, ja 等） |

## 布局 (20+)

### 流程 & 时间

| 布局 | 用途 | CSS 实现 |
|------|------|----------|
| `linear-progression` | 时间线、流程、教程步骤 | 竖排/横排步骤条 + 连接线 |
| `circular-flow` | 循环、重复流程 | 环形排列 + 箭头 |
| `winding-roadmap` | 旅程、里程碑 | 曲线路径 + 锚点 |
| `funnel` | 转化、过滤 | 逐级缩窄的层叠块 |
| `bridge` | 问题 → 解决 | 左右两岛 + 桥接元素 |

### 对比 & 分析

| 布局 | 用途 | CSS 实现 |
|------|------|----------|
| `binary-comparison` | A vs B、前后对比 | 双栏 + 中线分隔 |
| `comparison-matrix` | 多因素对比 | 响应式表格 |
| `venn-diagram` | 重叠概念 | 重叠圆形 + 标签 |
| `iceberg` | 表面 vs 深层 | 上下分割 + 水位线 |

### 结构 & 分类

| 布局 | 用途 | CSS 实现 |
|------|------|----------|
| `hierarchical-layers` | 金字塔、优先级 | 垂直层叠块 |
| `tree-branching` | 分类、层级 | 缩进树形结构 |
| `hub-spoke` | 中心概念 + 分支 | 中心节点 + 放射分支 |
| `structural-breakdown` | 分解图、剖面 | 模块堆叠 + 标注线 |
| `periodic-table` | 分类集合 | 多行多列网格 |
| `dense-modules` | 高密度信息模块 | 紧凑多列网格 |

### 叙事 & 概览

| 布局 | 用途 | CSS 实现 |
|------|------|----------|
| `bento-grid`（默认） | 多主题概览 | 不等大网格卡片 |
| `dashboard` | 指标、KPI | 数字卡片 + 图表槽位 |
| `comic-strip` | 叙事、序列 | 顺序排列面板 |
| `story-mountain` | 情节结构、张力曲线 | 上升-峰值-下降布局 |

## 风格 (21)

| 风格 | 描述 | CSS 特征 |
|------|------|----------|
| `craft-handmade`（默认） | 手绘纸艺 | 暖色、不规则边框、手写字体 |
| `claymation` | 3D 粘土 | 圆角、柔和阴影、高饱和色 |
| `kawaii` | 日系可爱 | 粉彩、圆润边角、小装饰 |
| `storybook-watercolor` | 水彩绘本 | 柔和渐变、晕染色块 |
| `chalkboard` | 黑板粉笔 | 深色底、粉笔色字、粗犷线条 |
| `cyberpunk-neon` | 赛博朋克 | 霓虹发光、深色底、荧光色 |
| `bold-graphic` | 漫画风 | 粗边框、网点纹理、强对比 |
| `aged-academia` | 复古学术 | 暖黄底、衬线字、旧纸张纹理 |
| `corporate-memphis` | 孟菲斯扁平 | 纯色块、几何装饰、活力配色 |
| `technical-schematic` | 工程蓝图 | 蓝底白线、坐标标记、等宽字体 |
| `origami` | 折纸几何 | 纯色三角面、折叠阴影 |
| `pixel-art` | 像素 8-bit | 块状背景、粗像素边框 |
| `ui-wireframe` | 线框图 | 灰度、虚线边框、标注箭头 |
| `subway-map` | 地铁图 | 彩线交叉、圆点站点 |
| `ikea-manual` | 宜家说明 | 极简线条、无衬线、黑白为主 |
| `knolling` | 平铺整理 | 直角排列、等距分布 |
| `lego-brick` | 乐高积木 | 凸点装饰、纯色块、粗圆角 |
| `pop-laboratory` | 流行实验室 | 蓝网格底、坐标标记、标签气泡 |
| `morandi-journal` | 莫兰迪手帐 | 低饱和暖色、手绘涂鸦、线装边距 |
| `retro-pop-grid` | 70s 复古波普 | 瑞士网格、粗边框、撞色 |
| `hand-drawn-edu` | 手绘教育 | 马卡龙色、晃动线条、火柴人 |

### 推荐组合

| 内容类型 | 推荐 Layout + Style |
|----------|-------------------|
| 时间线/历史 | `linear-progression` + `craft-handmade` |
| 步骤教程 | `linear-progression` + `ikea-manual` |
| A vs B 对比 | `binary-comparison` + `corporate-memphis` |
| 层级/优先级 | `hierarchical-layers` + `craft-handmade` |
| 概念重叠 | `venn-diagram` + `hand-drawn-edu` |
| 转化漏斗 | `funnel` + `corporate-memphis` |
| 循环流程 | `circular-flow` + `craft-handmade` |
| 技术拆解 | `structural-breakdown` + `technical-schematic` |
| 数据指标 | `dashboard` + `corporate-memphis` |
| 教育科普 | `bento-grid` + `chalkboard` |
| 旅程/里程碑 | `winding-roadmap` + `storybook-watercolor` |
| 分类集合 | `periodic-table` + `bold-graphic` |
| 高密度指南 | `dense-modules` + `morandi-journal` |
| 技术指南 | `dense-modules` + `pop-laboratory` |
| 教育图解 | `hub-spoke` + `hand-drawn-edu` |

## 内容规则

- **忠实保留源数据** — 不概括、不改写、不改述
- **去除敏感信息** — 移除凭据、API 密钥、令牌
- **定义学习目标** — 组织内容前明确输出要传达什么

## 文件布局

```
infographic/{topic-slug}/
├── source-{slug}.{ext}
├── analysis.md
├── structured-content.md
└── index.html
```

## 工作流

```
- [ ] Step 1: Setup & 分析
- [ ] Step 2: 结构化内容
- [ ] Step 3: 推荐组合
- [ ] Step 4: 确认 ⚠️ 必需
- [ ] Step 5: 生成 HTML 信息图
- [ ] Step 6: 审查（条件性）
- [ ] Step 7: 预览与交付
```

### Step 1: Setup & 分析

加载 EXTEND.md，分析内容类型、数据结构、复杂度、受众。

### Step 2: 结构化内容

将内容转化为信息图结构：标题 + 学习目标 + 分区（关键概念、内容、视觉元素、标签）+ 数据点（精确复制）。

### Step 3: 推荐组合

根据数据结构推荐 3-5 种 layout×style 组合。

### Step 4: 确认 ⚠️ 必需

展示推荐组合、aspect、语言。确认后进入生成。

### Step 5: 生成 HTML 信息图

1. 从 `assets/template.html` 拷贝模板
2. 替换 `:root` 风格变量 + 布局 CSS
3. 嵌入结构化内容
4. 应用风格对应的装饰和字体

> [!IMPORTANT]
> **编码安全**：必须使用 `Write` 工具直接写入 `index.html`。

### Step 6: 审查（条件性）

展示信息图效果，询问确认或调整。

### Step 7: 预览与交付

```bash
open "infographic/{topic-slug}/index.html"
```

## 使用场景

- 浏览器打开 → 截图 → 社交媒体、文章插图
- 导出 PDF → 印刷、报告附件
- 嵌入网页 → iframe 或复制 HTML 到文章
- 打印 → 办公室/教室海报

## 字体策略

与 peng-slide-deck 相同：Google Fonts → 系统字体 → 通用族名。无版权风险。
