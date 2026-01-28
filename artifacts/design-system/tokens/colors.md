# Color System - Design Tokens
**Emotional-First, OLED-Optimized**
**Created:** 2026-01-28

---

## Philosophy

**Colors create feelings.** Every color choice answers: "How should the user FEEL right now?"

- **Dark-First:** OLED black saves battery, looks premium
- **Emotional Semantic:** Not just "green" = success, but "celebration gold"
- **App Personality:** Each app has a unique primary color identity
- **Accessibility:** WCAG AA minimum contrast ratio (4.5:1)

---

## Primary Colors (App Identities)

### TaskFlow v3 - "Productivity Purple"
**Feeling:** Creative, focused, magical

```css
--taskflow-primary-50: #faf5ff;
--taskflow-primary-100: #f3e8ff;
--taskflow-primary-200: #e9d5ff;
--taskflow-primary-300: #d8b4fe;
--taskflow-primary-400: #c084fc;
--taskflow-primary-500: #a855f7;  /* Main brand */
--taskflow-primary-600: #9333ea;  /* Hover/active */
--taskflow-primary-700: #7e22ce;
--taskflow-primary-800: #6b21a8;
--taskflow-primary-900: #581c87;

/* Gradient */
--taskflow-gradient: linear-gradient(135deg, #a855f7 0%, #6366f1 100%);
```

---

### TeenPopTastic (Vibe) - "Vibe Gradient"
**Feeling:** Energetic, warm, social

```css
--vibe-primary-pink: #ec4899;
--vibe-primary-purple: #8b5cf6;

/* Gradient - Pink to Purple */
--vibe-gradient: linear-gradient(135deg, #ec4899 0%, #8b5cf6 100%);

/* Accent - Amber for CTAs */
--vibe-accent: #fbbf24;
```

---

### MemeCraft - "Meme Electric"
**Feeling:** Fun, viral, energetic

```css
--memecraft-primary-cyan: #22d3ee;
--memecraft-primary-indigo: #6366f1;

/* Gradient - Cyan to Indigo */
--memecraft-gradient: linear-gradient(135deg, #22d3ee 0%, #6366f1 100%);

/* Accent - Amber for CTAs */
--memecraft-accent: #f59e0b;
```

---

## Semantic Colors (Emotional Naming)

### Success - "Celebration Gold"
**Feeling:** Achievement, warmth, delight

```css
--success-50: #fefce8;
--success-100: #fef9c3;
--success-200: #fef08a;
--success-300: #fde047;
--success-400: #facc15;
--success-500: #eab308;  /* Main success */
--success-600: #ca8a04;
--success-700: #a16207;
--success-800: #854d0e;
--success-900: #713f12;

/* For celebrations - warmer */
--celebration: #fbbf24;
--celebration-glow: rgba(251, 191, 36, 0.3);
```

---

### Error - "Gentle Rose"
**Feeling:** Concern, not alarm; fixable, not fatal

```css
--error-50: #fff1f2;
--error-100: #ffe4e6;
--error-200: #fecdd3;
--error-300: #fda4af;
--error-400: #fb7185;
--error-500: #f43f5e;  /* Main error */
--error-600: #e11d48;
--error-700: #be123c;
--error-800: #9f1239;
--error-900: #881337;

/* Soft error background */
--error-bg: rgba(244, 63, 94, 0.1);
--error-border: rgba(244, 63, 94, 0.2);
```

---

### Warning - "Helpful Amber"
**Feeling:** Caution, guidance, assistance

```css
--warning-50: #fffbeb;
--warning-100: #fef3c7;
--warning-200: #fde68a;
--warning-300: #fcd34d;
--warning-400: #fbbf24;
--warning-500: #f59e0b;  /* Main warning */
--warning-600: #d97706;
--warning-700: #b45309;
--warning-800: #92400e;
--warning-900: #78350f;
```

---

### Info - "Calm Sky"
**Feeling:** Information, clarity, peace

