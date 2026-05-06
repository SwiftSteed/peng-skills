---
name: peng-slide-deck
description: 基于 HTML+CSS 的专业幻灯片生成器。保留 baoyu-slide-deck 的分阶段可审查管线 + 4 维正交风格系统（Texture×Mood×Typography×Density），用纯 HTML/CSS 替代生图。当用户需要"做幻灯片"、"生成 PPT"、"slide deck"、"演示文稿"时使用。
version: 0.1.0
---

# HTML Slide Deck Generator

将内容转化为**单文件 HTML** 的专业幻灯片。核心设计：

- **阅读和分享优先** — 自解释幻灯片、逻辑滚动流畅、适合社交媒体传播
- **4 维正交风格系统** — Texture(5)×Mood(7)×Typography(5)×Density(3)，17 个精调预设
- **纯 HTML+CSS 实现** — 无需生图，直接在浏览器中呈现
- **分阶段可审查管线** — 每一步可回溯、可修改

## 与 baoyu-slide-deck 的关系

本技能是 baoyu-slide-deck 的 HTML+CSS 移植版：

| 维度 | baoyu-slide-deck | peng-slide-deck |
|------|-----------------|-----------------|
| 输出格式 | 逐页 PNG 图片 | 单文件 HTML |
| 风格系统 | 4 维 × 17 预设 → 提示词描述 | 4 维 × 17 预设 → CSS 变量 |
| 生成方式 | 调用图像生成后端 | 直接写入 HTML |
| 工作流 | 9 步（含提示词审查） | 8 步（含 HTML 审查） |
| 合并输出 | PPTX + PDF | HTML（可直接打印为 PDF） |

## 语言

用中文回应用户，技术标记（风格名、文件路径、CSS 类名）保留英文。

## 选项

| 选项 | 描述 |
|------|------|
| `--style <name>` | 预设名（17 选 1）、`custom` 或自定义风格名 |
| `--audience <type>` | beginners / intermediate / experts / executives / general |
| `--lang <code>` | 输出语言（en, zh, ja, ...） |
| `--slides <N>` | 目标页数（8-25 推荐，最大 30） |
| `--outline-only` | 仅生成大纲 |
| `--html-only` | 仅生成 HTML，不进入审查 |
| `--theme <name>` | 主题色预设：ink / indigo / forest / kraft / dune |

## 风格系统

### 4 个维度

| 维度 | 选项 | 在 CSS 中的作用 |
|------|------|----------------|
| **Texture** | clean, grid, organic, pixel, paper | 背景处理（纯色/网格/噪声纹理/像素/纸纹） |
| **Mood** | professional, warm, macaron, cool, vibrant, dark, neutral | 色彩调色（--bg, --text, --accent 系列） |
| **Typography** | geometric, humanist, handwritten, editorial, technical | 字体族（--font-headline, --font-body, --font-mono） |
| **Density** | minimal, balanced, dense | 间距和字号（--slide-padding, --content-gap, --headline-size） |

### 17 个预设

| 预设 | 维度组合 | 最佳场景 |
|------|----------|----------|
| `blueprint`（默认） | grid + cool + technical + balanced | 架构、系统设计 |
| `chalkboard` | organic + warm + handwritten + balanced | 教育、教程 |
| `corporate` | clean + professional + geometric + balanced | 投资者、提案 |
| `minimal` | clean + neutral + geometric + minimal | 高管简报 |
| `sketch-notes` | organic + warm + handwritten + balanced | 教程、学习 |
| `hand-drawn-edu` | organic + macaron + handwritten + balanced | 教育图表 |
| `watercolor` | organic + warm + humanist + minimal | 生活方式、健康 |
| `dark-atmospheric` | clean + dark + editorial + balanced | 娱乐、游戏 |
| `notion` | clean + neutral + geometric + dense | 产品演示、SaaS |
| `bold-editorial` | clean + vibrant + editorial + balanced | 产品发布、主题演讲 |
| `editorial-infographic` | clean + cool + editorial + dense | 技术解释、研究 |
| `fantasy-animation` | organic + vibrant + handwritten + minimal | 教育叙事 |
| `intuition-machine` | clean + cool + technical + dense | 技术文档、学术 |
| `pixel-art` | pixel + vibrant + technical + balanced | 游戏、开发者演讲 |
| `scientific` | clean + cool + technical + dense | 生物、化学、医学 |
| `vector-illustration` | clean + vibrant + humanist + balanced | 创意、儿童内容 |
| `vintage` | paper + warm + editorial + balanced | 历史、遗产 |

