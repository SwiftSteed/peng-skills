# blueprint (grid + cool + technical + balanced)

**Best for**: 架构图、系统设计、数据分析、技术文档
**Feel**: 冷静、精确、工程感，像蓝图上绘制的技术规格
**Auto-select keywords**: architecture, system design, data analysis, technical, blueprint, engineering, infrastructure

```css
:root {
  /* --- Texture: grid --- */
  --bg-texture: none;
  --bg-overlay: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='40' height='40'><rect width='40' height='40' fill='none'/><rect width='1' height='40' fill='rgba(0,0,0,0.04)' x='20'/><rect width='40' height='1' fill='rgba(0,0,0,0.04)' y='20'/></svg>");
  --texture-opacity: 0.5;
  --border-radius: 2px;

  /* --- Mood: cool --- */
  --palette-bg: #FAF8F5;
  --palette-bg-rgb: 250,248,245;
  --palette-text: #334155;
  --palette-text-rgb: 51,65,85;
  --palette-text-secondary: #64748B;
  --palette-accent-1: #2563EB;
  --palette-accent-1-rgb: 37,99,235;
  --palette-accent-2: #1E3A5F;
  --palette-accent-2-rgb: 30,58,95;
  --palette-accent-3: #BFDBFE;
  --palette-accent-3-rgb: 191,219,254;
  --palette-warning: #F59E0B;

  /* --- Typography: technical --- */
  --font-headline-en: 'JetBrains Mono', 'IBM Plex Mono', ui-monospace, monospace;
  --font-headline-zh: 'Noto Serif SC', 'PingFang SC', 'Songti SC', serif;
  --font-body-en: 'Inter', -apple-system, 'Helvetica Neue', sans-serif;
  --font-body-zh: 'Noto Sans SC', 'PingFang SC', sans-serif;
  --font-mono: 'JetBrains Mono', 'IBM Plex Mono', 'SF Mono', monospace;
  --font-display: 'Playfair Display', 'Georgia', 'Times New Roman', serif;
  --font-handwritten: 'Caveat', 'Klee One', 'Kaiti SC', cursive;
  --headline-weight: 700;
  --headline-style: normal;
  --headline-letter-spacing: -0.02em;
  --body-letter-spacing: 0.01em;

  /* --- Density: balanced --- */
  --slide-padding: 6vh 6vw 10vh 6vw;
  --content-gap: 2.4vh;
  --headline-hero-size: 10vw;
  --headline-xl-size: 6.2vw;
  --headline-md-size: 2.3vw;
  --subheadline-size: 3.1vw;
  --body-size: max(15px, 1.22vw);
  --lead-size: 1.75vw;
  --margin-content: 10%;
  --grid-gap-h: 3vw;
  --grid-gap-v: 4vh;
  --stat-nb-size: 5.8vw;
  --stat-label-size: max(10px, 0.78vw);
}
```

<!-- Google Fonts: https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600;700&family=Noto+Serif+SC:wght@300;400;500;600;700;900&family=Inter:wght@300;400;500;600;700;800;900&family=Noto+Sans+SC:wght@300;400;500;700;900&family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,700&family=Caveat:wght@400;500;600;700&family=Klee+One:wght@400;600&display=swap -->
