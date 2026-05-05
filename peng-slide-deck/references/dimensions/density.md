# Density Dimension (CSS Spacing & Sizing System)

> Maps the 3 density options to concrete CSS spacing, sizing, and layout variables.
> Density controls information density per slide -- from airy single-focus slides to compact data-rich layouts.
> All size values use viewport-relative units (vw) for consistent scaling across screen sizes.

---

## Overview

| Density | Content Per Slide | Whitespace | Margin | Best For |
|---------|-------------------|------------|--------|----------|
| `minimal` | One focal point | Maximum (15%+) | 15% | Executive briefings, keynotes, hero slides |
| `balanced` | 2-3 key points | Standard (10%) | 10% | General presentations, most content types |
| `dense` | Multiple data points | Compact (5-8%) | 6% | Technical reviews, data dashboards, academic |

---

## Density Definitions

### 1. `minimal` -- Airy, Single-Focus

**Visual Character**: One clear message per slide. Large typography, generous whitespace, minimal visual clutter. The content breathes.

**CSS Variables**:
```css
/* ============================================================
   DENSITY: minimal
   ============================================================ */
--density: minimal;

/* Spacing */
--slide-padding: clamp(48px, 6vw, 96px);
--slide-padding-top: clamp(64px, 8vw, 120px);
--slide-padding-bottom: clamp(48px, 6vw, 96px);
--slide-padding-left: clamp(48px, 6vw, 96px);
--slide-padding-right: clamp(48px, 6vw, 96px);
--content-gap: clamp(24px, 3vw, 48px);
--content-gap-large: clamp(36px, 5vw, 80px);
--content-gap-small: clamp(12px, 1.5vw, 24px);

/* Typography sizing */
--headline-size: clamp(2.2rem, 5vw, 4.5rem);
--headline-size-hero: clamp(2.8rem, 6.5vw, 6rem);
--subheadline-size: clamp(1.2rem, 2.2vw, 2rem);
--body-size: clamp(1.1rem, 1.6vw, 1.4rem);
--body-size-small: clamp(0.9rem, 1.2vw, 1.1rem);

/* Layout */
--margin-content: 15%;
--max-content-width: 880px;
--grid-gap: clamp(36px, 5vw, 72px);
--column-gap: clamp(32px, 4vw, 64px);

/* Cards & components */
--card-padding: clamp(32px, 4vw, 56px);
--card-gap: clamp(24px, 3vw, 48px);
--icon-size: clamp(48px, 5vw, 72px);
--bullet-gap: clamp(16px, 2vw, 28px);

/* Max elements per slide */
--max-bullets: 3;
--max-columns: 2;
--max-cards: 2;
```

**Use When**:
- Audience is executives or non-specialists
- Each slide communicates one bold idea
- Visual impact matters more than information density
- Large images or hero graphics are the focus
- Total slide count exceeds 15 (keep individual slides light)

**CSS Layout Snippet**:
```css
.density-minimal .slide {
  padding: var(--slide-padding-top) var(--slide-padding-left) var(--slide-padding-bottom) var(--slide-padding-right);
}

.density-minimal .content-wrapper {
  max-width: var(--max-content-width);
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: var(--content-gap);
}

.density-minimal h1 {
  font-size: var(--headline-size-hero);
  max-width: 14ch; /* Limit line length for large text */
}

.density-minimal .slide.cover {
  justify-content: center;
  text-align: center;
}

.density-minimal .grid-2col {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--column-gap);
}
```

---

### 2. `balanced` -- Standard, General-Purpose

**Visual Character**: The default sweet spot. Room for 2-4 key points with comfortable reading density. Works for most presentation types.

**CSS Variables**:
```css
/* ============================================================
   DENSITY: balanced
   ============================================================ */
--density: balanced;

/* Spacing */
--slide-padding: clamp(36px, 4vw, 64px);
--slide-padding-top: clamp(48px, 5vw, 80px);
--slide-padding-bottom: clamp(36px, 4vw, 64px);
--slide-padding-left: clamp(36px, 4vw, 64px);
--slide-padding-right: clamp(36px, 4vw, 64px);
--content-gap: clamp(16px, 2vw, 32px);
--content-gap-large: clamp(24px, 3vw, 48px);
--content-gap-small: clamp(8px, 1vw, 16px);

/* Typography sizing */
--headline-size: clamp(1.8rem, 3.8vw, 3.2rem);
--headline-size-hero: clamp(2.2rem, 5vw, 4.5rem);
--subheadline-size: clamp(1rem, 1.6vw, 1.5rem);
--body-size: clamp(0.95rem, 1.3vw, 1.2rem);
--body-size-small: clamp(0.8rem, 1vw, 0.95rem);

/* Layout */
--margin-content: 10%;
--max-content-width: 1000px;
--grid-gap: clamp(24px, 3vw, 48px);
--column-gap: clamp(24px, 3vw, 40px);

/* Cards & components */
--card-padding: clamp(20px, 2.5vw, 36px);
--card-gap: clamp(16px, 2vw, 28px);
--icon-size: clamp(36px, 4vw, 56px);
--bullet-gap: clamp(12px, 1.5vw, 20px);

/* Max elements per slide */
--max-bullets: 5;
--max-columns: 3;
--max-cards: 4;
```