完整预设规范：`references/themes/{preset}.md`。维度→预设映射：`references/dimensions/presets.md`。

### 自动风格选择

| 关键词 | 预设 |
|--------|------|
| tutorial, learn, education, guide, beginner | `sketch-notes` |
| hand-drawn, infographic, diagram, process, onboarding | `hand-drawn-edu` |
| classroom, teaching, school, chalkboard | `chalkboard` |
| architecture, system, data, analysis, technical | `blueprint` |
| creative, children, kids, cute | `vector-illustration` |
| executive, minimal, clean, simple | `minimal` |
| saas, product, dashboard, metrics | `notion` |
| investor, quarterly, business, corporate | `corporate` |
| launch, marketing, keynote, magazine | `bold-editorial` |
| entertainment, music, gaming, atmospheric | `dark-atmospheric` |
| explainer, journalism, science communication | `editorial-infographic` |
| story, fantasy, animation, magical | `fantasy-animation` |
| gaming, retro, pixel, developer | `pixel-art` |
| biology, chemistry, medical, scientific | `scientific` |
| history, heritage, vintage, expedition | `vintage` |
| lifestyle, wellness, travel, artistic | `watercolor` |
| briefing, academic, research, bilingual | `intuition-machine` |

无匹配时回退到 `blueprint`。

### 页数启发式

| 源内容长度 | 推荐页数 |
|------------|----------|
| < 1000 字 | 5-10 |
| 1000-3000 字 | 10-18 |
| 3000-5000 字 | 15-25 |
| > 5000 字 | 20-30（考虑拆分） |

## 主题色系统（5 套预设）

从 guizang-ppt-skill 继承的 5 套主题色，控制深色/浅色页的整体色温：

| # | 主题 | 适合 |
|---|------|------|
| 1 | 🖋 墨水经典 | 通用 / 商业发布 / 默认 |
| 2 | 🌊 靛蓝瓷 | 科技 / 研究 / 数据 |
| 3 | 🌿 森林墨 | 自然 / 可持续 / 文化 |
| 4 | 🍂 牛皮纸 | 怀旧 / 人文 / 文学 |
| 5 | 🌙 沙丘 | 艺术 / 设计 / 创意 |

## 文件布局

```
slide-deck/{topic-slug}/
├── source-{slug}.{ext}     # 源内容
├── analysis.md              # 分析结果
├── outline.md               # 大纲（含 CSS_STYLE_INSTRUCTIONS）
└── index.html               # 最终 HTML 输出（唯一产出物）
```

`index.html` 是唯一产出物。所有内容（文字、布局、风格）内嵌在 HTML 中。

**备份规则**：写入前如文件已存在，重命名为 `{name}-backup-YYYYMMDD-HHMMSS.{ext}`。

## 工作流

```
- [ ] Step 1: Setup & 分析
- [ ] Step 2: 确认 ⚠️ 必需（Round 1；仅"自定义维度"时进入 Round 2）
- [ ] Step 3: 生成大纲
- [ ] Step 4: 审查大纲（条件性）
- [ ] Step 5: 生成 HTML 幻灯片
- [ ] Step 6: 审查 HTML（条件性）
- [ ] Step 7: 预览与交付
- [ ] Step 8: 输出摘要
```

### Step 1: Setup & 分析

**1.1 加载 EXTEND.md** — 按优先级查找：

