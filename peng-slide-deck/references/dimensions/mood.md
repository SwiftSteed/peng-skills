# Mood Dimension (CSS Color Palette System)

> Maps the 7 mood options from baoyu-slide-deck to complete CSS color palettes.
> Each mood defines a full set of CSS custom properties for backgrounds, text, accents, and surface colors.
> Hex values are sourced from the original baoyu-slide-deck mood definitions.

---

## Overview

| Mood | Character | Palette Anchor | Best For |
|------|-----------|----------------|----------|
| `professional` | Cool-neutral, authoritative | Navy + Gold | Investor decks, corporate proposals, executive summaries |
| `warm` | Warm, earthy, approachable | Off-White + Soft Orange | Lifestyle, wellness, education, storytelling |
| `macaron` | Soft, candy-like pastels | Warm Cream + Coral Red | Education, children's content, creative workshops |
| `cool` | Clean, technical, precise | Blueprint White + Engineering Blue | Architecture, engineering, data, research |
| `vibrant` | Bold, high-energy, loud | Coral Red + Deep Blue | Product launches, creative pitches, marketing |
| `dark` | Sleek, dramatic, nocturnal | Deep Black + Bright Blue | Entertainment, gaming, night events, tech demos |
| `neutral` | Minimal, grayscale, timeless | Pure White + Near Black | Executive briefings, minimal portfolios, any content |

---

## Mood Color Palettes

### 1. `professional` -- Navy + Gold

**Personality**: Trustworthy, established, refined. The gold accent adds warmth and prestige to the structured navy foundation.

```css
/* ============================================================
   MOOD: professional
   ============================================================ */
--mood: professional;

/* Primary surfaces */
--bg-primary: #1E3A5F;
--bg-primary-rgb: 30, 58, 95;
--bg-secondary: #F5F7FA;
--bg-secondary-rgb: 245, 247, 250;

/* Text */
--text-primary: #1E3A5F;
--text-primary-rgb: 30, 58, 95;
--text-secondary: #5A6B7F;
--text-secondary-rgb: 90, 107, 127;

/* Accents */
--accent-1: #C9A227;
--accent-1-rgb: 201, 162, 39;
--accent-2: #2E5C8A;
--accent-2-rgb: 46, 92, 138;
--accent-3: #D4AF37;
--accent-3-rgb: 212, 175, 55;

/* Light/dark extremes */
--paper: #FFFFFF;
--paper-rgb: 255, 255, 255;
--paper-tint: #F7F9FC;
--ink: #0A1929;
--ink-rgb: 10, 25, 41;
--ink-tint: #112240;

/* Functional */
--success: #2E7D32;
--success-rgb: 46, 125, 50;
--warning: #F57C00;
--warning-rgb: 245, 124, 0;
--error: #C62828;
--error-rgb: 198, 40, 40;
--info: #1565C0;
--info-rgb: 21, 101, 192;

/* Surface hierarchy (for cards, callouts, etc.) */
--surface-1: #FFFFFF;
--surface-2: #F5F7FA;
--surface-3: #EBEFF5;
--surface-ink: #1E3A5F;
```

