# Typography System - Design Tokens
**Voice, Personality, Readability**
**Created:** 2026-01-28

---

## Philosophy

**Typography is voice.** How we say things matters as much as what we say.

- **Native First:** SF Pro on Apple, Inter elsewhere (both feel similar)
- **Scale Matters:** Major Third for headings - musical, harmonious
- **Weight Hierarchy:** Clear distinction between levels
- **Line Length:** 60-75 characters for optimal readability
- **Leading:** Generous for body, tight for display

---

## Font Families

### System Font Stack (Apple-Optimized)

```css
/* Display - Headlines, bold statements */
--font-display: -apple-system, BlinkMacSystemFont, "SF Pro Display",
                 "Inter", "Segoe UI", sans-serif;

/* Body - Readable, neutral */
--font-body: -apple-system, BlinkMacSystemFont, "SF Pro Text",
              "Inter", "Segoe UI", sans-serif;

/* Monospace - Code, data */
--font-mono: -apple-system, BlinkMacSystemFont, "SF Mono",
             "JetBrains Mono", "Fira Code", monospace;
```

### Fallback Stack (Cross-Platform)

```css
--font-stack: -apple-system, BlinkMacSystemFont, "SF Pro Display",
              "Inter var", "Inter", -apple-system, BlinkMacSystemFont,
              "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
```

---

## Type Scale (Major Third)

**Major Third (1.250)** - Musical interval, creates harmony

| Name | Size | Line Height | Weight | Usage |
|------|------|-------------|--------|-------|
| **Display** | | | | |
| display-2xl | 48px | 52px (108%) | 700 | Hero, marketing |
| display-xl | 40px | 44px (110%) | 700 | Page titles |
| display-lg | 32px | 36px (112%) | 700 | Section headers |
| **Heading** | | | | |
| heading-xl | 24px | 28px (116%) | 600 | Card titles |
| heading-lg | 20px | 24px (120%) | 600 | Subsection headers |
| heading-md | 18px | 22px (122%) | 600 | List headers |
| **Body** | | | | |
| body-lg | 16px | 24px (150%) | 400 | Primary body |
| body-md | 14px | 20px (142%) | 400 | Secondary body |
| body-sm | 12px | 16px (133%) | 400 | Caption, helper |
| **Micro** | | | | |
| micro-lg | 11px | 14px (127%) | 500 | Buttons, tabs |
| micro-md | 10px | 13px (130%) | 500 | Labels, tags |
| micro-sm | 9px | 12px (133%) | 500 | Fine print |

---

## Font Weights

```css
--weight-regular: 400;  /* Body text, descriptions */
--weight-medium: 500;   /* Emphasis, UI labels */
--weight-semibold: 600; /* Headings, buttons */
--weight-bold: 700;     /* Display, celebration */
```

### Usage Guidelines

| Weight | When to Use | Examples |
|--------|-------------|----------|
| 400 | Body text, paragraphs | Descriptions, content |
| 500 | Subtle emphasis | Helper text, secondary labels |
| 600 | UI elements, headings | Buttons, card titles |
| 700 | Display, attention | Hero text, celebrations |

---

## Letter Spacing

```css
/* Tight for large text */
--tracking-tighter: -0.025em;  /* Display */
--tracking-tight: -0.01em;     /* Headings */

/* Normal for body */
--tracking-normal: 0;           /* Body text */

/* Wide for emphasis */
--tracking-wide: 0.025em;       /* Uppercase, labels */
--tracking-wider: 0.05em;       /* Buttons, CTAs */
--tracking-widest: 0.1em;       /* Special emphasis */
```

### Usage

| Element | Tracking |
|---------|----------|
| Display text (48px+) | `letter-spacing: -0.025em` |
| Headings (24-32px) | `letter-spacing: -0.01em` |
| Body text | `letter-spacing: 0` |
| Uppercase labels | `letter-spacing: 0.05em` |
| Buttons | `letter-spacing: 0.025em` |

---

## Line Height (Leading)

