<div align="center">

# peng-skills

**AI Agent Skills for Content Creation**

A collection of skills for content creation workflows.

[English](./README.md) · [中文](./README.zh-CN.md)

</div>

---

## Skills

| Skill | Description |
|-------|-------------|
| [peng-slide-deck](./peng-slide-deck/SKILL.md) | HTML+CSS slide deck generator — 17 curated visual presets (customizable across texture, color, typography, density), 8-step reviewable pipeline |
| [peng-image-cards](./peng-image-cards/SKILL.md) | HTML+CSS vertical card generator — 12 styles × 8 layouts × 3 palettes, output as scrollable web page. Ideal for social media, email, article embeds |
| [peng-cover-image](./peng-cover-image/SKILL.md) | HTML+CSS article cover generator — 6 types × 11 palettes × 7 renderings × 4 text levels. Browser preview, screenshot as social share image |

## Quick Start

```bash
git clone https://github.com/SwiftSteed/peng-skills.git
ln -sf $(pwd)/peng-skills/peng-slide-deck ~/.claude/skills/peng-slide-deck
```

## peng-slide-deck

> [!NOTE]
> Forked from [baoyu-slide-deck](https://github.com/JimLiu/baoyu-skills) by [JimLiu](https://github.com/JimLiu). Replaces image generation with pure HTML+CSS output — same curated visual presets and reviewable pipeline, browser-native rendering.
>
> Color theme system and Motion One animation engine adapted from [guizang-ppt-skill](https://github.com/op7418/guizang-ppt-skill) by [op7418](https://github.com/op7418).

Transform content into a single-file HTML slide deck — no image generation backend, no PPT tooling, just open in a browser and present.

### Usage

```bash
# From markdown file
/peng-slide-deck path/to/article.md

# With style and audience
/peng-slide-deck path/to/article.md --style corporate
/peng-slide-deck path/to/article.md --audience executives

# Target slide count
/peng-slide-deck path/to/article.md --slides 15

# Outline only (no HTML generation)
/peng-slide-deck path/to/article.md --outline-only

# With language and theme
/peng-slide-deck path/to/article.md --lang zh --theme indigo
```

### Options

| Option | Description |
|--------|-------------|
| `--style <name>` | Visual style: preset name or `custom` |
| `--audience <type>` | Target: beginners, intermediate, experts, executives, general |
| `--lang <code>` | Output language (en, zh, ja, etc.) |
| `--slides <N>` | Target slide count (8-25 recommended, max 30) |
| `--outline-only` | Generate outline only, skip HTML |
| `--html-only` | Generate HTML only, skip review |
| `--theme <name>` | Color theme: ink, indigo, forest, kraft, dune |

### Live Demo

Try it in your browser — full WebGL backgrounds, page transitions, and animations:

→ **[Live Demo](https://swiftsteed.github.io/peng-skills/demo/index-en.html)** ←

![peng-slide-deck screenshot](./screenshots/peng-slide-deck-en.png)

### Key Features

- **17 curated visual presets**: blueprint, corporate, minimal, sketch-notes, bold-editorial, vintage, and more — auto-recommended from content keywords, freely customizable across texture, color, typography, and density
- **17 curated presets**: blueprint, corporate, minimal, sketch-notes, bold-editorial, vintage, and more — auto-selected from content keywords
- **8-step reviewable pipeline**: analyze → confirm → outline → review → generate HTML → review → preview → ship
- **Font safety**: Google Fonts (SIL OFL) → Apple system fonts → CSS generic fallbacks — zero copyright risk
- **Self-contained output**: single HTML file with WebGL backgrounds, keyboard/wheel/touch navigation, ESC overview, and offline Motion One animations
- **Print to PDF**: Cmd+P directly in browser

## peng-image-cards

> [!NOTE]
> Forked from [baoyu-image-cards](https://github.com/JimLiu/baoyu-skills#baoyu-image-cards) by [JimLiu](https://github.com/JimLiu). Replaces image generation with pure HTML+CSS output — same 12 styles × 8 layouts × 3 palettes, browser-native rendering.

Generate vertical content cards as a single HTML file — scrollable, mobile-friendly, ideal for social media, email marketing, and article embeds.

### Usage

```bash
/peng-image-cards path/to/content.md
/peng-image-cards path/to/content.md --preset knowledge-card
/peng-image-cards path/to/content.md --style notion --layout dense
/peng-image-cards path/to/content.md --cards 5
/peng-image-cards path/to/content.md --outline-only
```

### Live Demo

→ **[Live Demo](https://swiftsteed.github.io/peng-skills/demo/cards/)** ←

### Key Features

- **12 visual styles**: cute, fresh, warm, bold, minimal, retro, pop, notion, chalkboard, study-notes, screen-print, sketch-notes
- **8 layouts**: sparse, balanced, dense, list, comparison, flow, mindmap, quadrant
- **3 color palettes**: macaron, warm, neon — override style colors independently
- **28 presets**: quick-start style+layout combos for every content type
- **Vertical scroll**: mobile-first 3:4 card ratio, scroll-snap navigation
- **Multi-scenario**: screenshot for social media, embed in articles, email-friendly HTML

## peng-cover-image

> [!NOTE]
> Forked from [baoyu-cover-image](https://github.com/JimLiu/baoyu-skills#baoyu-cover-image) by [JimLiu](https://github.com/JimLiu). Replaces image generation with pure HTML+CSS output — same 5-dimension system (Type × Palette × Rendering × Text × Mood), browser-native rendering.

Generate a single article cover as HTML — one page, one file, open in browser and screenshot for use anywhere.

### Usage

```bash
/peng-cover-image path/to/article.md
/peng-cover-image path/to/article.md --type hero --palette warm
/peng-cover-image path/to/article.md --aspect 2.35:1 --text title-subtitle
/peng-cover-image path/to/article.md --title "My Title" --author "Name"
```

### Live Demo

→ **[Live Demo](https://swiftsteed.github.io/peng-skills/demo/covers/)** ←

### Key Features

- **5 dimensions**: Type (6) × Palette (11) × Rendering (7) × Text (4) × Mood (3)
- **6 aspect ratios**: 16:9, 2.35:1, 4:3, 3:2, 1:1, 3:4 — cinema to square
- **11 palettes**: warm, elegant, cool, dark, earth, vivid, pastel, mono, retro, duotone, macaron
- **7 rendering styles**: flat-vector, hand-drawn, painterly, digital, pixel, chalk, screen-print
- **4 font families**: clean, handwritten, serif, display
- **Auto-selection**: content keywords → recommended type + palette
- **Screenshot-ready**: open in browser, Cmd+Shift+4, use as og:image, article header, or email hero

## License

This project is licensed under the [MIT License](./LICENSE).
