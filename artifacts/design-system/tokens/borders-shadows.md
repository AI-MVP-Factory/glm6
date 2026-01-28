# Borders, Shadows & Effects - Design Tokens
**Depth, Elevation, Personality**
**Created:** 2026-01-28

---

## Philosophy

**Depth without heavy shadows.** Modern design uses borders and elevation instead.

- **OLED-Optimized:** Borders > shadows for dark mode
- **Friendly Curves:** Rounded corners feel approachable
- **Subtle Elevation:** Layers, not drop shadows
- **Glow over Shadow:** Light creates depth in dark mode

---

## Border Radius (Friendly, Approachable)

```css
--radius-none: 0;
--radius-sm: 4px;     /* Buttons, small elements */
--radius-md: 8px;     /* Cards, inputs (default) */
--radius-lg: 12px;    /* Large cards, modals */
--radius-xl: 16px;    /* Hero elements */
--radius-2xl: 24px;   /* Very rounded cards */
--radius-3xl: 32px;   /* Pill shapes */
--radius-full: 9999px; /* Completely rounded */
```

### Usage Guidelines

| Radius | Use For | Example |
|--------|---------|---------|
| `4px` | Buttons, tags, small UI | Primary button, chips |
| `8px` | Cards, inputs (default) | Task card, text input |
| `12px` | Large cards, modals | Modal dialog, featured card |
| `16px` | Hero elements | Hero card, prominent CTA |
| `full` | Pills, badges | Status badge, avatar ring |

---

## Border Widths

```css
--border-none: 0;
--border-thin: 1px;
--border-medium: 2px;
--border-thick: 3px;
```

### Border Styles

```css
--border-style: solid;

/* Subtle borders for dark mode */
--border-subtle: 1px solid rgba(255, 255, 255, 0.08);
--border-default: 1px solid rgba(255, 255, 255, 0.12);
--border-strong: 1px solid rgba(255, 255, 255, 0.2);

/* Focus borders */
--border-focus: 2px solid rgba(168, 85, 247, 0.5);
--border-focus-success: 2px solid rgba(234, 179, 8, 0.5);
--border-focus-error: 2px solid rgba(244, 63, 94, 0.5);
```

---

## Shadows (OLED-Optimized)

### Dark Mode Shadows

**For OLED:** Use lighter borders and subtle brightness, not drop shadows

```css
/* Elevation through brightness, not shadows */
--elevation-0: 0 0 0 transparent;
--elevation-1: 0 0 0 1px rgba(255, 255, 255, 0.05);
--elevation-2: 0 0 0 1px rgba(255, 255, 255, 0.08);
--elevation-3: 0 0 0 1px rgba(255, 255, 255, 0.12);
--elevation-4: 0 4px 12px rgba(0, 0, 0, 0.5);
```

### Light Mode Shadows

```css
/* Traditional shadows for light mode */
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
--shadow-md: 0 4px 6px rgba(0, 0, 0, 0.07);
--shadow-lg: 0 10px 15px rgba(0, 0, 0, 0.1);
--shadow-xl: 0 20px 25px rgba(0, 0, 0, 0.15);
```

---

## Glow Effects (Celebration, Focus)

```css
/* Primary brand glow */
--glow-primary: 0 0 20px rgba(168, 85, 247, 0.4);
--glow-primary-strong: 0 0 40px rgba(168, 85, 247, 0.6);

/* Celebration glow */
--glow-gold: 0 0 20px rgba(251, 191, 36, 0.5);
--glow-party: 0 0 30px rgba(168, 85, 247, 0.3),
                0 0 60px rgba(236, 72, 153, 0.2);

/* Error glow */
--glow-error: 0 0 20px rgba(244, 63, 94, 0.4);

/* Success glow */
--glow-success: 0 0 20px rgba(234, 179, 8, 0.5);
```

---

## Backdrop Blur

```css
/* For overlays, sheets, floating elements */
--backdrop-blur-sm: blur(4px);
--backdrop-blur-md: blur(8px);
--backdrop-blur-lg: blur(12px);
--backdrop-blur-xl: blur(16px);
```

### Frosted Glass Effect

```css
.frosted-glass {
  background: rgba(10, 10, 10, 0.7);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(255, 255, 255, 0.08);
}
```

---

## CSS Variables (Copy-Paste Ready)

