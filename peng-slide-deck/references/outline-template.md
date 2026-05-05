# 大纲模板

> 在 Step 3（生成大纲）时使用。大纲是连接内容分析和 HTML 生成的桥梁。
> **CSS_STYLE_INSTRUCTIONS 是样式唯一真相源**——生成 HTML 时，从此块提取 `:root` 块注入 template.html。

---

## 模板

```markdown
# Slide Deck Outline

**Topic**: {主题名}
**Style**: {预设名 或 "custom: texture+mood+typography+density"}
**Dimensions**: {texture} + {mood} + {typography} + {density}
**Theme**: {ink / indigo / forest / kraft / dune}
**Audience**: {beginners / intermediate / experts / executives / general}
**Language**: {zh / en / ja / ...}
**Slide Count**: {N} slides
**Generated**: {YYYY-MM-DD HH:mm}

---

<CSS_STYLE_INSTRUCTIONS>
{完整的 :root CSS 变量块}
</CSS_STYLE_INSTRUCTIONS>

---

## 幻灯片页表

| # | 标题 | 类型 | 布局 | 主题 |
|---|------|------|------|------|
| 01 | {封面标题} | Cover | title-hero | hero dark |
| 02 | {内容标题} | Content | {布局名} | light |
| ... | ... | ... | ... | ... |
| {N} | {封底标题} | Back Cover | {布局名} | hero dark |

---

## Slide 1 of {N}
**Type**: Cover
**Layout**: title-hero

{页面详细说明：标题文案、副标题、特殊元素、动画配方}

---

## Slide 2 of {N}
**Type**: Content
**Layout**: {布局名}

{页面详细说明}

---

（...后续页面...）

---

## Slide {N} of {N}
**Type**: Back Cover
**Layout**: {布局名}

{封底详细说明}
```

---

## CSS_STYLE_INSTRUCTIONS 规范

### 构建流程

1. **确定风格来源**：预设 → 读取 `references/themes/{preset}.md`；自定义维度 → 合并 `references/dimensions/` 中的 4 个文件
2. **提取 `:root` 块**：从风格规范文件中提取完整的 CSS 变量声明
3. **合并主题色**：将用户选择的主题色变量（`--ink`、`--paper` 等）插入 `:root` 块
4. **写入大纲**：完整 `:root { ... }` 块放置在 `<CSS_STYLE_INSTRUCTIONS>` 和 `</CSS_STYLE_INSTRUCTIONS>` 标记之间

### 变量分块结构

`:root` 块按以下顺序组织，每块有明确的注释标题：

```css
:root{
  /* ============================================================
     ============ 主题色（{主题名}） ============
     ============================================================ */
  --ink: ...;
  --ink-rgb: ...;
  --paper: ...;
  --paper-rgb: ...;
  --paper-tint: ...;
  --ink-tint: ...;

  /* ============================================================
     ============ 风格变量（{预设名 或 custom}） ============
     ============================================================ */

  /* --- Texture: {texture} --- */
  --bg-texture: ...;
  --bg-overlay: ...;
  --texture-opacity: ...;
  --border-radius: ...;

  /* --- Mood: {mood} --- */
  --palette-bg: ...;
  --palette-bg-rgb: ...;
  --palette-text: ...;
  --palette-text-rgb: ...;
  --palette-text-secondary: ...;
  --palette-accent-1: ...;
  --palette-accent-1-rgb: ...;
  --palette-accent-2: ...;
  --palette-accent-2-rgb: ...;
  --palette-accent-3: ...;
  --palette-accent-3-rgb: ...;
  --palette-warning: ...;

  /* --- Typography: {typography} --- */
  --font-headline-en: ...;
  --font-headline-zh: ...;
  --font-body-en: ...;
  --font-body-zh: ...;
  --font-mono: ...;
  --font-display: ...;
  --font-handwritten: ...;
  --headline-weight: ...;
  --headline-style: ...;
  --headline-letter-spacing: ...;
  --body-letter-spacing: ...;

  /* --- Density: {density} --- */
  --slide-padding: ...;
  --content-gap: ...;
  --headline-hero-size: ...;
  --headline-xl-size: ...;
  --headline-md-size: ...;
  --subheadline-size: ...;
  --body-size: ...;
  --lead-size: ...;
  --margin-content: ...;
  --grid-gap-h: ...;
  --grid-gap-v: ...;
  --stat-nb-size: ...;
  --stat-label-size: ...;
}
```