| 路径 | 范围 |
|------|------|
| `.baoyu-skills/peng-slide-deck/EXTEND.md` | 项目 |
| `$HOME/.baoyu-skills/peng-slide-deck/EXTEND.md` | 用户 |

读取并输出偏好摘要。未找到则使用默认值。

**1.2 分析内容** — 遵循 `references/analysis-framework.md`：
- 分类内容类型
- 检测语言
- 标注风格信号
- 估算页数
- 生成 topic slug

保存源文件为 `source.md`（遵守备份规则）。

**1.3 检查已有输出** — 如果 `slide-deck/{topic-slug}/` 存在，询问处理方式（重新生成大纲/重新生成 HTML/备份后重新生成/退出）。

保存分析结果到 `analysis.md`。

### Step 2: 确认 ⚠️ 必需

**硬性门控**：必须完成确认才能进入 Step 3。除非用户明确说"直接生成"/"不用确认"/"跳过确认"。

**Round 1（始终执行）** — 批量 6 个问题：
1. 风格（推荐预设 / 备选预设 / 自定义维度）
2. 主题色（5 套预设选一）
3. 受众（通用 / 初学者 / 专家 / 高管）
4. 页数
5. 是否审查大纲
6. 是否审查 HTML

**Round 2（仅"自定义维度"时）** — 批量 4 个问题：纹理 / 情绪 / 排版 / 密度。

完整选项文案见 `references/confirmation.md`。

### Step 3: 生成大纲

解析风格：预设 → `references/themes/{preset}.md`；自定义维度 → 合并 `references/dimensions/` 中的文件。

构建 `CSS_STYLE_INSTRUCTIONS`：从解析的风格中提取 CSS 变量块（`:root` 块），写入大纲。大纲结构见 `references/outline-template.md`。

`--outline-only` 时在此停止。

### Step 4: 审查大纲（条件性）

展示幻灯片列表（`# | 标题 | 类型 | 布局`）、总数、解析后的风格。询问：继续 / 编辑大纲 / 重新生成。

### Step 5: 生成 HTML 幻灯片

1. 从 `assets/template.html` 拷贝模板到 `slide-deck/{topic-slug}/index.html`
2. 替换 `[必填]` 占位符（`<title>` 等）
3. 从大纲的 `CSS_STYLE_INSTRUCTIONS` 中提取完整 `:root` 块，替换模板中的主题色部分
4. 为每一页大纲条目生成对应的 `<section class="slide ...">` HTML
5. 插入到模板的 `<!-- SLIDES_HERE -->` 位置
6. 更新导航圆点（JS 自动计算）

布局选择参考 `references/layouts.md`。组件细节参考 `references/components.md`。

> [!IMPORTANT]
> **编码安全**：必须使用 `Write` 工具直接写入 `index.html`。禁止通过 Bash heredoc、Python 脚本等间接方式生成最终 HTML 文件——中文内容经过多层编码链（heredoc → shell → Python → 文件）极易发生双重 UTF-8 编码损坏，导致浏览器显示乱码。

`--html-only` 时在此停止。

### Step 6: 审查 HTML（条件性）

展示生成的页面摘要，询问：继续 / 编辑 HTML / 重新生成。

### Step 7: 预览与交付

```bash
open "slide-deck/{topic-slug}/index.html"
```

直接浏览器打开即可，无需本地服务器。

### Step 8: 摘要

```
Slide Deck Complete!
Topic: [topic]
Style: [preset 或 "custom: texture+mood+typography+density"]
Theme: [墨水经典 / 靛蓝瓷 / 森林墨 / 牛皮纸 / 沙丘]
Location: slide-deck/{topic-slug}/
Slides: N

- 01: [封面标题]
- ...
- NN: [封底标题]

HTML: index.html
```

## 幻灯片修改