```css
--info-50: #f0f9ff;
--info-100: #e0f2fe;
--info-200: #bae6fd;
--info-300: #7dd3fc;
--info-400: #38bdf8;
--info-500: #0ea5e9;  /* Main info */
--info-600: #0284c7;
--info-700: #0369a1;
--info-800: #075985;
--info-900: #0c4a6e;
```

---

## Neutrals (OLED-Optimized)

**True Black for OLED** - Saves battery, deeper blacks

```css
/* Backgrounds - True black to near black */
--neutral-950: #000000;  /* Pure black - OLED */
--neutral-900: #0a0a0a;  /* Surface level 1 */
--neutral-800: #141414;  /* Surface level 2 */
--neutral-700: #1c1c1c;  /* Surface level 3 */
--neutral-600: #262626;  /* Borders, dividers */
--neutral-500: #404040;  /* Disabled borders */
--neutral-400: #71717a;  /* Text tertiary */
--neutral-300: #a1a1aa;  /* Text secondary */
--neutral-200: #d4d4d8;  /* Text primary (dark mode) */
--neutral-100: #e4e4e7;  /* Text primary (light mode) */
--neutral-50: #f4f4f5;   /* Background (light mode) */
```

---

## Text Colors

### Dark Mode (Default)

```css
--text-primary: #fafafa;     /* Headlines, important text */
--text-secondary: #a1a1aa;   /* Body, descriptions */
--text-tertiary: #71717a;    /* Captions, hints */
--text-disabled: #404040;    /* Disabled text */
--text-inverse: #000000;     /* On colored backgrounds */
```

### Light Mode

```css
--text-primary-light: #18181b;
--text-secondary-light: #52525b;
--text-tertiary-light: #71717a;
--text-disabled-light: #d4d4d8;
```

---

## Elevation (Background Layers)

**OLED-Optimized:** Use brightness, not shadows, for dark mode

```css
/* Dark Mode Elevation */
--elevation-0: #000000;     /* Base - true black */
--elevation-1: #0a0a0a;     /* Raised slightly */
--elevation-2: #141414;     /* Cards */
--elevation-3: #1c1c1c;     /* Modals, drawers */
--elevation-4: #262626;     /* Highest elevation */

/* Borders for elevation */
--border-elevation-1: rgba(255, 255, 255, 0.05);
--border-elevation-2: rgba(255, 255, 255, 0.08);
--border-elevation-3: rgba(255, 255, 255, 0.12);
```

---

## Overlay Colors

```css
/* Modal backdrops */
--overlay-light: rgba(0, 0, 0, 0.3);
--overlay-medium: rgba(0, 0, 0, 0.5);
--overlay-dark: rgba(0, 0, 0, 0.7);

/* Focus rings */
--focus-ring: rgba(168, 85, 247, 0.5);  /* Primary brand */
--focus-ring-success: rgba(234, 179, 8, 0.5);
--focus-ring-error: rgba(244, 63, 94, 0.5);

/* Gradients for celebration */
--gradient-warm: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
--gradient-cool: linear-gradient(135deg, #22d3ee 0%, #6366f1 100%);
--gradient-party: linear-gradient(135deg, #ec4899 0%, #8b5cf6 50%, #22d3ee 100%);
```

---

## State Colors (Interactive Elements)

```css
/* Hover states */
--hover-primary: rgba(168, 85, 247, 0.15);
--hover-surface: rgba(255, 255, 255, 0.05);

/* Active/Pressed states */
--active-primary: rgba(168, 85, 247, 0.25);
--active-surface: rgba(255, 255, 255, 0.08);

/* Focus states */
--focus-ring-width: 2px;
--focus-ring-offset: 2px;

/* Disabled states */
--disabled-bg: #262626;
--disabled-text: #404040;
--disabled-border: #404040;
```

---

## Special Purpose Colors

### Celebration Palette
**For confetti, achievements, streaks**

