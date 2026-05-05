# Typography Dimension (CSS Font System)

> Maps the 5 typography options from baoyu-slide-deck to CSS `font-family` declarations using Google Fonts.
> Unlike baoyu-slide-deck (which uses visual descriptions for image generation), peng-slide-deck maps each option
> directly to real web fonts with specific CSS properties for headlines, body text, and monospace elements.

---

## Overview

| Typography | Personality | Headline Font (EN) | Headline Font (ZH) | Body Font | Mono Font |
|------------|-------------|---------------------|--------------------|-----------|-----------|
| `geometric` | Modern, clean, precise | Inter / DM Sans | Noto Sans SC | Noto Sans SC | IBM Plex Mono |
| `humanist` | Warm, friendly, readable | Source Serif 4 | Noto Sans SC | Noto Sans SC | IBM Plex Mono |
| `handwritten` | Personal, organic, playful | Caveat / Klee One | Klee One | Noto Sans SC | IBM Plex Mono |
| `editorial` | Sophisticated, magazine-quality | Playfair Display | Noto Serif SC | Source Serif 4 | IBM Plex Mono |
| `technical` | Precise, data-focused, monospace | JetBrains Mono | Noto Sans SC | IBM Plex Mono | JetBrains Mono |

---

## Typography Definitions

### 1. `geometric` -- Modern Geometric Sans-Serif

**Visual Character**: Clean, rational, constructed. Geometric sans-serifs feature near-perfect circular O shapes and consistent stroke widths. Feels modern, neutral, and highly legible.

**Google Fonts Import**:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,400;0,9..40,500;0,9..40,600;0,9..40,700;1,9..40,400&family=IBM+Plex+Mono:wght@400;500;600&family=Inter:wght@400;500;600;700;800&family=Noto+Sans+SC:wght@400;500;600;700&display=swap" rel="stylesheet">
```

**CSS Variables**:
```css
/* ============================================================
   TYPOGRAPHY: geometric
   ============================================================ */
--typo: geometric;

/* Font families */
--font-headline: 'Inter', 'DM Sans', 'Noto Sans SC', sans-serif;
--font-headline-en: 'Inter', 'DM Sans', sans-serif;
--font-headline-zh: 'Noto Sans SC', sans-serif;
--font-body: 'Noto Sans SC', 'Inter', sans-serif;
--font-body-zh: 'Noto Sans SC', sans-serif;
--font-mono: 'IBM Plex Mono', 'JetBrains Mono', monospace;

/* Headline styling */
--headline-weight: 700;
--headline-style: normal;
--headline-letter-spacing: -0.02em;
--headline-line-height: 1.15;
--headline-text-transform: none;

/* Sub-headline styling */
--subheadline-weight: 600;
--subheadline-letter-spacing: -0.01em;

/* Body styling */
--body-weight: 400;
--body-letter-spacing: 0;
--body-line-height: 1.65;

/* Mono styling */
--mono-weight: 500;
--mono-letter-spacing: 0;
--mono-line-height: 1.5;

/* Google Fonts import URL */
--google-fonts-url: "https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,400;0,9..40,500;0,9..40,600;0,9..40,700;1,9..40,400&family=IBM+Plex+Mono:wght@400;500;600&family=Inter:wght@400;500;600;700;800&family=Noto+Sans+SC:wght@400;500;600;700&display=swap";
```

**Design Notes**:
- Inter is the primary English headline font for its geometric precision and excellent readability at display sizes
- DM Sans is listed as a fallback with similar geometric character
- Negative `letter-spacing` (-0.02em) tightens headline tracking, common in geometric typography
- Use heavier weights for headlines (700+) for clear hierarchy
- Body text uses Noto Sans SC for excellent CJK support with matching geometric character

---

### 2. `humanist` -- Warm Humanist Serif

**Visual Character**: Friendly, organic, bookish. Humanist serifs have subtle stroke variation, angled stress, and open apertures. Feels warm, literary, and highly readable for long texts.

**Google Fonts Import**:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600&family=Noto+Sans+SC:wght@400;500;600;700&family=Source+Serif+4:ital,opsz,wght@0,8..60,400;0,8..60,500;0,8..60,600;0,8..60,700;1,8..60,400;1,8..60,500&display=swap" rel="stylesheet">
```

