# vintage (paper + warm + editorial + balanced)

**Best for**: 历史、文化遗产、复古主题、人文探索
**Feel**: 怀旧、时光沉淀、书籍感，像古籍或老照片集
**Auto-select keywords**: history, heritage, vintage, expedition, classic, archive, antique, cultural

```css
:root {
  /* --- Texture: paper --- */
  --bg-texture: none;
  --bg-overlay: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='300' height='300'><filter id='g'><feTurbulence type='fractalNoise' baseFrequency='0.04' numOctaves='5' stitchTiles='stitch'/></filter><rect width='100%' height='100%' filter='url(%23g)' opacity='0.35'/></svg>");
  --texture-opacity: 0.6;
  --border-radius: 3px;

  /* --- Mood: warm --- */
  --palette-bg: #FAF8F0;
  --palette-bg-rgb: 250,248,240;
  --palette-text: #2C3E50;
  --palette-text-rgb: 44,62,80;
  --palette-text-secondary: #4A4A4A;
  --palette-accent-1: #F4A261;
  --palette-accent-1-rgb: 244,162,97;
  --palette-accent-2: #E9C46A;
  --palette-accent-2-rgb: 233,196,106;
  --palette-accent-3: #87A96B;
  --palette-accent-3-rgb: 135,169,107;
  --palette-warning: #E07A5F;

  /* --- Typography: editorial --- */
  --font-headline-en: 'Playfair Display', Georgia, serif;
  --font-headline-zh: 'Noto Serif SC', 'PingFang SC', 'Songti SC', serif;
  --font-body-en: 'Source Serif 4', 'Georgia', 'Times New Roman', serif;
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

<!-- Google Fonts: https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,700&family=Source+Serif+4:ital,opsz,wght@0,8..60,300;0,8..60,400;0,8..60,500;0,8..60,600;0,8..60,700;1,8..60,400&family=Noto+Serif+SC:wght@300;400;500;600;700;900&family=Noto+Sans+SC:wght@300;400;500;700;900&family=IBM+Plex+Mono:wght@300;400;500;600&display=swap -->