| 操作 | 流程 |
|------|------|
| 编辑 | 直接修改 `index.html` 中对应 `<section>` |
| 添加 | 插入新 `<section>`，更新后续页号和 `chrome` 里的页码 |
| 删除 | 删除对应 `<section>`，更新后续页号 |
| 换主题 | 替换 `:root` 块，无需改动任何 slide HTML |
| 换风格 | 替换 `:root` 块中的风格相关变量 |

## 图片嵌入（可选）

`index.html` 本身是自包含的，不需要任何图片。如果确实需要嵌入外部图片素材（照片、截图、图表）：

- 在 `index.html` 同级创建 `images/` 目录
- 命名：`{页号}-{语义}.{ext}`，例如 `03-figma.jpg`
- 规格：单张 ≥ 1600px 宽，JPG 用于照片，PNG 用于透明图
- HTML 中引用：`<img src="images/03-figma.jpg">`

没有图片时直接用 CSS 色块、数据卡片、文字排版承载内容 — 这本身就是本技能的设计意图。

## 参考文件

| 文件 | 内容 |
|------|------|
| `assets/template.html` | 完整可运行的 HTML 模板（种子文件） |
| `references/dimensions/texture.md` | 纹理维度规范 |
| `references/dimensions/mood.md` | 情绪/色彩维度规范 |
| `references/dimensions/typography.md` | 排版维度规范 |
| `references/dimensions/density.md` | 密度维度规范 |
| `references/dimensions/presets.md` | 预设→维度映射 |
| `references/themes/{preset}.md` | 每个预设的完整 CSS 规范 |
| `references/layouts.md` | HTML 布局模板库 |
| `references/components.md` | HTML 组件参考 |
| `references/analysis-framework.md` | 内容分析框架 |
| `references/outline-template.md` | 大纲模板 |
| `references/confirmation.md` | 用户确认选项文案 |
| `references/content-rules.md` | 内容与风格规则 |
| `references/checklist.md` | 质量检查清单 |
| `references/modification-guide.md` | 修改工作流 |
| `references/config/preferences-schema.md` | EXTEND.md 偏好架构 |

## 字体策略

### 三层回退

```
Google Fonts（首选）→ 系统字体（回退）→ 通用字体族（最终兜底）
```

| 角色 | Google Fonts | 系统回退（安全） | 最终兜底 |
|------|-------------|-----------------|----------|
| 中文标题（衬线） | Noto Serif SC | PingFang SC / Songti SC (macOS) | serif |
| 中文正文（非衬线） | Noto Sans SC | PingFang SC (macOS) | sans-serif |
| 英文标题 | Playfair Display / Inter | -apple-system / Georgia | serif / sans-serif |
| 英文正文 | Inter / Source Serif 4 | -apple-system / Georgia | sans-serif / serif |
| 等宽 | JetBrains Mono / IBM Plex Mono | SF Mono (macOS) | monospace |
| 手写 | Caveat / Klee One | Kaiti SC (macOS) | cursive |

所有字体均为 SIL OFL（Google Fonts）、Apple 系统字体或 CSS 通用族名，无版权风险。

### 国内用户

Google Fonts 在国内无法加载时，自动回退：
- **macOS**: PingFang SC + Songti SC + SF Mono — Apple 自有字体，效果接近 Google Fonts
- **Windows/Linux**: 浏览器默认衬线/非衬线/等宽字体 — 结构清晰，仅风格细节有差异
- 体感差异主要在英文衬线标题（Playfair Display 退化为 Georgia 或 Times New Roman）

### 离线使用

即使完全无网络，所有内容仍可读。`motion.min.js` 本地兜底已内置。

## 注意事项

- HTML 文件自包含，无需服务器，直接浏览器打开
- 翻页支持：键盘 ← →、滚轮、触屏滑动、底部圆点、ESC 索引
- 动效由 Motion One 驱动（本地兜底 + CDN 双保险）
- 打印：浏览器打开后 Ctrl+P / Cmd+P 可直接打印或保存为 PDF
- 字体从 Google Fonts CDN 加载，首次加载需联网