**CSS Variables**:
```css
/* ============================================================
   TYPOGRAPHY: humanist
   ============================================================ */
--typo: humanist;

/* Font families */
--font-headline: 'Source Serif 4', 'Noto Serif SC', 'Noto Sans SC', serif;
--font-headline-en: 'Source Serif 4', Georgia, serif;
--font-headline-zh: 'Noto Sans SC', sans-serif;
--font-body: 'Noto Sans SC', 'Source Serif 4', sans-serif;
--font-body-zh: 'Noto Sans SC', sans-serif;
--font-mono: 'IBM Plex Mono', 'JetBrains Mono', monospace;

/* Headline styling */
--headline-weight: 600;
--headline-style: normal;
--headline-letter-spacing: -0.005em;
--headline-line-height: 1.2;
--headline-text-transform: none;

/* Sub-headline styling */
--subheadline-weight: 500;
--subheadline-letter-spacing: 0;

/* Body styling */
--body-weight: 400;
--body-letter-spacing: 0;
--body-line-height: 1.7;

/* Mono styling */
--mono-weight: 500;
--mono-letter-spacing: 0;
--mono-line-height: 1.5;

/* Google Fonts import URL */
--google-fonts-url: "https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600&family=Noto+Sans+SC:wght@400;500;600;700&family=Source+Serif+4:ital,opsz,wght@0,8..60,400;0,8..60,500;0,8..60,600;0,8..60,700;1,8..60,400;1,8..60,500&display=swap";
```

**Design Notes**:
- Source Serif 4 headlines bring a warm, bookish quality
- More generous line-height (1.2 headlines, 1.7 body) for comfortable reading
- Headline weight at 600 (semi-bold) rather than 700 -- humanist serifs don't need extreme contrast
- Italian (`italic`) variants available for pull quotes and emphasis
- Body text remains Noto Sans SC for clean CJK rendering; English body can fall back to Source Serif 4

---

### 3. `handwritten` -- Casual Handwritten

**Visual Character**: Personal, organic, playful. Mimics hand-lettering with natural variation in stroke and baseline. Feels intimate, friendly, and unpretentious.

**Google Fonts Import**:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Caveat:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500&family=Klee+One:wght@400;600&family=Noto+Sans+SC:wght@400;500;600;700&display=swap" rel="stylesheet">
```

**CSS Variables**:
```css
/* ============================================================
   TYPOGRAPHY: handwritten
   ============================================================ */
--typo: handwritten;

/* Font families */
--font-headline: 'Caveat', 'Klee One', 'Noto Sans SC', cursive;
--font-headline-en: 'Caveat', 'Comic Sans MS', cursive;
--font-headline-zh: 'Klee One', 'Noto Sans SC', cursive;
--font-body: 'Noto Sans SC', 'Klee One', sans-serif;
--font-body-zh: 'Noto Sans SC', sans-serif;
--font-mono: 'IBM Plex Mono', 'JetBrains Mono', monospace;

/* Headline styling */
--headline-weight: 600;
--headline-style: normal;
--headline-letter-spacing: 0.01em;
--headline-line-height: 1.3;
--headline-text-transform: none;

/* Sub-headline styling */
--subheadline-weight: 500;
--subheadline-letter-spacing: 0.005em;

/* Body styling */
--body-weight: 400;
--body-letter-spacing: 0.005em;
--body-line-height: 1.7;

/* Mono styling */
--mono-weight: 400;
--mono-letter-spacing: 0.01em;
--mono-line-height: 1.5;

/* Google Fonts import URL */
--google-fonts-url: "https://fonts.googleapis.com/css2?family=Caveat:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500&family=Klee+One:wght@400;600&family=Noto+Sans+SC:wght@400;500;600;700&display=swap";
```

**Design Notes**:
- Caveat is the primary English headline font -- it has a natural, marker-pen handwriting feel with organic variation
- Klee One is the ideal Chinese handwritten font -- it mimics brush pen calligraphy with warm, personal character
- Slightly relaxed `letter-spacing` (0.01em) for body text to harmonize with the handwritten aesthetic
- Headlines should use larger sizes (handwriting fonts tend to be smaller at the same font-size)
- Consider scaling headlines up by 10-15% relative to other typography options for readability
- Avoid bold/bold-italic with Caveat -- the 600 weight is sufficient; too heavy looks artificial

---

### 4. `editorial` -- High-Contrast Magazine Serif

**Visual Character**: Sophisticated, dramatic, luxurious. High stroke contrast, elegant serifs, and refined proportions. Feels like a premium magazine spread.

**Google Fonts Import**:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500&family=Noto+Sans+SC:wght@400;500;600;700&family=Noto+Serif+SC:wght@400;500;600;700;900&family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,500;1,600;1,700&family=Source+Serif+4:ital,opsz,wght@0,8..60,400;0,8..60,500;0,8..60,600;1,8..60,400;1,8..60,500&display=swap" rel="stylesheet">
```

