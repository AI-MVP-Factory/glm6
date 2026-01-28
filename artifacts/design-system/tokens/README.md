# Design Tokens - Complete Reference
**Emotional Design System for SOLO Products**
**Created:** 2026-01-28
**Version:** 1.0.0

---

## Overview

This design system provides the visual language for all SOLO products. Every token is designed to evoke specific emotions and create delightful user experiences.

**Products using this system:**
- TaskFlow v3 - Productivity that celebrates
- TeenPopTastic (Vibe) - Music that connects
- MemeCraftVibe - Memes that delight

---

## Token Categories

| Category | File | Purpose |
|----------|------|---------|
| **Colors** | `colors.md` | Emotional color system, OLED-optimized |
| **Typography** | `typography.md` | Font scales, weights, readable text |
| **Spacing** | `spacing.md` | 4px grid, breathing room, rhythm |
| **Borders & Shadows** | `borders-shadows.md` | Depth, elevation, effects |

---

## Quick Reference

### Color Palette

| Purpose | Light | Dark |
|---------|-------|------|
| **Background** | #ffffff | #000000 |
| **Surface** | #f4f4f5 | #0a0a0a |
| **Text Primary** | #18181b | #fafafa |
| **Text Secondary** | #52525b | #a1a1aa |
| **Border** | #d4d4d8 | rgba(255,255,255,0.1) |

### Brand Colors

| App | Primary | Gradient |
|-----|---------|----------|
| **TaskFlow** | #a855f7 | Purple → Indigo |
| **Vibe** | #ec4899 | Pink → Purple |
| **MemeCraft** | #22d3ee | Cyan → Indigo |

### Typography Scale

| Name | Size | Weight | Usage |
|------|------|--------|-------|
| Display 2XL | 48px | 700 | Hero titles |
| Heading XL | 24px | 600 | Card titles |
| Body Large | 16px | 400 | Primary text |
| Body Small | 14px | 400 | Secondary text |
| Micro | 11px | 500 | Labels, buttons |

### Spacing Scale

| Name | Value | Usage |
|------|-------|-------|
| XS | 4px | Icon + text gaps |
| SM | 8px | Compact spacing |
| MD | 16px | Default padding |
| LG | 24px | Section spacing |
| XL | 32px | Large sections |
| 2XL | 48px | Page sections |

### Border Radius

| Name | Value | Usage |
|------|-------|-------|
| SM | 4px | Buttons, tags |
| MD | 8px | Cards (default) |
| LG | 12px | Modals |
| Full | 9999px | Pills, badges |

---

## CSS Variables (All-in-One)

```css
:root {
  /* ===== COLORS ===== */
  --taskflow-primary: #a855f7;
  --vibe-primary-pink: #ec4899;
  --vibe-primary-purple: #8b5cf6;
  --meme-primary-cyan: #22d3ee;
  --meme-primary-indigo: #6366f1;

  --success: #eab308;
  --error: #f43f5e;
  --warning: #f59e0b;
  --info: #0ea5e9;
  --celebration: #fbbf24;

  /* Dark Mode (Default) */
  --bg-base: #000000;
  --bg-surface: #0a0a0a;
  --bg-card: #141414;
  --text-primary: #fafafa;
  --text-secondary: #a1a1aa;
  --text-tertiary: #71717a;
  --border-default: rgba(255, 255, 255, 0.1);

  /* ===== TYPOGRAPHY ===== */
  --font-display: "SF Pro Display", "Inter", sans-serif;
  --font-body: "SF Pro Text", "Inter", sans-serif;
  --font-mono: "SF Mono", "JetBrains Mono", monospace;

  --text-display-2xl: 48px;
  --text-display-xl: 40px;
  --text-display-lg: 32px;
  --text-heading-xl: 24px;
  --text-heading-lg: 20px;
  --text-heading-md: 18px;
  --text-body-lg: 16px;
  --text-body-md: 14px;
  --text-body-sm: 12px;

  --font-regular: 400;
  --font-medium: 500;
  --font-semibold: 600;
  --font-bold: 700;

  --leading-display: 1.1;
  --leading-heading: 1.2;
  --leading-body: 1.5;

  /* ===== SPACING ===== */
  --spacing-xs: 4px;
  --spacing-sm: 8px;
  --spacing-md: 16px;
  --spacing-lg: 24px;
  --spacing-xl: 32px;
  --spacing-2xl: 48px;

  /* ===== BORDERS & SHADOWS ===== */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-xl: 16px;
  --radius-full: 9999px;

  --border-subtle: 1px solid rgba(255, 255, 255, 0.05);
  --border-default: 1px solid rgba(255, 255, 255, 0.1);

  --elevation-1: 0 0 0 1px rgba(255, 255, 255, 0.05);
  --elevation-2: 0 0 0 1px rgba(255, 255, 255, 0.08);
  --elevation-3: 0 0 0 1px rgba(255, 255, 255, 0.12);

  --glow-primary: 0 0 20px rgba(168, 85, 247, 0.4);
  --glow-gold: 0 0 20px rgba(251, 191, 36, 0.5);
}

/* Light Mode */
@media (prefers-color-scheme: light) {
  :root {
    --bg-base: #ffffff;
    --bg-surface: #fafafa;
    --bg-card: #f4f4f5;
    --text-primary: #18181b;
    --text-secondary: #52525b;
    --text-tertiary: #71717a;
    --border-default: #d4d4d8;
  }
}
```

