# sketch-notes (organic + warm + handwritten + balanced)

**Best for**: 教程、学习笔记、知识总结、轻松讲解
**Feel**: 手绘草图感、亲切、非正式，像在笔记本上画出的示意图
**Auto-select keywords**: tutorial, learn, education, guide, beginner, notes, explain, how-to

```css
:root {
  /* --- Texture: organic --- */
  --bg-texture: none;
  --bg-overlay: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='200' height='200'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/></filter><rect width='100%' height='100%' filter='url(%23n)' opacity='0.12'/></svg>");
  --texture-opacity: 0.3;
  --border-radius: 8px;

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

  /* --- Typography: handwritten --- */
  --font-headline-en: 'Caveat', 'Klee One', 'Kaiti SC', cursive;
  --font-headline-zh: 'Noto Serif SC', 'PingFang SC', 'Songti SC', serif;
  --font-body-en: 'Inter', -apple-system, 'Helvetica Neue', sans-serif;
  --font-body-zh: 'Noto Sans SC', 'PingFang SC', sans-serif;
  --font-mono: 'JetBrains Mono', 'IBM Plex Mono', 'SF Mono', monospace;
  --font-display: 'Playfair Display', 'Georgia', 'Times New Roman', serif;
  --font-handwritten: 'Caveat', 'Klee One', 'Kaiti SC', cursive;
  --headline-weight: 600;
  --headline-style: normal;
  --headline-letter-spacing: 0em;
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

<!-- Google Fonts: https://fonts.googleapis.com/css2?family=Caveat:wght@400;500;600;700&family=Klee+One:wght@400;600&family=Inter:wght@300;400;500;600;700;800;900&family=Noto+Sans+SC:wght@300;400;500;700;900&family=IBM+Plex+Mono:wght@300;400;500;600&family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,700&display=swap -->
