# peng-skills

A collection of AI agent skills for content creation, built as [Claude Code skills](https://docs.anthropic.com/en/docs/claude-code/skills).

## Skills

| Skill | Description |
|-------|-------------|
| [peng-slide-deck](./peng-slide-deck/SKILL.md) | HTML+CSS slide deck generator — 4-dimension orthogonal style system (Texture × Mood × Typography × Density = 525 combinations), 17 curated presets, 8-step reviewable pipeline |

## Quick Start

```bash
# Clone the repo
git clone https://github.com/peng2219/peng-skills.git

# Symlink a skill into Claude Code
ln -sf $(pwd)/peng-skills/peng-slide-deck ~/.claude/skills/peng-slide-deck
```

## peng-slide-deck

Transform content into a single-file HTML slide deck — no image generation, no PPT tooling, just open in a browser.

**Core design:**
- **4-dimension style system**: Texture (5) × Mood (7) × Typography (5) × Density (3) → 525 unique CSS themes
- **17 curated presets**: blueprint, corporate, minimal, sketch-notes, bold-editorial, vintage, and more — auto-selected from content keywords
- **8-step pipeline**: analyze → confirm → outline → review → generate HTML → review → preview → ship
- **Font safety**: Google Fonts (SIL OFL) → Apple system fonts → CSS generic fallbacks — zero copyright risk
- **Offline capable**: Motion One bundled locally; WebGL backgrounds + keyboard/wheel/touch navigation

**Why HTML+CSS instead of image generation:**
- Instant preview in browser, no backend dependency
- Print to PDF directly (Cmd+P)
- Edit any slide by editing its `<section>` block
- Switch theme by replacing one `:root` CSS block
- Entire deck is one self-contained file

---

# peng-skills · 中文

AI 内容创作技能合集，以 [Claude Code skills](https://docs.anthropic.com/en/docs/claude-code/skills) 形式分发。

## 技能列表

| 技能 | 简介 |
|------|------|
| [peng-slide-deck](./peng-slide-deck/SKILL.md) | HTML+CSS 幻灯片生成器 — 4 维正交风格系统（纹理×情绪×排版×密度=525 种组合）、17 个精调预设、8 步可审查管线 |

## 快速开始

```bash
git clone https://github.com/peng2219/peng-skills.git
ln -sf $(pwd)/peng-skills/peng-slide-deck ~/.claude/skills/peng-slide-deck
```

## peng-slide-deck

将内容转化为单文件 HTML 幻灯片——无需生图、无需 PPT 工具，浏览器直接打开。

**核心设计：**
- **4 维正交风格系统**：纹理(5) × 情绪(7) × 排版(5) × 密度(3) → 525 种 CSS 主题
- **17 个精调预设**：blueprint、corporate、minimal、sketch-notes、bold-editorial、vintage 等——根据内容关键词自动推荐
- **8 步可审查管线**：分析 → 确认 → 大纲 → 审查 → 生成 HTML → 审查 → 预览 → 交付
- **字体零版权风险**：Google Fonts (SIL OFL) → Apple 系统字体 → CSS 通用族名
- **离线可用**：Motion One 本地打包；WebGL 背景 + 键盘/滚轮/触屏翻页

**为什么用 HTML+CSS 替代生图：**
- 浏览器即时预览，无后端依赖
- 直接打印为 PDF (Cmd+P)
- 编辑某页只需改对应的 `<section>`
- 换主题只需替换一个 `:root` CSS 块
- 整个 slide deck 是单个自包含文件