```css
/* Display - Tight */
--leading-display: 1.1;    /* 48px → 52px */

/* Heading - Moderate */
--leading-heading: 1.2;    /* 24px → 28px */

/* Body - Generous */
--leading-body: 1.5;       /* 16px → 24px */
--leading-compact: 1.4;    /* When space constrained */

/* Captions - Moderate */
--leading-caption: 1.3;    /* 12px → 16px */
```

---

## CSS Variables (Copy-Paste Ready)

```css
:root {
  /* Font Families */
  --font-display: -apple-system, BlinkMacSystemFont, "SF Pro Display", "Inter", sans-serif;
  --font-body: -apple-system, BlinkMacSystemFont, "SF Pro Text", "Inter", sans-serif;
  --font-mono: -apple-system, BlinkMacSystemFont, "SF Mono", "JetBrains Mono", monospace;

  /* Font Sizes */
  --text-display-2xl: 48px;
  --text-display-xl: 40px;
  --text-display-lg: 32px;
  --text-heading-xl: 24px;
  --text-heading-lg: 20px;
  --text-heading-md: 18px;
  --text-body-lg: 16px;
  --text-body-md: 14px;
  --text-body-sm: 12px;
  --text-micro-lg: 11px;
  --text-micro-md: 10px;
  --text-micro-sm: 9px;

  /* Font Weights */
  --font-regular: 400;
  --font-medium: 500;
  --font-semibold: 600;
  --font-bold: 700;

  /* Line Heights */
  --leading-display: 1.1;
  --leading-heading: 1.2;
  --leading-body: 1.5;
  --leading-compact: 1.4;
  --leading-caption: 1.3;

  /* Letter Spacing */
  --tracking-tighter: -0.025em;
  --tracking-tight: -0.01em;
  --tracking-normal: 0;
  --tracking-wide: 0.025em;
  --tracking-wider: 0.05em;
}
```

---

## Tailwind Config (Copy-Paste Ready)

```javascript
module.exports = {
  theme: {
    extend: {
      fontFamily: {
        display: ['SF Pro Display', 'Inter', 'sans-serif'],
        body: ['SF Pro Text', 'Inter', 'sans-serif'],
        mono: ['SF Mono', 'JetBrains Mono', 'monospace'],
      },
      fontSize: {
        // Display
        'display-2xl': ['48px', { lineHeight: '1.1', letterSpacing: '-0.025em', fontWeight: '700' }],
        'display-xl': ['40px', { lineHeight: '1.1', letterSpacing: '-0.01em', fontWeight: '700' }],
        'display-lg': ['32px', { lineHeight: '1.125', letterSpacing: '-0.01em', fontWeight: '700' }],

        // Heading
        'heading-xl': ['24px', { lineHeight: '1.16', letterSpacing: '-0.01em', fontWeight: '600' }],
        'heading-lg': ['20px', { lineHeight: '1.2', letterSpacing: '-0.01em', fontWeight: '600' }],
        'heading-md': ['18px', { lineHeight: '1.22', letterSpacing: '0', fontWeight: '600' }],

        // Body
        'body-lg': ['16px', { lineHeight: '1.5', letterSpacing: '0', fontWeight: '400' }],
        'body-md': ['14px', { lineHeight: '1.42', letterSpacing: '0', fontWeight: '400' }],
        'body-sm': ['12px', { lineHeight: '1.33', letterSpacing: '0', fontWeight: '400' }],

        // Micro
        'micro-lg': ['11px', { lineHeight: '1.27', letterSpacing: '0.01em', fontWeight: '500' }],
        'micro-md': ['10px', { lineHeight: '1.3', letterSpacing: '0.025em', fontWeight: '500' }],
        'micro-sm': ['9px', { lineHeight: '1.33', letterSpacing: '0.025em', fontWeight: '500' }],
      },
      letterSpacing: {
        tighter: '-0.025em',
        tight: '-0.01em',
        normal: '0',
        wide: '0.025em',
        wider: '0.05em',
        widest: '0.1em',
      },
      lineHeight: {
        display: '1.1',
        heading: '1.2',
        body: '1.5',
        compact: '1.4',
        caption: '1.3',
      },
    },
  },
};
```