**CSS Variables**:
```css
/* ============================================================
   TYPOGRAPHY: editorial
   ============================================================ */
--typo: editorial;

/* Font families */
--font-headline: 'Playfair Display', 'Noto Serif SC', serif;
--font-headline-en: 'Playfair Display', 'Georgia', serif;
--font-headline-zh: 'Noto Serif SC', serif;
--font-body: 'Source Serif 4', 'Noto Serif SC', serif;
--font-body-zh: 'Noto Serif SC', serif;
--font-mono: 'IBM Plex Mono', 'JetBrains Mono', monospace;

/* Headline styling */
--headline-weight: 700;
--headline-style: normal;
--headline-letter-spacing: -0.01em;
--headline-line-height: 1.1;
--headline-text-transform: none;

/* Sub-headline styling */
--subheadline-weight: 600;
--subheadline-letter-spacing: 0.005em;
--subheadline-style: italic;

/* Body styling */
--body-weight: 400;
--body-letter-spacing: 0;
--body-line-height: 1.75;

/* Mono styling */
--mono-weight: 400;
--mono-letter-spacing: 0.02em;
--mono-line-height: 1.5;

/* Google Fonts import URL */
--google-fonts-url: "https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500&family=Noto+Sans+SC:wght@400;500;600;700&family=Noto+Serif+SC:wght@400;500;600;700;900&family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,500;1,600;1,700&family=Source+Serif+4:ital,opsz,wght@0,8..60,400;0,8..60,500;0,8..60,600;1,8..60,400;1,8..60,500&display=swap";
```

**Design Notes**:
- Playfair Display is the hero -- dramatic high-contrast headlines with elegant, refined serifs
- Noto Serif SC provides matching Chinese serif headlines with similar sophistication
- Sub-headlines default to italic for magazine-style deck copy below headlines
- Body text uses Source Serif 4 for comfortable extended reading
- Tight line-height on headlines (1.1) maximizes impact; generous line-height on body (1.75) for readability
- Available weights up to 900 (Black) for maximum impact headlines
- The full italic range (400-700) enables rich typographic hierarchy

---

### 5. `technical` -- Monospace-Forward Technical

**Visual Character**: Precise, systematic, data-oriented. Monospace fonts for headlines create a terminal/code-editor aesthetic. Feels analytical, engineering-focused, and rigorous.

**Google Fonts Import**:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600;700&family=JetBrains+Mono:ital,wght@0,400;0,500;0,600;0,700;0,800;1,400;1,500&family=Noto+Sans+SC:wght@400;500;600;700&display=swap" rel="stylesheet">
```

**CSS Variables**:
```css
/* ============================================================
   TYPOGRAPHY: technical
   ============================================================ */
--typo: technical;

/* Font families */
--font-headline: 'JetBrains Mono', 'Noto Sans SC', monospace;
--font-headline-en: 'JetBrains Mono', 'IBM Plex Mono', monospace;
--font-headline-zh: 'Noto Sans SC', sans-serif;
--font-body: 'IBM Plex Mono', 'Noto Sans SC', monospace;
--font-body-zh: 'Noto Sans SC', sans-serif;
--font-mono: 'JetBrains Mono', 'IBM Plex Mono', monospace;

/* Headline styling */
--headline-weight: 600;
--headline-style: normal;
--headline-letter-spacing: 0;
--headline-line-height: 1.2;
--headline-text-transform: none;

/* Sub-headline styling */
--subheadline-weight: 500;
--subheadline-letter-spacing: 0;
--subheadline-style: normal;

/* Body styling */
--body-weight: 400;
--body-letter-spacing: 0;
--body-line-height: 1.6;
--body-font-feature-settings: "tnum", "ss02";  /* tabular numbers + stylistic set */

/* Mono styling */
--mono-weight: 400;
--mono-letter-spacing: 0;
--mono-line-height: 1.5;
--mono-font-feature-settings: "calt", "liga", "tnum";