### 主题色变量参考（5 套预设）

#### 墨水经典 (ink)

```css
--ink:#0a0a0b;
--ink-rgb:10,10,11;
--paper:#f1efea;
--paper-rgb:241,239,234;
--paper-tint:#e8e5de;
--ink-tint:#18181a;
```

#### 靛蓝瓷 (indigo)

```css
--ink:#0f172a;
--ink-rgb:15,23,42;
--paper:#f0f4fa;
--paper-rgb:240,244,250;
--paper-tint:#e2e8f0;
--ink-tint:#1e293b;
```

#### 森林墨 (forest)

```css
--ink:#1a2e1a;
--ink-rgb:26,46,26;
--paper:#f4f8f2;
--paper-rgb:244,248,242;
--paper-tint:#e6f0e4;
--ink-tint:#2a3e2a;
```

#### 牛皮纸 (kraft)

```css
--ink:#3d2b1f;
--ink-rgb:61,43,31;
--paper:#faf3e6;
--paper-rgb:250,243,230;
--paper-tint:#efe4d2;
--ink-tint:#4d3b2f;
```

#### 沙丘 (dune)

```css
--ink:#2d2a25;
--ink-rgb:45,42,37;
--paper:#faf8f3;
--paper-rgb:250,248,243;
--paper-tint:#ede9e2;
--ink-tint:#3d3a35;
```

---

## 幻灯片条目模板

每张幻灯片的大纲条目需包含以下信息块：

### Cover 类型

```markdown
## Slide 01 of {N}
**Type**: Cover
**Layout**: title-hero
**Theme**: hero dark
**Animation**: hero

- **Kicker**: {上方小标签，英文全大写，如 "PRODUCT STRATEGY"}
- **Headline**: {中文主标题，≤ 15 字}
- **Headline EN**: {英文副标题，如 "Redefining Collaboration"}
- **Subtitle**: {一句话副标题，≤ 30 字}
- **Speaker**: {演讲者姓名 / 角色 / 日期}
- **Chrome Left**: {机构名 / 日期}
- **Chrome Right**: {01 / N}
- **Foot Title**: {幻灯片简称}

**视觉策略**：
- 使用 `.hero.dark`，WebGL 深色背景大幅透出
- 标题居中，层级从 kicker → h-hero → h-hero-en → sub
```

### Content 类型

```markdown
## Slide 02 of {N}
**Type**: Content
**Layout**: split-screen（.grid-2-7-5）
**Theme**: light
**Animation**: directional

- **Headline**: {内容页标题，≤ 12 字}
- **Body**: {正文内容要点}
  - 要点 1（≤ 20 字）
  - 要点 2（≤ 20 字）
- **Callout**: {引语或 insight}
  - Quote: "{引语内容}"
  - Source: "— {来源}"
- **Image**: images/{页码}-{语义}.jpg
  - Ratio: 3x4
  - Caption: {图注标题}
- **Chrome Left**: {章节名}
- **Foot Title**: {短标题}

**视觉策略**：
- 左侧文字 + 右侧竖图
- 使用 directional 动画：文字 left → 图片 right
- callout 强化核心 insight
```

### Back Cover 类型

```markdown
## Slide {N} of {N}
**Type**: Back Cover
**Layout**: title-hero（变体）
**Theme**: hero dark
**Animation**: hero

- **Headline**: {封底标题，精选一句核心信息或 CTA}
- **Subtitle**: {一句话收尾，如 "让我们一起构建未来"}
- **CTA**: {具体行动号召，如 "今天注册获 30 天免费使用"}
- **Contact**: {可选：联系方式/二维码/网址}
- **Foot**: {N} / {N}

**视觉策略**：
- 主题色与封面不同（封面 dark → 封底 light 或反之）
- 更大的留白、更少的文字
- 不使用 "谢谢"/"Thank you"/"Q&A" 作为封底标题
- CTA 要具体可操作
```