**Use When**:
- General-purpose presentations (default choice)
- Mixed content types (text + visuals + data)
- Audience expects both overview and detail
- Slide count is 8-15
- No strong reason to go minimal or dense

**CSS Layout Snippet**:
```css
.density-balanced .slide {
  padding: var(--slide-padding-top) var(--slide-padding-left) var(--slide-padding-bottom) var(--slide-padding-right);
}

.density-balanced .content-wrapper {
  max-width: var(--max-content-width);
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: var(--content-gap);
}

.density-balanced h1 {
  font-size: var(--headline-size);
}

.density-balanced .grid-3col {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--column-gap);
}

.density-balanced .card {
  padding: var(--card-padding);
}
```

---

### 3. `dense` -- Compact, Data-Rich

**Visual Character**: Information-packed. Smaller text, tighter spacing, more elements per slide. Designed for scanning and reference, not emotional impact.

**CSS Variables**:
```css
/* ============================================================
   DENSITY: dense
   ============================================================ */
--density: dense;

/* Spacing */
--slide-padding: clamp(20px, 2.5vw, 40px);
--slide-padding-top: clamp(28px, 3vw, 48px);
--slide-padding-bottom: clamp(20px, 2.5vw, 40px);
--slide-padding-left: clamp(20px, 2.5vw, 40px);
--slide-padding-right: clamp(20px, 2.5vw, 40px);
--content-gap: clamp(10px, 1.2vw, 20px);
--content-gap-large: clamp(16px, 2vw, 28px);
--content-gap-small: clamp(6px, 0.6vw, 10px);

/* Typography sizing */
--headline-size: clamp(1.4rem, 2.8vw, 2.4rem);
--headline-size-hero: clamp(1.8rem, 3.5vw, 3rem);
--subheadline-size: clamp(0.9rem, 1.2vw, 1.2rem);
--body-size: clamp(0.8rem, 1vw, 1rem);
--body-size-small: clamp(0.7rem, 0.8vw, 0.85rem);

/* Layout */
--margin-content: 6%;
--max-content-width: 1200px;
--grid-gap: clamp(14px, 1.5vw, 24px);
--column-gap: clamp(14px, 1.5vw, 24px);

/* Cards & components */
--card-padding: clamp(12px, 1.5vw, 24px);
--card-gap: clamp(10px, 1vw, 16px);
--icon-size: clamp(24px, 3vw, 40px);
--bullet-gap: clamp(6px, 0.8vw, 14px);

/* Max elements per slide */
--max-bullets: 8;
--max-columns: 4;
--max-cards: 8;
```

**Use When**:
- Technical documentation or reference slides
- Data dashboards with multiple charts
- Academic or research presentations
- Slides meant to be read (not presented live)
- Content must fit in fewer slides

**CSS Layout Snippet**:
```css
.density-dense .slide {
  padding: var(--slide-padding-top) var(--slide-padding-left) var(--slide-padding-bottom) var(--slide-padding-right);
}

.density-dense .content-wrapper {
  max-width: var(--max-content-width);
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: var(--content-gap);
}

.density-dense h1 {
  font-size: var(--headline-size);
  margin-bottom: var(--content-gap-small);
}

.density-dense .grid-4col {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: var(--column-gap);
}

.density-dense .grid-auto {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: var(--column-gap);
}

.density-dense .card {
  padding: var(--card-padding);
  font-size: var(--body-size);
}

.density-dense .stat-number {
  font-size: var(--headline-size);
}

.density-dense table {
  font-size: var(--body-size-small);
}
```

---

## Density CSS Property Summary

