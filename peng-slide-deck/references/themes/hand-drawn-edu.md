# hand-drawn-edu (organic + macaron + handwritten + balanced)

**Best for**: 教育图表、手绘风格教程、入门引导、流程图
**Feel**: 可爱、柔和、亲和力强，像老师手绘的教学挂图
**Auto-select keywords**: hand-drawn, infographic, diagram, process, onboarding, kids education, visual guide

```css
:root {
  /* --- Texture: organic --- */
  --bg-texture: none;
  --bg-overlay: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='200' height='200'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/></filter><rect width='100%' height='100%' filter='url(%23n)' opacity='0.1'/></svg>");
  --texture-opacity: 0.3;
  --border-radius: 8px;

  /* --- Mood: macaron --- */
  --palette-bg: #F5F0E8;
  --palette-bg-rgb: 245,240,232;
  --palette-text: #2D2D2D;
  --palette-text-rgb: 45,45,45;
  --palette-text-secondary: #6B6B6B;
  --palette-accent-1: #A8D8EA;
  --palette-accent-1-rgb: 168,216,234;
  --palette-accent-2: #B5E5CF;
  --palette-accent-2-rgb: 181,229,207;
  --palette-accent-3: #D5C6E0;
  --palette-accent-3-rgb: 213,198,224;
  --palette-warning: #E8655A;

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