**Light slide** (default): `background-color: var(--paper)` (white), `color: var(--text-primary)` (navy).
**Dark slide**: `background-color: var(--bg-primary)` (navy #1E3A5F), `color: var(--paper)` (white). Gold accents pop on both.

---

### 2. `warm` -- Off-White + Soft Orange

**Personality**: Inviting, organic, gentle. Feels handcrafted and personal. Orange accents add energy without aggression.

```css
/* ============================================================
   MOOD: warm
   ============================================================ */
--mood: warm;

/* Primary surfaces */
--bg-primary: #FAF8F0;
--bg-primary-rgb: 250, 248, 240;
--bg-secondary: #FFFDF7;
--bg-secondary-rgb: 255, 253, 247;

/* Text */
--text-primary: #3D2E1C;
--text-primary-rgb: 61, 46, 28;
--text-secondary: #7A6E5D;
--text-secondary-rgb: 122, 110, 93;

/* Accents */
--accent-1: #F4A261;
--accent-1-rgb: 244, 162, 97;
--accent-2: #E76F51;
--accent-2-rgb: 231, 111, 81;
--accent-3: #E9C46A;
--accent-3-rgb: 233, 196, 106;

/* Light/dark extremes */
--paper: #FAF8F0;
--paper-rgb: 250, 248, 240;
--paper-tint: #F5F0E0;
--ink: #2C1810;
--ink-rgb: 44, 24, 16;
--ink-tint: #3D2E1C;

/* Functional */
--success: #5B8C5A;
--success-rgb: 91, 140, 90;
--warning: #F4A261;
--warning-rgb: 244, 162, 97;
--error: #D64045;
--error-rgb: 214, 64, 69;
--info: #5FA8D4;
--info-rgb: 95, 168, 212;

/* Surface hierarchy */
--surface-1: #FFFFFF;
--surface-2: #FAF8F0;
--surface-3: #F0EBE0;
--surface-ink: #3D2E1C;
```

**Light slide** (default): `background-color: var(--paper)` (warm off-white #FAF8F0), `color: var(--text-primary)` (dark brown).
**Dark slide**: `background-color: var(--ink-tint)` (#3D2E1C), `color: var(--paper)`.

---

### 3. `macaron` -- Warm Cream + Pastels

**Personality**: Soft, sweet, playful. Pastel candy colors evoking French macarons. Gentle and approachable.

```css
/* ============================================================
   MOOD: macaron
   ============================================================ */
--mood: macaron;

/* Primary surfaces */
--bg-primary: #F5F0E8;
--bg-primary-rgb: 245, 240, 232;
--bg-secondary: #FFFAF5;
--bg-secondary-rgb: 255, 250, 245;

/* Text */
--text-primary: #4A3F35;
--text-primary-rgb: 74, 63, 53;
--text-secondary: #8B7E6F;
--text-secondary-rgb: 139, 126, 111;

/* Accents */
--accent-1: #E8655A;
--accent-1-rgb: 232, 101, 90;
--accent-2: #A8D8EA;
--accent-2-rgb: 168, 216, 234;
--accent-3: #C3A5D8;
--accent-3-rgb: 195, 165, 216;

/* Light/dark extremes */
--paper: #F5F0E8;
--paper-rgb: 245, 240, 232;
--paper-tint: #EDE5D8;
--ink: #3D3226;
--ink-rgb: 61, 50, 38;
--ink-tint: #4A3F35;

/* Additional pastels for decorative use */
--pastel-mint: #B5EAD7;
--pastel-mint-rgb: 181, 234, 215;
--pastel-peach: #FFD3B6;
--pastel-peach-rgb: 255, 211, 182;
--pastel-lavender: #D5C6E0;
--pastel-lavender-rgb: 213, 198, 224;
--pastel-yellow: #FFF1C1;
--pastel-yellow-rgb: 255, 241, 193;

/* Functional */
--success: #7BC4A0;
--success-rgb: 123, 196, 160;
--warning: #FFB88C;
--warning-rgb: 255, 184, 140;
--error: #E8655A;
--error-rgb: 232, 101, 90;
--info: #A8D8EA;
--info-rgb: 168, 216, 234;

/* Surface hierarchy */
--surface-1: #FFFFFF;
--surface-2: #F5F0E8;
--surface-3: #EDE0D5;
--surface-ink: #4A3F35;
```

**Light slide** (default): `background-color: var(--paper)` (warm cream #F5F0E8), `color: var(--text-primary)`.
**Dark slide**: `background-color: var(--ink-tint)` (#4A3F35), `color: var(--paper)`.

---

### 4. `cool` -- Blueprint White + Engineering Blue

**Personality**: Clean, analytical, trustworthy. The blueprint-inspired off-white with crisp blue accents creates a technical, precise atmosphere.

```css
/* ============================================================
   MOOD: cool
   ============================================================ */
--mood: cool;

/* Primary surfaces */
--bg-primary: #2563EB;
--bg-primary-rgb: 37, 99, 235;
--bg-secondary: #FAF8F5;
--bg-secondary-rgb: 250, 248, 245;

/* Text */
--text-primary: #1E293B;
--text-primary-rgb: 30, 41, 59;
--text-secondary: #64748B;
--text-secondary-rgb: 100, 116, 139;

/* Accents */
--accent-1: #2563EB;
--accent-1-rgb: 37, 99, 235;
--accent-2: #0891B2;
--accent-2-rgb: 8, 145, 178;
--accent-3: #6366F1;
--accent-3-rgb: 99, 102, 241;

/* Light/dark extremes */
--paper: #FAF8F5;
--paper-rgb: 250, 248, 245;
--paper-tint: #F0F4FF;
--ink: #0F172A;
--ink-rgb: 15, 23, 42;
--ink-tint: #1E293B;

/* Functional */
--success: #10B981;
--success-rgb: 16, 185, 129;
--warning: #F59E0B;
--warning-rgb: 245, 158, 11;
--error: #EF4444;
--error-rgb: 239, 68, 68;
--info: #3B82F6;
--info-rgb: 59, 130, 246;

/* Surface hierarchy */
--surface-1: #FFFFFF;
--surface-2: #FAF8F5;
--surface-3: #F0EEF8;
--surface-ink: #1E293B;
```

**Light slide** (default): `background-color: var(--paper)` (blueprint off-white #FAF8F5), `color: var(--text-primary)`.
**Dark slide**: `background-color: var(--text-primary)` (#1E293B, slate), `color: var(--paper)`.

---

### 5. `vibrant` -- Coral Red + Deep Blue

**Personality**: Energetic, bold, attention-grabbing. High saturation, high contrast. Makes a statement.

```css
/* ============================================================
   MOOD: vibrant
   ============================================================ */
--mood: vibrant;

/* Primary surfaces */
--bg-primary: #E94560;
--bg-primary-rgb: 233, 69, 96;
--bg-secondary: #FFFFFF;
--bg-secondary-rgb: 255, 255, 255;

/* Text */
--text-primary: #0F3460;
--text-primary-rgb: 15, 52, 96;
--text-secondary: #5C6B7E;
--text-secondary-rgb: 92, 107, 126;

/* Accents */
--accent-1: #E94560;
--accent-1-rgb: 233, 69, 96;
--accent-2: #16C79A;
--accent-2-rgb: 22, 199, 154;
--accent-3: #F5C518;
--accent-3-rgb: 245, 197, 24;

/* Light/dark extremes */
--paper: #FFFFFF;
--paper-rgb: 255, 255, 255;
--paper-tint: #FFF5F5;
--ink: #0F3460;
--ink-rgb: 15, 52, 96;
--ink-tint: #162B48;

/* Functional */
--success: #16C79A;
--success-rgb: 22, 199, 154;
--warning: #F5C518;
--warning-rgb: 245, 197, 24;
--error: #E94560;
--error-rgb: 233, 69, 96;
--info: #5DADE2;
--info-rgb: 93, 173, 226;

/* Surface hierarchy */
--surface-1: #FFFFFF;
--surface-2: #FFF5F5;
--surface-3: #FFE8EC;
--surface-ink: #0F3460;
```

**Light slide** (default): `background-color: var(--paper)` (white), `color: var(--text-primary)` (deep blue).
**Dark slide**: `background-color: var(--ink)` (deep blue #0F3460), `color: var(--paper)` (white). Coral accent #E94560 pops dramatically on both.

---

### 6. `dark` -- Deep Black + Bright Blue

**Personality**: Dramatic, modern, nocturnal. High contrast dark backgrounds with luminous blue accents. Feels premium and futuristic.

```css
/* ============================================================
   MOOD: dark
   ============================================================ */
--mood: dark;

/* Primary surfaces */
--bg-primary: #0D1117;
--bg-primary-rgb: 13, 17, 23;
--bg-secondary: #161B22;
--bg-secondary-rgb: 22, 27, 34;

/* Text */
--text-primary: #F0F6FC;
--text-primary-rgb: 240, 246, 252;
--text-secondary: #8B949E;
--text-secondary-rgb: 139, 148, 158;

/* Accents */
--accent-1: #58A6FF;
--accent-1-rgb: 88, 166, 255;
--accent-2: #3FB950;
--accent-2-rgb: 63, 185, 80;
--accent-3: #D2991D;
--accent-3-rgb: 210, 153, 29;

/* Light/dark extremes */
--paper: #F0F6FC;
--paper-rgb: 240, 246, 252;
--paper-tint: #C9D1D9;
--ink: #0D1117;
--ink-rgb: 13, 17, 23;
--ink-tint: #161B22;

/* Functional */
--success: #3FB950;
--success-rgb: 63, 185, 80;
--warning: #D2991D;
--warning-rgb: 210, 153, 29;
--error: #F85149;
--error-rgb: 248, 81, 73;
--info: #58A6FF;
--info-rgb: 88, 166, 255;

/* Surface hierarchy */
--surface-1: #0D1117;
--surface-2: #161B22;
--surface-3: #21262D;
--surface-ink: #F0F6FC;
```

**Default slide**: `background-color: var(--ink)` (deep black #0D1117), `color: var(--text-primary)` (near-white).
**Light slide** (reverse): `background-color: var(--bg-secondary)` (#161B22, still dark), `color: var(--text-primary)`.

> Note: `dark` mood defaults to dark slides. The `--paper` variable holds the lightest color for text/icons on dark backgrounds.

---

### 7. `neutral` -- Pure White + Near Black

**Personality**: Minimal, timeless, universal. Pure grayscale with no color bias. The blank canvas that works for any content.

```css
/* ============================================================
   MOOD: neutral
   ============================================================ */
--mood: neutral;

/* Primary surfaces */
--bg-primary: #FFFFFF;
--bg-primary-rgb: 255, 255, 255;
--bg-secondary: #FAFAFA;
--bg-secondary-rgb: 250, 250, 250;

/* Text */
--text-primary: #18181B;
--text-primary-rgb: 24, 24, 27;
--text-secondary: #71717A;
--text-secondary-rgb: 113, 113, 122;

/* Accents */
--accent-1: #18181B;
--accent-1-rgb: 24, 24, 27;
--accent-2: #3F3F46;
--accent-2-rgb: 63, 63, 70;
--accent-3: #A1A1AA;
--accent-3-rgb: 161, 161, 170;

/* Light/dark extremes */
--paper: #FFFFFF;
--paper-rgb: 255, 255, 255;
--paper-tint: #FAFAFA;
--ink: #18181B;
--ink-rgb: 24, 24, 27;
--ink-tint: #27272A;

/* Functional */
--success: #22C55E;
--success-rgb: 34, 197, 94;
--warning: #F59E0B;
--warning-rgb: 245, 158, 11;
--error: #EF4444;
--error-rgb: 239, 68, 68;
--info: #3B82F6;
--info-rgb: 59, 130, 246;

/* Surface hierarchy */
--surface-1: #FFFFFF;
--surface-2: #FAFAFA;
--surface-3: #F4F4F5;
--surface-ink: #18181B;
```

**Light slide** (default): `background-color: var(--paper)` (white #FFFFFF), `color: var(--text-primary)` (near-black).
**Dark slide**: `background-color: var(--ink)` (near-black #18181B), `color: var(--paper)` (white).

---

## Mood Color Reference Table

| Variable | professional | warm | macaron | cool | vibrant | dark | neutral |
|----------|-------------|------|---------|------|---------|------|---------|
| `--paper` | `#FFFFFF` | `#FAF8F0` | `#F5F0E8` | `#FAF8F5` | `#FFFFFF` | `#F0F6FC` | `#FFFFFF` |
| `--paper-tint` | `#F7F9FC` | `#F5F0E0` | `#EDE5D8` | `#F0F4FF` | `#FFF5F5` | `#C9D1D9` | `#FAFAFA` |
| `--ink` | `#0A1929` | `#2C1810` | `#3D3226` | `#0F172A` | `#0F3460` | `#0D1117` | `#18181B` |
| `--ink-tint` | `#112240` | `#3D2E1C` | `#4A3F35` | `#1E293B` | `#162B48` | `#161B22` | `#27272A` |
| `--text-primary` | `#1E3A5F` | `#3D2E1C` | `#4A3F35` | `#1E293B` | `#0F3460` | `#F0F6FC` | `#18181B` |
| `--text-secondary` | `#5A6B7F` | `#7A6E5D` | `#8B7E6F` | `#64748B` | `#5C6B7E` | `#8B949E` | `#71717A` |
| `--accent-1` | `#C9A227` | `#F4A261` | `#E8655A` | `#2563EB` | `#E94560` | `#58A6FF` | `#18181B` |
| `--accent-2` | `#2E5C8A` | `#E76F51` | `#A8D8EA` | `#0891B2` | `#16C79A` | `#3FB950` | `#3F3F46` |
| `--accent-3` | `#D4AF37` | `#E9C46A` | `#C3A5D8` | `#6366F1` | `#F5C518` | `#D2991D` | `#A1A1AA` |
| `--bg-primary` | `#1E3A5F` | `#FAF8F0` | `#F5F0E8` | `#2563EB` | `#E94560` | `#0D1117` | `#FFFFFF` |
| `--bg-secondary` | `#F5F7FA` | `#FFFDF7` | `#FFFAF5` | `#FAF8F5` | `#FFFFFF` | `#161B22` | `#FAFAFA` |

---

## Light vs. Dark Slide Behavior

Each mood defines which surface is the default slide background and whether it leans light or dark:

| Mood | Default Background | Light/Dark | Text Color on Default |
|------|-------------------|------------|----------------------|
| `professional` | `--paper` (#FFFFFF) | Light | `--text-primary` (#1E3A5F) |
| `warm` | `--paper` (#FAF8F0) | Light | `--text-primary` (#3D2E1C) |
| `macaron` | `--paper` (#F5F0E8) | Light | `--text-primary` (#4A3F35) |
| `cool` | `--paper` (#FAF8F5) | Light | `--text-primary` (#1E293B) |
| `vibrant` | `--paper` (#FFFFFF) | Light | `--text-primary` (#0F3460) |
| `dark` | `--ink` (#0D1117) | **Dark** | `--text-primary` (#F0F6FC) |
| `neutral` | `--paper` (#FFFFFF) | Light | `--text-primary` (#18181B) |

For individual slides that invert (e.g., a dark hero slide in a light deck), toggle between `--paper` and `--ink` backgrounds, and between `--text-primary` (light-mode text) and `--paper` (dark-mode text = light color).

---

## Usage in `:root` Block

```css
:root {
  /* === MOOD: professional === */
  --mood: professional;
  --bg-primary: #1E3A5F;
  --bg-primary-rgb: 30, 58, 95;
  --bg-secondary: #F5F7FA;
  --bg-secondary-rgb: 245, 247, 250;
  --text-primary: #1E3A5F;
  --text-primary-rgb: 30, 58, 95;
  --text-secondary: #5A6B7F;
  --text-secondary-rgb: 90, 107, 127;
  --accent-1: #C9A227;
  --accent-1-rgb: 201, 162, 39;
  --accent-2: #2E5C8A;
  --accent-2-rgb: 46, 92, 138;
  --accent-3: #D4AF37;
  --accent-3-rgb: 212, 175, 55;
  --paper: #FFFFFF;
  --paper-rgb: 255, 255, 255;
  --paper-tint: #F7F9FC;
  --ink: #0A1929;
  --ink-rgb: 10, 25, 41;
  --ink-tint: #112240;
  /* ... success/warning/error/info, surfaces ... */
}
```

For dark slides, use the RGB versions with `rgba()` for flexible opacity control:
```css
.dark-slide {
  background-color: var(--ink);
  color: var(--paper);
  --current-text-rgb: var(--paper-rgb);
}
```
