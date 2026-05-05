# Texture Dimension (CSS Background System)

> Maps the 5 texture options from baoyu-slide-deck's image-prompt-based system to concrete CSS background implementations.
> Each texture defines `--bg-texture`, `--bg-overlay`, `--border-radius`, and additional decorative CSS custom properties.

---

## Overview

| Texture | Character | Best For |
|---------|-----------|----------|
| `clean` | Solid, no pattern, pure minimalism | Executive briefings, corporate decks, keynotes |
| `grid` | Subtle engineering grid overlay | Architecture diagrams, system design, technical documentation |
| `organic` | Soft grain/noise, hand-crafted feel | Education, creative content, friendly presentations |
| `pixel` | Blocky pixel-art aesthetic | Game developer talks, retro-themed content |
| `paper` | Aged paper texture with warmth | History, heritage, literary content, narrative decks |

---

## Texture Definitions

### 1. `clean` -- Solid Minimalist

**Visual Description**: Pure solid background with no visible pattern. Clean lines, geometric shapes, maximum clarity. Professional and authoritative.

**CSS Variables**:

```css
--bg-texture: none;
--bg-overlay: none;
--bg-color-fallback: var(--paper);
--border-radius: 0px;
--border-treatment: none;
--shadow-intensity: 0;
```

**Implementation Notes**:
- Simply use `background-color: var(--paper)` or `var(--ink)` -- no additional layers needed
- Content blocks (cards, callouts) may use `border-radius: 0-2px` for a crisp, modern look
- Shadows should be minimal or absent; rely on spacing and typography for hierarchy
- Best paired with bold typography choices (editorial, geometric) to add visual interest

**CSS Background Snippet**:
```css
.slide {
  background-color: var(--paper);
  /* No background-image -- pure solid */
}
```

---

### 2. `grid` -- Engineering Grid Overlay

**Visual Description**: Subtle grid lines at 5-8% opacity over a solid background. Evokes blueprints, engineering drawings, graph paper. Technical and precise.

**CSS Variables**:

```css
--bg-texture: grid;
--bg-overlay:
  /* Major grid lines (every 80px) */
  linear-gradient(rgba(var(--ink-rgb), 0.06) 1px, transparent 1px),
  linear-gradient(90deg, rgba(var(--ink-rgb), 0.06) 1px, transparent 1px);
--bg-overlay-size: 80px 80px;
--bg-overlay-secondary:
  /* Minor grid lines (every 20px) */
  linear-gradient(rgba(var(--ink-rgb), 0.03) 1px, transparent 1px),
  linear-gradient(90deg, rgba(var(--ink-rgb), 0.03) 1px, transparent 1px);
--bg-overlay-secondary-size: 20px 20px;
--border-radius: 2px;
--border-treatment: 1px solid rgba(var(--ink-rgb), 0.08);
--accent-line-opacity: 0.15;
```

**Implementation Notes**:
- Use two stacked grid layers: major grid (80px) at 6% opacity, minor grid (20px) at 3% opacity
- On dark backgrounds (`ink`), invert the grid to white lines at similar low opacity
- Edge accent lines (top/bottom borders on slides) add a blueprint feel
- Grid intersections can optionally have subtle dot markers using `radial-gradient`

**CSS Background Snippet**:
```css
.slide {
  background-color: var(--paper);
  background-image:
    /* Minor grid */
    linear-gradient(rgba(var(--ink-rgb), 0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(var(--ink-rgb), 0.03) 1px, transparent 1px),
    /* Major grid */
    linear-gradient(rgba(var(--ink-rgb), 0.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(var(--ink-rgb), 0.06) 1px, transparent 1px);
  background-size:
    20px 20px,
    20px 20px,
    80px 80px,
    80px 80px;
}

/* For dark mood: use white grid lines */
.mood-dark .slide {
  background-color: var(--ink);
  background-image:
    linear-gradient(rgba(var(--paper-rgb), 0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(var(--paper-rgb), 0.04) 1px, transparent 1px),
    linear-gradient(rgba(var(--paper-rgb), 0.08) 1px, transparent 1px),
    linear-gradient(90deg, rgba(var(--paper-rgb), 0.08) 1px, transparent 1px);
  background-size:
    20px 20px,
    20px 20px,
    80px 80px,
    80px 80px;
}
```

---

### 3. `organic` -- Soft Grain / Noise

**Visual Description**: Subtle noise/grain texture that mimics hand-drawn paper or natural surfaces. Soft, warm, approachable. Feels human-crafted rather than machine-generated.

**CSS Variables**:

```css
--bg-texture: organic;
--bg-overlay: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
--bg-overlay-opacity: 0.5;
--border-radius: 8px;
--border-treatment: 1px solid rgba(var(--ink-rgb), 0.06);
--shadow-intensity: 0.3;
--organic-splotch-color: rgba(var(--accent-1-rgb), 0.04);
```