```css
:root {
  /* Border Radius */
  --radius-none: 0;
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-xl: 16px;
  --radius-2xl: 24px;
  --radius-3xl: 32px;
  --radius-full: 9999px;

  /* Border Width */
  --border-thin: 1px;
  --border-medium: 2px;
  --border-thick: 3px;

  /* Borders (Dark Mode) */
  --border-subtle: 1px solid rgba(255, 255, 255, 0.05);
  --border-default: 1px solid rgba(255, 255, 255, 0.1);
  --border-strong: 1px solid rgba(255, 255, 255, 0.15);

  /* Focus Borders */
  --border-focus: 2px solid rgba(168, 85, 247, 0.5);

  /* Elevation (Dark Mode) */
  --elevation-0: 0 0 0 transparent;
  --elevation-1: 0 0 0 1px rgba(255, 255, 255, 0.05);
  --elevation-2: 0 0 0 1px rgba(255, 255, 255, 0.08);
  --elevation-3: 0 0 0 1px rgba(255, 255, 255, 0.12);
  --elevation-4: 0 4px 12px rgba(0, 0, 0, 0.5);

  /* Shadows (Light Mode) */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.07);
  --shadow-lg: 0 10px 15px rgba(0, 0, 0, 0.1);
  --shadow-xl: 0 20px 25px rgba(0, 0, 0, 0.15);

  /* Glow Effects */
  --glow-primary: 0 0 20px rgba(168, 85, 247, 0.4);
  --glow-gold: 0 0 20px rgba(251, 191, 36, 0.5);
  --glow-error: 0 0 20px rgba(244, 63, 94, 0.4);
  --glow-success: 0 0 20px rgba(234, 179, 8, 0.5);

  /* Backdrop Blur */
  --backdrop-blur: blur(12px);
}
```

---

## Tailwind Config (Copy-Paste Ready)

```javascript
module.exports = {
  theme: {
    extend: {
      borderRadius: {
        none: '0',
        sm: '4px',
        DEFAULT: '8px',
        md: '8px',
        lg: '12px',
        xl: '16px',
        '2xl': '24px',
        '3xl': '32px',
        full: '9999px',
      },
      borderWidth: {
        DEFAULT: '1px',
      },
      boxShadow: {
        // Dark mode elevation
        'elevation-1': '0 0 0 1px rgba(255, 255, 255, 0.05)',
        'elevation-2': '0 0 0 1px rgba(255, 255, 255, 0.08)',
        'elevation-3': '0 0 0 1px rgba(255, 255, 255, 0.12)',

        // Glow effects
        'glow-primary': '0 0 20px rgba(168, 85, 247, 0.4)',
        'glow-gold': '0 0 20px rgba(251, 191, 36, 0.5)',
        'glow-error': '0 0 20px rgba(244, 63, 94, 0.4)',
        'glow-success': '0 0 20px rgba(234, 179, 8, 0.5)',
      },
      backdropBlur: {
        xs: 'blur(4px)',
      },
    },
  },
};
```

---

## Component Border Patterns

### Cards

```css
.card {
  border-radius: var(--radius-md);
  border: var(--border-subtle);
}

.card-elevated {
  border-radius: var(--radius-lg);
  border: var(--border-default);
  box-shadow: var(--elevation-2);
}
```

### Inputs

```css
.input {
  border-radius: var(--radius-md);
  border: var(--border-subtle);
}

.input:focus {
  border: var(--border-focus);
  box-shadow: var(--glow-primary);
}
```

### Buttons

```css
.button-primary {
  border-radius: var(--radius-sm);
  border: none;
}

.button-secondary {
  border-radius: var(--radius-sm);
  border: var(--border-default);
}
```

### Modals

```css
.modal {
  border-radius: var(--radius-xl);
  border: var(--border-strong);
  box-shadow: var(--elevation-4);
}
```

---

## Special Effects

### Gradient Borders

```css
.gradient-border {
  position: relative;
  border-radius: var(--radius-md);
  padding: 2px;
  background: var(--gradient-taskflow);
}

.gradient-border-inner {
  background: var(--bg-surface);
  border-radius: calc(var(--radius-md) - 2px);
}
```

### Animated Glow (Pulse)

```css
@keyframes glow-pulse {
  0%, 100% { box-shadow: 0 0 20px rgba(168, 85, 247, 0.4); }
  50% { box-shadow: 0 0 40px rgba(168, 85, 247, 0.6); }
}

.glow-pulse {
  animation: glow-pulse 2s ease-in-out infinite;
}
```

### Shimmer Effect

```css
@keyframes shimmer {
  0% { background-position: -200% 0; }
  100% { background-position: 200% 0; }
}

.shimmer {
  background: linear-gradient(
    90deg,
    rgba(255, 255, 255, 0) 0%,
    rgba(255, 255, 255, 0.05) 50%,
    rgba(255, 255, 255, 0) 100%
  );
  background-size: 200% 100%;
  animation: shimmer 1.5s infinite;
}
```

---

## Usage Guidelines

### DO:
- Use borders for elevation in dark mode
- Reserve glow for emphasis and celebration
- Keep border radius consistent
- Use backdrop blur for overlays

### DON'T:
- Overuse glow effects (diminishes impact)
- Use heavy shadows in dark mode
- Mix too many border radius values
- Use shadows for text (use legible colors)

---

*Last updated: 2026-01-28*
*Status: FINAL*