/* Google Fonts import URL */
--google-fonts-url: "https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600;700&family=JetBrains+Mono:ital,wght@0,400;0,500;0,600;0,700;0,800;1,400;1,500&family=Noto+Sans+SC:wght@400;500;600;700&display=swap";
```

**Design Notes**:
- JetBrains Mono is the primary headline font -- it has excellent readability for a monospace with distinct letterforms
- The monospace headlines create a distinctive "terminal/code editor" aesthetic perfect for technical content
- Body text also uses IBM Plex Mono for consistency, but with Noto Sans SC fallback for CJK
- `font-feature-settings: "tnum"` enables tabular (monospaced) numbers in body text for aligned data display
- JetBrains Mono includes programming ligatures (`"calt", "liga"`) which can be enabled for code elements
- Avoid excessive letter-spacing -- monospace fonts already have built-in character width
- Headlines should use at least 600 weight to distinguish from body monospace text

---

## Typography CSS Property Summary

| Property | geometric | humanist | handwritten | editorial | technical |
|----------|-----------|----------|-------------|-----------|-----------|
| `--font-headline` | Inter, DM Sans, Noto Sans SC | Source Serif 4, Noto Serif SC | Caveat, Klee One, Noto Sans SC | Playfair Display, Noto Serif SC | JetBrains Mono, Noto Sans SC |
| `--font-body` | Noto Sans SC, Inter | Noto Sans SC, Source Serif 4 | Noto Sans SC, Klee One | Source Serif 4, Noto Serif SC | IBM Plex Mono, Noto Sans SC |
| `--font-mono` | IBM Plex Mono | IBM Plex Mono | IBM Plex Mono | IBM Plex Mono | JetBrains Mono |
| `--headline-weight` | 700 | 600 | 600 | 700 | 600 |
| `--headline-letter-spacing` | -0.02em | -0.005em | 0.01em | -0.01em | 0 |
| `--headline-line-height` | 1.15 | 1.2 | 1.3 | 1.1 | 1.2 |
| `--body-weight` | 400 | 400 | 400 | 400 | 400 |
| `--body-letter-spacing` | 0 | 0 | 0.005em | 0 | 0 |
| `--body-line-height` | 1.65 | 1.7 | 1.7 | 1.75 | 1.6 |

---

## Google Fonts Import Strategy

The Google Fonts import URL is constructed to load only the required fonts for the selected typography option. The import URL is stored in `--google-fonts-url` as a string for reference and documentation. In practice, the HTML template includes:

```html
<!-- Font loading strategy: -->
<!-- 1. Preconnect to Google Fonts for faster initial connection -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<!-- 2. Load the font CSS (URL is replaced at generation time) -->
<!-- GOOGLE_FONTS_HERE -->
<link href="[IMPORT_URL]" rel="stylesheet">

<!-- 3. Local fallback: if Google Fonts is unreachable, system fonts kick in via the font-family stack -->
```

The `--google-fonts-url` in each typography definition contains the complete, ready-to-use URL. At generation time, the workflow replaces `GOOGLE_FONTS_HERE` with the actual `<link>` tag.

---

## Usage in `:root` Block

```css
:root {
  /* === TYPOGRAPHY: geometric === */
  --typo: geometric;
  --font-headline: 'Inter', 'DM Sans', 'Noto Sans SC', sans-serif;
  --font-headline-en: 'Inter', 'DM Sans', sans-serif;
  --font-headline-zh: 'Noto Sans SC', sans-serif;
  --font-body: 'Noto Sans SC', 'Inter', sans-serif;
  --font-body-zh: 'Noto Sans SC', sans-serif;
  --font-mono: 'IBM Plex Mono', 'JetBrains Mono', monospace;
  --headline-weight: 700;
  --headline-style: normal;
  --headline-letter-spacing: -0.02em;
  --headline-line-height: 1.15;
  --headline-text-transform: none;
  --subheadline-weight: 600;
  --subheadline-letter-spacing: -0.01em;
  --body-weight: 400;
  --body-letter-spacing: 0;
  --body-line-height: 1.65;
  --mono-weight: 500;
  --mono-letter-spacing: 0;
  --mono-line-height: 1.5;
  --google-fonts-url: "https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,400;0,9..40,500;0,9..40,600;0,9..40,700;1,9..40,400&family=IBM+Plex+Mono:wght@400;500;600&family=Inter:wght@400;500;600;700;800&family=Noto+Sans+SC:wght@400;500;600;700&display=swap";
}
```

---

## Applying Typography in CSS

```css
/* Headlines */
.slide h1, .slide h2, .slide h3 {
  font-family: var(--font-headline);
  font-weight: var(--headline-weight);
  font-style: var(--headline-style);
  letter-spacing: var(--headline-letter-spacing);
  line-height: var(--headline-line-height);
  text-transform: var(--headline-text-transform);
}

/* Sub-headlines (deck copy) */
.slide .subheadline {
  font-family: var(--font-headline);
  font-weight: var(--subheadline-weight);
  letter-spacing: var(--subheadline-letter-spacing);
}

/* Body text */
.slide p, .slide li, .slide .body-text {
  font-family: var(--font-body);
  font-weight: var(--body-weight);
  letter-spacing: var(--body-letter-spacing);
  line-height: var(--body-line-height);
}

/* Code, data, metadata */
.slide code, .slide pre, .slide .mono, .slide .stat-number {
  font-family: var(--font-mono);
  font-weight: var(--mono-weight);
  letter-spacing: var(--mono-letter-spacing);
  line-height: var(--mono-line-height);
}
```