**Implementation Notes**:
- Primary grain uses an inline SVG data URI with `feTurbulence` filter -- lightweight, no external dependency
- The SVG filter generates fractal noise at ~4% opacity, creating a subtle paper-like grain
- Optional secondary layer: a very subtle radial gradient "splotch" (large, blurred) in the accent color at 3-5% opacity to add warmth
- For dark moods, increase the noise opacity slightly (6-8%) since it's less visible on dark backgrounds
- Content cards get slightly rounded corners (`border-radius: 8px`) to harmonize with organic feel

**CSS Background Snippet**:
```css
.slide {
  background-color: var(--paper);
  /* Organic splotch for warmth */
  background-image:
    radial-gradient(ellipse at 30% 20%, rgba(var(--accent-1-rgb), 0.04) 0%, transparent 50%),
    radial-gradient(ellipse at 70% 80%, rgba(var(--accent-2-rgb), 0.03) 0%, transparent 50%);
  position: relative;
}

/* SVG noise overlay via pseudo-element */
.slide::before {
  content: '';
  position: absolute;
  inset: 0;
  pointer-events: none;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
  opacity: var(--bg-overlay-opacity, 0.5);
  z-index: 0;
}
```

---

### 4. `pixel` -- Pixel-Art / 8-Bit Background

**Visual Description**: Blocky pixel-art aesthetic evoking retro video games, 8-bit computing, and digital nostalgia. Chunky, grid-aligned elements with deliberate jagged edges.

**CSS Variables**:

```css
--bg-texture: pixel;
--bg-overlay:
  /* Pixel dot pattern */
  radial-gradient(circle, rgba(var(--ink-rgb), 0.06) 1px, transparent 1px);
--bg-overlay-size: 8px 8px;
--bg-overlay-secondary:
  /* Larger pixel block pattern */
  linear-gradient(45deg, rgba(var(--accent-1-rgb), 0.04) 25%, transparent 25%),
  linear-gradient(-45deg, rgba(var(--accent-1-rgb), 0.04) 25%, transparent 25%),
  linear-gradient(45deg, transparent 75%, rgba(var(--accent-1-rgb), 0.04) 75%),
  linear-gradient(-45deg, transparent 75%, rgba(var(--accent-1-rgb), 0.04) 75%);
--bg-overlay-secondary-size: 16px 16px;
--bg-overlay-secondary-position: 0 0, 0 8px, 8px -8px, -8px 0px;
--border-radius: 0px;
--border-treatment: 2px solid rgba(var(--ink-rgb), 0.15);
--pixel-size: 4px;
--shadow-intensity: 1;
--shadow-style: 4px 4px 0px rgba(var(--ink-rgb), 0.15);
```

**Implementation Notes**:
- Primary pattern: a tight dot grid (8px) mimics pixel raster, optionally combined with a checkerboard-style pattern at 16px
- Use `image-rendering: pixelated;` on any content images to maintain the aesthetic
- Borders and shadows should be "hard" -- no blur radius (`box-shadow: 4px 4px 0 rgba(...)`)
- Content blocks should use zero border-radius and 2px solid borders for a blocky, pixel-perfect look
- The `--shadow-style` uses a hard offset shadow with no blur, creating the distinctive pixel-art depth effect
- On dark moods, use brighter pixel dots (8-10% white) and neon accent overlays

**CSS Background Snippet**:
```css
.slide {
  background-color: var(--paper);
  background-image:
    /* Checkerboard blocks */
    linear-gradient(45deg, rgba(var(--accent-1-rgb), 0.04) 25%, transparent 25%),
    linear-gradient(-45deg, rgba(var(--accent-1-rgb), 0.04) 25%, transparent 25%),
    linear-gradient(45deg, transparent 75%, rgba(var(--accent-1-rgb), 0.04) 75%),
    linear-gradient(-45deg, transparent 75%, rgba(var(--accent-1-rgb), 0.04) 75%),
    /* Pixel dots */
    radial-gradient(circle, rgba(var(--ink-rgb), 0.05) 1px, transparent 1px);
  background-size:
    16px 16px, 16px 16px, 16px 16px, 16px 16px,
    8px 8px;
  background-position:
    0 0, 0 8px, 8px -8px, -8px 0px,
    0 0;
}

/* Pixel-art card style */
.pixel .card {
  border-radius: 0;
  border: 2px solid rgba(var(--ink-rgb), 0.15);
  box-shadow: 4px 4px 0 rgba(var(--ink-rgb), 0.12);
}
```

---

### 5. `paper` -- Aged Paper Texture