---

## 大纲生成规则

### 页数算法

```
总页数 = 封面(1) + 目录(0-1) + Σ(每支撑点的页数) + 章节分隔(N) + 封底(1)
```

其中：
- 每个支撑点分配 2-5 页（根据内容复杂度）
- 每个支撑点之间插入一个章���分隔页（如果 > 10 页）
- 目录页可选（≥ 12 页时推荐添加）

### 主题交替算法

```
设 pages = [slide_1, slide_2, ..., slide_N]

对于第 i 页：
  如果是 Cover:    theme = hero dark
  如果是 Chapter:  theme = (上一章分隔页是 hero.dark ? hero.light : hero.dark)
  如果是 Content:  theme = (上一页是 dark && 非 hero ? light : 根据节奏规则)
  如果是 Back:     theme = hero dark（或与封面不同）

节奏约束检查：
  - 连续 3 页同 theme → 将第 3 页翻转
  - ≥ 8 页时 → 确保至少 1 个 hero dark + 1 个 hero light
```

### 布局分配算法

对视觉机会映射表（`analysis.md` 中产出）的每个条目：

1. 匹配**内容类型** → **首选布局**（参见 `layouts.md` 布局决策矩阵）
2. 检查前后页面布局，确保不连续 3 页使用相同布局
3. 如果冲突：降级到备选布局
4. 如果仍冲突：使用 `text-with-figure` 作为通用 fallback

---

## 完整示例（精简版）

```markdown
# Slide Deck Outline

**Topic**: 边缘计算平台架构设计
**Style**: blueprint
**Dimensions**: grid + cool + technical + balanced
**Theme**: indigo
**Audience**: experts
**Language**: zh
**Slide Count**: 12 slides
**Generated**: 2026-05-05 14:30

---

<CSS_STYLE_INSTRUCTIONS>
:root{
  /* ============ 主题色（靛蓝瓷） ============ */
  --ink:#0f172a;
  --ink-rgb:15,23,42;
  --paper:#f0f4fa;
  --paper-rgb:240,244,250;
  --paper-tint:#e2e8f0;
  --ink-tint:#1e293b;

  /* --- Texture: grid --- */
  --bg-texture:none;
  --bg-overlay:url("data:image/svg+xml,...");
  --texture-opacity:0.5;
  --border-radius:2px;

  /* --- Mood: cool --- */
  --palette-bg:#FAF8F5;
  --palette-bg-rgb:250,248,245;
  --palette-text:#334155;
  --palette-text-rgb:51,65,85;
  --palette-text-secondary:#64748B;
  --palette-accent-1:#2563EB;
  --palette-accent-1-rgb:37,99,235;
  --palette-accent-2:#1E3A5F;
  --palette-accent-2-rgb:30,58,95;
  --palette-accent-3:#BFDBFE;
  --palette-accent-3-rgb:191,219,254;
  --palette-warning:#F59E0B;

  /* --- Typography: technical --- */
  --font-headline-en:'Inter', 'Helvetica Neue', sans-serif;
  --font-headline-zh:'Noto Serif SC', source-han-serif-sc, serif;
  --font-body-en:'Inter', 'Helvetica Neue', sans-serif;
  --font-body-zh:'Noto Sans SC', source-han-sans-sc, sans-serif;
  --font-mono:'JetBrains Mono', 'IBM Plex Mono', ui-monospace, monospace;
  --font-display:'Playfair Display', Georgia, serif;
  --font-handwritten:'Caveat', 'Klee One', cursive;
  --headline-weight:700;
  --headline-style:normal;
  --headline-letter-spacing:-0.02em;
  --body-letter-spacing:0.01em;

  /* --- Density: balanced --- */
  --slide-padding:6vh 6vw 10vh 6vw;
  --content-gap:2.4vh;
  --headline-hero-size:10vw;
  --headline-xl-size:6.2vw;
  --headline-md-size:2.3vw;
  --subheadline-size:3.1vw;
  --body-size:max(15px, 1.22vw);
  --lead-size:1.75vw;
  --margin-content:10%;
  --grid-gap-h:3vw;
  --grid-gap-v:4vh;
  --stat-nb-size:5.8vw;
  --stat-label-size:max(10px, 0.78vw);
}
</CSS_STYLE_INSTRUCTIONS>

---

## 幻灯片页表

| # | 标题 | 类型 | 布局 | 主题 |
|---|------|------|------|------|
| 01 | 边缘计算：重新定义数据处理范式 | Cover | title-hero | hero dark |
| 02 | 为什么需要边缘计算 | Content | hero-question | hero dark |
| 03 | 核心架构：云-边-端协同 | Content | split-screen | light |
| 04 | 关键性能指标 | Content | stat-grid | light |
| 05 | 数据处理流水线 | Content | pipeline | light |
| 06 | 行业实践 | Content | section-divider | hero light |
| 07 | 智能制造场景 | Content | text-with-figure | light |
| 08 | 自动驾驶场景 | Content | image-grid | light |
| 09 | 部署架构对比 | Content | binary-comparison | light |
| 10 | 安全与合规 | Content | three-columns | light |
| 11 | 未来展望 | Content | big-quote | hero dark |
| 12 | 开启边缘智能新纪元 | Back Cover | title-hero | hero light |

---

## Slide 01 of 12
**Type**: Cover
**Layout**: title-hero
**Theme**: hero dark
**Animation**: hero

- **Kicker**: EDGE COMPUTING
- **Headline**: 边缘计算：重新定义数据处理范式
- **Headline EN**: Redefining Data Processing at the Edge
- **Subtitle**: 从中心到边缘，从延迟到实时，从单点到协同
- **Speaker**: 张三 / 首席架构师 / 2026.05
- **Chrome Left**: TechSummit 2026 / 05.05
- **Chrome Right**: 01 / 12
- **Foot Title**: 边缘计算架构设计

---

（...中间页面省略...）

---

## Slide 12 of 12
**Type**: Back Cover
**Layout**: title-hero（变体）
**Theme**: hero light
**Animation**: hero

- **Headline**: 开启边缘智能新纪元
- **CTA**: 下载完整白皮书：edge-platform.io/whitepaper
- **Contact**: 联系架构团队：arch@company.com
- **Foot**: 12 / 12

**视觉策略**：
- 封面是 hero dark → 封底用 hero light 形成视觉闭环
- 大字标题 + 具体 CTA，不止是"谢谢"
```