---

## Typography Components

### Headings

```css
.heading-xl {
  font-family: var(--font-display);
  font-size: var(--text-heading-xl);
  font-weight: var(--font-semibold);
  line-height: var(--leading-heading);
  letter-spacing: var(--tracking-tight);
}

.heading-lg {
  font-family: var(--font-display);
  font-size: var(--text-heading-lg);
  font-weight: var(--font-semibold);
  line-height: var(--leading-heading);
  letter-spacing: var(--tracking-tight);
}
```

### Body Text

```css
.body {
  font-family: var(--font-body);
  font-size: var(--text-body-lg);
  font-weight: var(--font-regular);
  line-height: var(--leading-body);
  letter-spacing: var(--tracking-normal);
}

.body-small {
  font-family: var(--font-body);
  font-size: var(--text-body-md);
  font-weight: var(--font-regular);
  line-height: var(--leading-compact);
  letter-spacing: var(--tracking-normal);
}
```

### Display Text

```css
.display-hero {
  font-family: var(--font-display);
  font-size: var(--text-display-2xl);
  font-weight: var(--font-bold);
  line-height: var(--leading-display);
  letter-spacing: var(--tracking-tighter);
}
```

---

## Responsive Typography

**Mobile-First Approach:**

| Breakpoint | Base (Mobile) | Tablet | Desktop |
|------------|---------------|--------|---------|
| Display Hero | 32px | 40px | 48px |
| Heading XL | 20px | 22px | 24px |
| Body Large | 16px | 16px | 18px |
| Body Small | 14px | 14px | 14px |

```css
/* Mobile default */
.display-hero {
  font-size: 32px;
}

/* Tablet */
@media (min-width: 768px) {
  .display-hero {
    font-size: 40px;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .display-hero {
    font-size: 48px;
  }
}
```

---

## Special Typography

### Celebration Text

```css
.celebration-text {
  font-family: var(--font-display);
  font-size: var(--text-display-lg);
  font-weight: var(--font-bold);
  background: var(--gradient-party);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

### Gradient Text

```css
.gradient-text {
  background: var(--gradient-taskflow);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

### Monospace for Data

```css
.data-text {
  font-family: var(--font-mono);
  font-size: var(--text-body-md);
  font-weight: var(--font-medium);
  letter-spacing: var(--tracking-wide);
}
```

---

## Accessibility

### Minimum Readable Sizes

| Context | Minimum Size |
|---------|--------------|
| Body text | 14px (16px recommended) |
| Form labels | 12px (14px recommended) |
| Captions | 11px |
| Fine print | 9px (with warning) |

### Contrast Requirements

- **WCAG AA:** 4.5:1 for normal text, 3:1 for large text (18px+)
- **WCAG AAA:** 7:1 for normal text, 4.5:1 for large text

### Font Smoothing

```css
/* Improve rendering on macOS */
body {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
```

---

## Usage Guidelines

### DO:
- Use semantic HTML (h1-h6, p, strong, em)
- Maintain clear hierarchy
- Keep line length 60-75 characters
- Use appropriate font weights for meaning

### DON'T:
- Use bold for entire paragraphs
- Use display fonts for long text
- Stretch text horizontally
- Use all caps for body text

---

## Copywriting Voice Guidelines

| Context | Tone | Example |
|---------|------|---------|
| **Celebrations** | Enthusiastic, personal | "You crushed it!" |
| **Empty States** | Encouraging, not sad | "Your first win awaits!" |
| **Errors** | Helpful, not blaming | "Let's fix this together" |
| **Success** | Validating, warm | "Look how far you've come" |
| **Onboarding** | Friendly, brief | "Let's get you set up" |
| **Settings** | Clear, functional | Each label describes exactly what it does |

---

*Last updated: 2026-01-28*
*Status: FINAL*