```css
--celebration-gold: #fbbf24;
--celebration-pink: #ec4899;
--celebration-purple: #a855f7;
--celebration-blue: #3b82f6;
--celebration-cyan: #22d3ee;
--celebration-green: #22c55e;
```

### Social Media Colors (For share buttons)

```css
--social-twitter: #1da1f2;
--social-instagram: #e4405f;
--social-tiktok: #000000;
--social-spotify: #1db954;
--social-apple-music: #fc3c44;
```

---

## CSS Variables (Copy-Paste Ready)

```css
:root {
  /* TaskFlow Primary */
  --taskflow-primary: #a855f7;
  --taskflow-primary-hover: #9333ea;
  --taskflow-gradient: linear-gradient(135deg, #a855f7 0%, #6366f1 100%);

  /* Vibe Primary */
  --vibe-primary-pink: #ec4899;
  --vibe-primary-purple: #8b5cf6;
  --vibe-gradient: linear-gradient(135deg, #ec4899 0%, #8b5cf6 100%);

  /* MemeCraft Primary */
  --memecraft-primary-cyan: #22d3ee;
  --memecraft-primary-indigo: #6366f1;
  --memecraft-gradient: linear-gradient(135deg, #22d3ee 0%, #6366f1 100%);

  /* Semantic */
  --success: #eab308;
  --error: #f43f5e;
  --warning: #f59e0b;
  --info: #0ea5e9;
  --celebration: #fbbf24;

  /* Neutrals (Dark Mode) */
  --bg-base: #000000;
  --bg-surface: #0a0a0a;
  --bg-card: #141414;
  --bg-elevated: #1c1c1c;
  --border-default: #262626;

  /* Text (Dark Mode) */
  --text-primary: #fafafa;
  --text-secondary: #a1a1aa;
  --text-tertiary: #71717a;
  --text-disabled: #404040;
}

/* Light Mode */
@media (prefers-color-scheme: light) {
  :root {
    --bg-base: #ffffff;
    --bg-surface: #fafafa;
    --bg-card: #f4f4f5;
    --bg-elevated: #e4e4e7;
    --border-default: #d4d4d8;

    --text-primary: #18181b;
    --text-secondary: #52525b;
    --text-tertiary: #71717a;
  }
}
```

---

## Tailwind Config (Copy-Paste Ready)

```javascript
module.exports = {
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
        success: {
          DEFAULT: '#eab308',
          glow: 'rgba(251, 191, 36, 0.3)',
        },
        error: {
          DEFAULT: '#f43f5e',
          bg: 'rgba(244, 63, 94, 0.1)',
          border: 'rgba(244, 63, 94, 0.2)',
        },
        warning: '#f59e0b',
        info: '#0ea5e9',
        celebration: '#fbbf24',

        // OLED Neutrals
        neutral: {
          950: '#000000', // True black
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
      backgroundImage: {
        'gradient-taskflow': 'linear-gradient(135deg, #a855f7 0%, #6366f1 100%)',
        'gradient-vibe': 'linear-gradient(135deg, #ec4899 0%, #8b5cf6 100%)',
        'gradient-meme': 'linear-gradient(135deg, #22d3ee 0%, #6366f1 100%)',
        'gradient-party': 'linear-gradient(135deg, #ec4899 0%, #8b5cf6 50%, #22d3ee 100%)',
      },
    },
  },
};
```

---

## Accessibility Notes

- **WCAG AA:** All text combinations meet 4.5:1 contrast minimum
- **WCAG AAA:** Large text (18px+) meets 7:1 contrast
- **Focus Rings:** Always visible, 2px minimum
- **Color Blindness:** Never rely on color alone (use icons + color)

---

## Usage Guidelines

### DO:
- Use semantic colors for meaning (success, error, warning)
- Reserve celebration colors for achievements
- Use neutrals for content structure
- Maintain contrast ratios

### DON'T:
- Use error color for generic red UI elements
- Overuse celebration colors (diminishes impact)
- Hard-code colors (use tokens)
- Use color as the only indicator

---

*Last updated: 2026-01-28*
*Status: FINAL*