| Property | minimal | balanced | dense |
|----------|---------|----------|-------|
| `--slide-padding` | `clamp(48px, 6vw, 96px)` | `clamp(36px, 4vw, 64px)` | `clamp(20px, 2.5vw, 40px)` |
| `--content-gap` | `clamp(24px, 3vw, 48px)` | `clamp(16px, 2vw, 32px)` | `clamp(10px, 1.2vw, 20px)` |
| `--headline-size` | `clamp(2.2rem, 5vw, 4.5rem)` | `clamp(1.8rem, 3.8vw, 3.2rem)` | `clamp(1.4rem, 2.8vw, 2.4rem)` |
| `--headline-size-hero` | `clamp(2.8rem, 6.5vw, 6rem)` | `clamp(2.2rem, 5vw, 4.5rem)` | `clamp(1.8rem, 3.5vw, 3rem)` |
| `--subheadline-size` | `clamp(1.2rem, 2.2vw, 2rem)` | `clamp(1rem, 1.6vw, 1.5rem)` | `clamp(0.9rem, 1.2vw, 1.2rem)` |
| `--body-size` | `clamp(1.1rem, 1.6vw, 1.4rem)` | `clamp(0.95rem, 1.3vw, 1.2rem)` | `clamp(0.8rem, 1vw, 1rem)` |
| `--margin-content` | `15%` | `10%` | `6%` |
| `--grid-gap` | `clamp(36px, 5vw, 72px)` | `clamp(24px, 3vw, 48px)` | `clamp(14px, 1.5vw, 24px)` |
| `--card-padding` | `clamp(32px, 4vw, 56px)` | `clamp(20px, 2.5vw, 36px)` | `clamp(12px, 1.5vw, 24px)` |
| `--icon-size` | `clamp(48px, 5vw, 72px)` | `clamp(36px, 4vw, 56px)` | `clamp(24px, 3vw, 40px)` |
| `--max-columns` | `2` | `3` | `4` |
| `--max-cards` | `2` | `4` | `8` |
| `--max-bullets` | `3` | `5` | `8` |
| `--max-content-width` | `880px` | `1000px` | `1200px` |

---

## Responsive Behavior

All size values use `clamp()` to ensure slides look good at any viewport size:

```
clamp(MIN, PREFERRED, MAX)
      ^^^  ^^^^^^^^^  ^^^
      Phone   Tablet   Desktop/4K
```

- **MIN**: Prevents text from becoming illegibly small on phones
- **PREFERRED**: The `vw` unit scales proportionally with viewport width
- **MAX**: Caps growth on large displays (4K monitors, projector screens)

This means a single HTML file works across:
- Mobile phone browsers (320px+)
- Tablets (768px+)
- Laptops (1366px+)
- Desktop monitors (1920px+)
- 4K displays (3840px+)
- Projectors (typically 1920x1080)

In practice, slides are 16:9 aspect ratio locked via `aspect-ratio: 16/9` on the `.slide` element, and the `vw` units ensure proportional scaling.

---

## Density Selection Heuristic

Choose density based on these factors:

```
Audience expertise:  expert ──────────> beginner
                     (dense)           (minimal)

Slide count:          many ──────────> few
                      (minimal)        (dense)

Content type:         data ──────────> emotional
                      (dense)          (minimal)

Delivery mode:        reference ──────> presented live
                      (dense)          (balanced/minimal)
```

**Rule of thumb**: Start with `balanced`. If slides feel crowded, move to `minimal`. If slides feel sparse, move to `dense`.

---

## Usage in `:root` Block

```css
:root {
  /* === DENSITY: balanced === */
  --density: balanced;
  --slide-padding: clamp(36px, 4vw, 64px);
  --slide-padding-top: clamp(48px, 5vw, 80px);
  --slide-padding-bottom: clamp(36px, 4vw, 64px);
  --slide-padding-left: clamp(36px, 4vw, 64px);
  --slide-padding-right: clamp(36px, 4vw, 64px);
  --content-gap: clamp(16px, 2vw, 32px);
  --content-gap-large: clamp(24px, 3vw, 48px);
  --content-gap-small: clamp(8px, 1vw, 16px);
  --headline-size: clamp(1.8rem, 3.8vw, 3.2rem);
  --headline-size-hero: clamp(2.2rem, 5vw, 4.5rem);
  --subheadline-size: clamp(1rem, 1.6vw, 1.5rem);
  --body-size: clamp(0.95rem, 1.3vw, 1.2rem);
  --body-size-small: clamp(0.8rem, 1vw, 0.95rem);
  --margin-content: 10%;
  --max-content-width: 1000px;
  --grid-gap: clamp(24px, 3vw, 48px);
  --column-gap: clamp(24px, 3vw, 40px);
  --card-padding: clamp(20px, 2.5vw, 36px);
  --card-gap: clamp(16px, 2vw, 28px);
  --icon-size: clamp(36px, 4vw, 56px);
  --bullet-gap: clamp(12px, 1.5vw, 20px);
  --max-bullets: 5;
  --max-columns: 3;
  --max-cards: 4;
}
```