**Visual Description**: A warm, aged paper surface with subtle creases, slight color variation, and vintage character. Evokes old manuscripts, historical documents, and narrative warmth.

**CSS Variables**:

```css
--bg-texture: paper;
--bg-overlay:
  /* Subtle paper fiber gradient */
  repeating-linear-gradient(
    0deg,
    transparent,
    transparent 2px,
    rgba(var(--ink-rgb), 0.008) 2px,
    rgba(var(--ink-rgb), 0.008) 4px
  ),
  /* Vignette for aged edges */
  radial-gradient(ellipse at 50% 50%, transparent 60%, rgba(var(--ink-rgb), 0.04) 100%);
--bg-overlay-secondary:
  /* Occasional horizontal crease lines */
  repeating-linear-gradient(
    0deg,
    transparent,
    transparent 120px,
    rgba(var(--ink-rgb), 0.015) 120px,
    rgba(var(--ink-rgb), 0.015) 121px
  );
--border-radius: 2px;
--border-treatment: none;
--paper-stain-color: rgba(180, 150, 110, 0.08);
--shadow-intensity: 0.3;
--paper-aging: 0.05; /* Controlled yellowing via sepia tint */
```

**Implementation Notes**:
- Base color uses `--paper-tint` (a slightly warmer, off-white version of `--paper`)
- Primary overlay creates a faint horizontal fiber texture (2px cycle) at very low opacity
- Secondary overlay adds occasional faint crease lines at irregular intervals (120px)
- A vignette effect (radial gradient from transparent to slightly tinted) darkens edges slightly, suggesting age
- The paper tint layer (`--paper-stain-color`) adds an overall warm sepia wash
- For the most authentic feel, combine with a warm or macaron mood palette
- On dark moods, invert the concept: use a dark parchment with slightly lighter edge wear

**CSS Background Snippet**:
```css
.slide {
  background-color: var(--paper-tint);
  background-image:
    /* Crease lines */
    repeating-linear-gradient(
      0deg,
      transparent,
      transparent 120px,
      rgba(var(--ink-rgb), 0.012) 120px,
      rgba(var(--ink-rgb), 0.012) 121px
    ),
    /* Paper fiber */
    repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(var(--ink-rgb), 0.006) 2px,
      rgba(var(--ink-rgb), 0.006) 4px
    ),
    /* Edge vignette */
    radial-gradient(ellipse at 50% 50%, transparent 55%, rgba(var(--ink-rgb), 0.035) 100%);
  position: relative;
}

/* Optional: sepia age tint overlay */
.paper .slide::after {
  content: '';
  position: absolute;
  inset: 0;
  pointer-events: none;
  background-color: rgba(180, 150, 110, 0.05);
  mix-blend-mode: multiply;
  z-index: 0;
}
```

---

## Texture CSS Property Summary

| Property | clean | grid | organic | pixel | paper |
|----------|-------|------|---------|-------|-------|
| `--bg-texture` | `none` | `grid` | `organic` | `pixel` | `paper` |
| `--bg-overlay` | `none` | grid lines (linear-gradient) | SVG noise filter | dot+checkerboard | fiber+crease+vignette |
| `--border-radius` | `0px` | `2px` | `8px` | `0px` | `2px` |
| `--card-border-radius` | `0px` | `2px` | `8px` | `0px` | `2px` |
| `--card-shadow` | `none` | `0 1px 3px rgba(0,0,0,0.06)` | `0 2px 12px rgba(0,0,0,0.04)` | `4px 4px 0 rgba(var(--ink-rgb),0.12)` | `0 1px 4px rgba(0,0,0,0.05)` |
| `--card-border` | `none` | `1px solid rgba(var(--ink-rgb),0.08)` | `1px solid rgba(var(--ink-rgb),0.06)` | `2px solid rgba(var(--ink-rgb),0.15)` | `none` |

---

## Usage in `:root` Block

When composing a complete slide deck CSS, the texture section provides:

```css
:root {
  /* === TEXTURE: grid === */
  --texture: grid;
  --bg-texture: grid;
  --bg-overlay:
    linear-gradient(rgba(var(--ink-rgb), 0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(var(--ink-rgb), 0.03) 1px, transparent 1px),
    linear-gradient(rgba(var(--ink-rgb), 0.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(var(--ink-rgb), 0.06) 1px, transparent 1px);
  --bg-overlay-size: 20px 20px, 20px 20px, 80px 80px, 80px 80px;
  --border-radius: 2px;
  --card-border-radius: 2px;
  --card-shadow: 0 1px 3px rgba(0, 0, 0, 0.06);
  --card-border: 1px solid rgba(var(--ink-rgb), 0.08);
  /* ... mood colors, typography, density follow ... */
}
```

Replace the texture-specific values based on the selected texture option above.
