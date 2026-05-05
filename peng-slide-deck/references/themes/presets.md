# Theme Presets Index

17 个预设覆盖 4 维正交风格系统的核心组合。每个预设是一个完整的 `:root` CSS 变量块，可直接替换 `assets/template.html` 中的风格变量区块。

## 维度 → 预设映射表

| # | 预设 | Texture | Mood | Typography | Density | 最佳场景 |
|---|------|---------|------|------------|---------|----------|
| 1 | `blueprint` | grid | cool | technical | balanced | 架构、系统设计、技术分析 |
| 2 | `chalkboard` | organic | warm | handwritten | balanced | 教育、教程、课堂 |
| 3 | `corporate` | clean | professional | geometric | balanced | 投资者、提案、商业 |
| 4 | `minimal` | clean | neutral | geometric | minimal | 高管简报、极简展示 |
| 5 | `sketch-notes` | organic | warm | handwritten | balanced | 教程、学习笔记 |
| 6 | `hand-drawn-edu` | organic | macaron | handwritten | balanced | 教育图表、手绘风格 |
| 7 | `watercolor` | organic | warm | humanist | minimal | 生活方式、健康、旅行 |
| 8 | `dark-atmospheric` | clean | dark | editorial | balanced | 娱乐、游戏、氛围 |
| 9 | `notion` | clean | neutral | geometric | dense | 产品演示、SaaS、数据面板 |
| 10 | `bold-editorial` | clean | vibrant | editorial | balanced | 产品发布、主题演讲 |
| 11 | `editorial-infographic` | clean | cool | editorial | dense | 技术解释、研究传播 |
| 12 | `fantasy-animation` | organic | vibrant | handwritten | minimal | 教育叙事、奇幻故事 |
| 13 | `intuition-machine` | clean | cool | technical | dense | 技术文档、学术报告 |
| 14 | `pixel-art` | pixel | vibrant | technical | balanced | 游戏、开发者演讲、复古 |
| 15 | `scientific` | clean | cool | technical | dense | 生物、化学、医学 |
| 16 | `vector-illustration` | clean | vibrant | humanist | balanced | 创意、儿童内容、插图 |
| 17 | `vintage` | paper | warm | editorial | balanced | 历史、遗产、人文 |

## 维度枚举

### Texture（5 种）
| 值 | 说明 | 视觉特征 |
|----|------|----------|
| `clean` | 纯色 | 无纹理，干净现代，圆角 4px |
| `grid` | 网格 | SVG 网格线叠加，圆角 2px，技术感 |
| `organic` | 有机 | SVG 噪声纹理，圆角 8px，手绘感 |
| `pixel` | 像素 | 像素网格图案，圆角 0，复古游戏感 |
| `paper` | 纸张 | 纸纹颗粒 SVG，圆角 3px，怀旧感 |

### Mood（7 种）
| 值 | 色温 | 主背景 | 主文字 | Accent 1 |
|----|------|--------|--------|----------|
| `professional` | 暖 | #FFFFFF | #1E3A5F | #C9A227（金） |
| `warm` | 暖 | #FAF8F0 | #2C3E50 | #F4A261（橙） |
| `macaron` | 暖 | #F5F0E8 | #2D2D2D | #A8D8EA（蓝） |
| `cool` | 冷 | #FAF8F5 | #334155 | #2563EB（蓝） |
| `vibrant` | 中性 | #FFFFFF | #1A1A2E | #E94560（红） |
| `dark` | 冷 | #0D1117 | #E6EDF3 | #58A6FF（蓝） |
| `neutral` | 中性 | #FFFFFF | #18181B | #18181B（黑） |

### Typography（5 种）
| 值 | 风格 | Headline EN | Body EN | 标志性特征 |
|----|------|-------------|---------|-----------|
| `geometric` | 几何现代 | Inter | Inter | 干净、无衬线、科技感 |
| `humanist` | 人文温暖 | Source Serif 4 | Source Serif 4 | 衬线体、温暖、古典 |
| `handwritten` | 手写活泼 | Caveat | Inter | 手写标题、趣味感 |
| `editorial` | 编辑典雅 | Playfair Display | Source Serif 4 | 高端杂志感、对比强 |
| `technical` | 技术等宽 | JetBrains Mono | Inter | 等宽代码感、精确 |

### Density（3 种）
| 值 | 内边距 | 标题大小 | 间距 | 适用场景 |
|----|--------|----------|------|----------|
| `minimal` | 8vh 8vw | 12vw hero | 3.6vh gap | 演讲、叙事、少量内容 |
| `balanced` | 6vh 6vw | 10vw hero | 2.4vh gap | 通用、大多数场景 |
| `dense` | 4vh 4vw | 8vw hero | 1.6vh gap | 信息密集、文档、数据 |

## 使用方式

### 在 HTML 模板中应用

1. 找到 `assets/template.html` 中的 `:root` 块
2. 找到 `/* --- Texture: ... --- */` 到 `/* --- Density: ... --- */` 之间的风格变量区块
3. 从对应 `references/themes/{preset-name}.md` 中复制完整的 `:root` 块
4. 替换模板中对应的变量区块
5. 更新 Google Fonts 链接为对应 typography 的字体组合

### 通过 SKILL.md 工作流应用

Step 3 生成大纲时自动解析预设 → 提取 CSS 变量 → 写入 CSS_STYLE_INSTRUCTIONS。Step 5 生成 HTML 时自动替换。

### 自定义维度组合

如需 17 个预设以外的组合（最多 5x7x5x3=525 种），使用 `--style custom` 并在 Step 2 Round 2 中逐个选择维度。系统会从以下参考文件中合并变量：

- `references/dimensions/texture.md` — 纹理变量
- `references/dimensions/mood.md` — 色彩变量
- `references/dimensions/typography.md` — 排版变量
- `references/dimensions/density.md` — 密度变量

## 自动选择关键词

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