---

## 与 baoyu-slide-deck 大纲的差异

| 方面 | baoyu-slide-deck | peng-slide-deck |
|------|-----------------|-----------------|
| 样式描述方式 | `STYLE_INSTRUCTIONS`（自然语言提示词描述） | `CSS_STYLE_INSTRUCTIONS`（CSS `:root` 变量块） |
| 布局字段 | 布局描述（如"左文右图"） | 具体布局名（如 `split-screen` / `.grid-2-7-5`） |
| 视觉策略 | 图像风格提示词 | CSS 策略（动画配方、主题选择） |
| 图片信息 | 每页图片的生成提示词 | 图片引用路径 + 比例 + 标题 |
| 字体信息 | 字体风格描述 | Google Fonts 引用 + CSS `--font-*` 变量 |
| 像素/SVG 信息 | 像素比、SVG 内嵌规则 | 固定高度类 + 宽高比类 |
| 证据保留 | prompts/ 文件夹（真相源） | `CSS_STYLE_INSTRUCTIONS` 块（样式真相源） |

---

## 格式规范

1. **`CSS_STYLE_INSTRUCTIONS` 块必须是有效的 CSS** — 提取后可以直接插入 `<style>` 标签而不报语法错误
2. **所有路径使用相对路径** — 图片路径为 `images/{页码}-{语义}.{ext}`
3. **页号始终两位数字** — `01` 而非 `1`
4. **标题不超过 15 字** — 超过需拆分到副标题
5. **副标题不超过 30 字** — 超过需拆分到正文
6. **正文每段不超过 80 字** — 超过需拆分到多页
7. **kicker 始终保持英文全大写** — 如 `PRODUCT STRATEGY`、`KEY FINDINGS`
8. **封底不得为"谢谢"/"Thank you"/"Q&A"** — 必须有实质性内容
