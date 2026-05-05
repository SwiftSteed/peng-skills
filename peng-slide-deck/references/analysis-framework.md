# 内容分析框架

> 在 Step 1 的 Setup & 分析阶段使用。对源内容进行结构化分析，
> 支撑风格推荐、页数估算和大纲生成。分析结果写入 `analysis.md`。

---

## 1. 消息层次

从源内容中提取三层消息结构：

### 核心消息 (Core Message)

> 如果受众只记住一件事，应该是什么？

- 提炼为一句话（≤ 15 字）
- 这句话将用于封面的主标题
- 必须具体：不是"关于我们的产品"，而是"产品使处理速度提升 10 倍"

### 支撑点 (Supporting Points)

- 3-5 个核心论据/子主题
- 每个支撑点展开为一组幻灯片
- 标记每个点的证据类型（数据 / 案例 / 类比 / 演示）

### 行动号召 (Call-to-Action)

- 受众看完幻灯片后应该做什么？
- 用于封面或封底的核心文案
- 要具体可操作：不是"了解更多"，而是"今天注册获 30 天免费试用"

---

## 2. 受众决策矩阵

分析 5 个维度，调整内容策略：

| 维度 | 问题 | 输出 |
|------|------|------|
| 谁 | 阅读者的角色和背景是什么？ | 角色标签（如：CTO、学生、投资人） |
| 当前认知 | 他们目前对该主题了解什么？ | 起点级别（零基础 / 有了解 / 熟悉） |
| 期望决策 | 阅读后他们需要做什么决定？ | 决策类型（选用 / 投资 / 学习 / 批准） |
| 障碍 | 什么可能阻止他们行动？ | 顾虑列表（成本 / 复杂性 / 风险） |
| 说服证据 | 什么能说服他们？ | 证据类型（数据基准 / 案例研究 / 推荐） |

### 受众内容焦点

| 受众 | 内容重点 | 语言风格 | 适合密度 |
|------|----------|----------|----------|
| `executives`（高管） | 结果、ROI、战略影响 | 直接、简洁、关注业务价值 | minimal |
| `experts`（专家） | 架构、实现、规格、细节 | 精确、技术化、可验证 | dense |
| `general`（通用） | 收益、故事、相关性 | 平实、清晰、避免术语 | balanced |
| `beginners`（初学者） | 逐步、示例、练习 | 友好、鼓励、循序渐进 | balanced |
| `intermediate`（中级） | 深入、对比、最佳实践 | 专业但不晦涩 | balanced |

---

## 3. 视觉机会映射

> **与 baoyu-slide-deck 的差异**：此处映射到 HTML 布局选择，而非图像生成。
> 分析内容类型，推荐对应的 HTML `<section>` 布局。

| 内容类型 | 识别信号 | HTML 布局 | CSS 策略 |
|----------|----------|-----------|----------|
| 比较 | "vs"、"相比"、"对比"、"区别" | `two-columns` / `comparison-matrix` | 并排 flex，`justify-content:space-between` |
| 流程 | "步骤"、"流程"、"阶段"、"然后" | `linear-progression` / `numbered-list` | 编号 + 箭头装饰，`align-items:center` |
| 层次 | "层级"、"组织结构"、"分类" | `hierarchical-layers` / `tree-branching` | 嵌套 indent，连接线 |
| 时间线 | "历史"、"里程碑"、"路线图"、日期序列 | `timeline` / `winding-roadmap` | 垂直时间线，`border-left` 连接 |
| 统计数据 | 百分比、数字对比、指标 | `key-stat` / `dashboard` | 大号数字，`font-size:clamp(4rem,...)` |
| 概念 | 抽象想法、定义、理论 | `quote-callout` / `icon-grid` | Lucide 图标 + 短文字，`gap:2rem` |
| 关系 | 关联、影响、网络 | `hub-spoke` / `venn-diagram` | CSS 定位，SVG 内联 |
| 列表 | 要点罗列、清单 | `bullet-list` / `bento-grid` | `grid` 布局，卡片样式 |
| 故事 | 叙事、案例、场景 | `image-caption` / `split-screen` | 全幅背景，文字叠加层 |
| 议程 | 目录、章节预告 | `agenda` / `numbered-list` | 大号数字，清晰的视觉节奏 |

