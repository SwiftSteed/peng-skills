# minimal (clean + neutral + geometric + minimal)

**Best for**: 高管简报、极简展示、快速汇报
**Feel**: 极致简洁、呼吸感强、无干扰，像 Apple Keynote 的极简风格
**Auto-select keywords**: executive, minimal, clean, simple, briefing, concise, elegant

```css
:root {
  /* --- Texture: clean --- */
  --bg-texture: none;
  --bg-overlay: none;
  --texture-opacity: 0;
  --border-radius: 4px;

  /* --- Mood: neutral --- */
  --palette-bg: #FFFFFF;
  --palette-bg-rgb: 255,255,255;
  --palette-text: #18181B;
  --palette-text-rgb: 24,24,27;
  --palette-text-secondary: #71717A;
  --palette-accent-1: #18181B;
  --palette-accent-1-rgb: 24,24,27;
  --palette-accent-2: #A1A1AA;
  --palette-accent-2-rgb: 161,161,170;
  --palette-accent-3: #E4E4E7;
  --palette-accent-3-rgb: 228,228,231;
  --palette-warning: #EF4444;

  /* --- Typography: geometric --- */
  --font-headline-en: 'Inter', -apple-system, 'Helvetica Neue', sans-serif;
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

  /* --- Density: minimal --- */
  --slide-padding: 8vh 8vw 10vh 8vw;
  --content-gap: 3.6vh;
  --headline-hero-size: 12vw;
  --headline-xl-size: 7vw;
  --headline-md-size: 2.6vw;
  --subheadline-size: 3.6vw;
  --body-size: max(16px, 1.4vw);
  --lead-size: 2vw;
  --margin-content: 15%;
  --grid-gap-h: 4vw;
  --grid-gap-v: 5vh;
  --stat-nb-size: 6.5vw;
  --stat-label-size: max(11px, 0.85vw);
}
```

<!-- Google Fonts: https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Noto+Serif+SC:wght@300;400;500;600;700;900&family=Noto+Sans+SC:wght@300;400;500;700;900&family=IBM+Plex+Mono:wght@300;400;500;600&family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,700&family=Caveat:wght@400;500;600;700&family=Klee+One:wght@400;600&display=swap -->