---

## Tailwind Config (Complete)

```javascript
// tailwind.config.js
module.exports = {
  darkMode: 'class', // or 'media'
  theme: {
    extend: {
      colors: {
        // TaskFlow
        taskflow: {
          50: '#faf5ff',
          100: '#f3e8ff',
          200: '#e9d5ff',
          300: '#d8b4fe',
          400: '#c084fc',
          500: '#a855f7',
          600: '#9333ea',
          700: '#7e22ce',
          800: '#6b21a8',
          900: '#581c87',
        },
        // Vibe
        vibe: {
          pink: '#ec4899',
          purple: '#8b5cf6',
          accent: '#fbbf24',
        },
        // MemeCraft
        meme: {
          cyan: '#22d3ee',
          indigo: '#6366f1',
          accent: '#f59e0b',
        },
        // Semantic
        success: '#eab308',
        error: '#f43f5e',
        warning: '#f59e0b',
        info: '#0ea5e9',
        celebration: '#fbbf24',
        // OLED Neutrals
        neutral: {
          950: '#000000',
          900: '#0a0a0a',
          800: '#141414',
          700: '#1c1c1c',
          600: '#262626',
          500: '#404040',
          400: '#71717a',
          300: '#a1a1aa',
          200: '#d4d4d8',
          100: '#e4e4e7',
          50: '#f4f4f5',
        },
      },
      fontFamily: {
        display: ['SF Pro Display', 'Inter', 'sans-serif'],
        body: ['SF Pro Text', 'Inter', 'sans-serif'],
        mono: ['SF Mono', 'JetBrains Mono', 'monospace'],
      },
      fontSize: {
        'display-2xl': ['48px', { lineHeight: '1.1', fontWeight: '700' }],
        'display-xl': ['40px', { lineHeight: '1.1', fontWeight: '700' }],
        'display-lg': ['32px', { lineHeight: '1.125', fontWeight: '700' }],
        'heading-xl': ['24px', { lineHeight: '1.16', fontWeight: '600' }],
        'heading-lg': ['20px', { lineHeight: '1.2', fontWeight: '600' }],
        'heading-md': ['18px', { lineHeight: '1.22', fontWeight: '600' }],
        'body-lg': ['16px', { lineHeight: '1.5', fontWeight: '400' }],
        'body-md': ['14px', { lineHeight: '1.42', fontWeight: '400' }],
        'body-sm': ['12px', { lineHeight: '1.33', fontWeight: '400' }],
        'micro-lg': ['11px', { lineHeight: '1.27', fontWeight: '500' }],
        'micro-md': ['10px', { lineHeight: '1.3', fontWeight: '500' }],
      },
      spacing: {
        18: '4.5rem', // 72px
        22: '5.5rem', // 88px
        88: '22rem',  // 352px
        128: '32rem', // 512px
      },
      borderRadius: {
        '4xl': '36px',
      },
      boxShadow: {
        'elevation-1': '0 0 0 1px rgba(255, 255, 255, 0.05)',
        'elevation-2': '0 0 0 1px rgba(255, 255, 255, 0.08)',
        'elevation-3': '0 0 0 1px rgba(255, 255, 255, 0.12)',
        'glow-primary': '0 0 20px rgba(168, 85, 247, 0.4)',
        'glow-gold': '0 0 20px rgba(251, 191, 36, 0.5)',
      },
      backgroundImage: {
        'gradient-taskflow': 'linear-gradient(135deg, #a855f7 0%, #6366f1 100%)',
        'gradient-vibe': 'linear-gradient(135deg, #ec4899 0%, #8b5cf6 100%)',
        'gradient-meme': 'linear-gradient(135deg, #22d3ee 0%, #6366f1 100%)',
        'gradient-party': 'linear-gradient(135deg, #ec4899 0%, #8b5cf6 50%, #22d3ee 100%)',
      },
    },
  },
  plugins: [
    require('@tailwindcss/forms'),
    require('@tailwindcss/typography'),
  ],
};
```

---

## Design Principles

### 1. Emotional First
Every design decision answers: "How should this make the user feel?"

### 2. Dark-First
OLED black saves battery, looks premium, reduces eye strain

### 3. Generous Spacing
White space is luxury, not waste

### 4. Native Feel
Use system fonts, respect platform conventions

### 5. Accessible Always
WCAG AA minimum, AAA where possible

---

## Implementation Checklist

When starting a new project:

- [ ] Copy CSS variables to global styles
- [ ] Install Tailwind (if using)
- [ ] Configure theme with design tokens
- [ ] Set up dark mode
- [ ] Create base component styles
- [ ] Test contrast ratios
- [ ] Verify on actual devices

---

## Maintenance

**Version:** 1.0.0
**Last Updated:** 2026-01-28
**Maintainer:** SOLO Design Team

**Changelog:**
- v1.0.0 - Initial design system release

---

## Related Documentation

- [Component Library](../components/README.md)
- [Emotional Design Patterns](../patterns/emotional-design.md)
- [Animation Specifications](../animations/README.md)

---

*Part of the SOLO Emotional Design System*