---

## 4. 展示流程

### 开头（2-3 页）

| 页 | 类型 | 目的 |
|----|------|------|
| 封面 | `title-hero` | 钩子：吸引注意力，传达核心消息 |
| 上下文 | `quote-callout` / `split-screen` | 设定场景：为什么这个问题重要？ |
| 预览 | `agenda` / `icon-grid` | 概览：接下来讲什么？ |

### 主体（核心内容）

选择一种叙事结构：

| 结构 | 模式 | 适合 |
|------|------|------|
| 问题 → 解决方案 | 先定义痛点，再展示如何解决 | 提案、产品发布 |
| What → Why → How | 概念 → 价值 → 实施 | 技术演讲、培训 |
| 过去 → 现在 → 未来 | 时间演进 | 战略、路线图 |
| 简单 → 复杂 | 难度递增 | 教程、入门指南 |
| 案例 → 原理 | 由具体引出抽象 | 研究分享、案例研究 |

### 结尾（2-3 页）

| 页 | 类型 | 目的 |
|----|------|------|
| 综合 | `key-stat` / `quote-callout` | 强化核心消息 |
| 行动号召 | `split-screen` / `title-hero` | 明确下一步 |
| 封底 | `title-hero` | 难忘收尾 —— **不能只是"谢谢"** |

---

## 5. 内容适配：保留/简化/可视化/省略

对源内容的每一段做分类决策：

| 决策 | 标准 | 处理方式 |
|------|------|----------|
| **保留** (Keep) | 核心论点、独特见解、关键数据、行动号召 | 直接体现在大纲中 |
| **简化** (Simplify) | 技术细节超过受众水平、长段落、术语堆砌 | 压缩为 1-2 句要点，或替换为类比 |
| **可视化** (Visualize) | 数据表格、流程描述、结构关系 | 转换为 HTML 布局（图表→key-stat，流程→numbered-list，对比→two-columns） |
| **省略** (Omit) | 过度限定词、重复表述、受众不关心的细节、源内容的元信息 | 从大纲中排除 |

### 可视化触发词

出现以下内容时，必须选择对应的 HTML 布局，不能直接用段落文字：

- 数字/百分比 → `key-stat` 布局（大号数字 + 标签）
- 步骤序列 → `numbered-list` 布局
- 并列比较 → `two-columns` 布局
- 层级分类 → `icon-grid` 或 `hierarchical-layers` 布局
- 时间序列 → `timeline` 布局
- 名言/引用 → `quote-callout` 布局

---

## 6. 分析检查清单

在 `analysis.md` 中必须包含以下内容：

```markdown
## Content Analysis

### Basic Info
- Topic: [主题名称]
- Slug: [topic-slug]
- Source Length: [字数] characters
- Detected Language: [zh / en / ja / etc.]

### Message Hierarchy
- Core Message: [≤ 15 字的核心消息]
- Supporting Points: [3-5 个支撑点]
- Call-to-Action: [具体可操作的 CTA]

### Audience Profile
- Role: [角色]
- Knowledge Level: [起点级别]
- Decision Needed: [决策类型]
- Key Obstacles: [主要障碍]
- Persuasive Evidence: [说服证据]

### Style Signals
- Keywords detected: [关键词列表]
- Recommended Preset: [预设名]
- Reason: [为什么推荐这个预设]
- Alternative Presets: [备选 1], [备选 2]

### Slide Count Estimate
- Recommended: [N] slides
- Confidence: [high / medium / low]
- Reason: [依据内容长度和复杂度]

### Content Decisions
- Keep: [N] sections
- Simplify: [N] sections
- Visualize: [N] sections → [对应布局]
- Omit: [N] sections

### Visual Opportunity Map
| Section | Content Type | Recommended Layout | Rationale |
|---------|--------------|--------------------|-----------|
| ... | ... | ... | ... |
```

---

## 7. 语言检测规则

| 检测条件 | 语言 |
|----------|------|
| 源内容中 > 50% 字符为中文字符范围 | `zh` |
| 源内容中 > 50% 字符为日文假名/汉字混合 | `ja` |
| 其他情况，以英文为主 | `en` |

如果用户在 EXTEND.md 中指定了 `language` 且不为 `auto`，则直接使用指定值，不进行自动检测。
