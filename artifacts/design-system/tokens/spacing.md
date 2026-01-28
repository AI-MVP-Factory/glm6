# Spacing System - Design Tokens
**Breath, Rhythm, Hierarchy**
**Created:** 2026-01-28

---

## Philosophy

**Spacing is breath.** Without it, design suffocates.

- **4px Base Unit:** Every spacing value is a multiple of 4
- **Purposeful Naming:** Names describe usage, not numbers
- **Consistent Rhythm:** Creates visual harmony
- **Generous by Default:** White space is luxury

---

## The Spacing Scale

**Base Unit:** 4px
**Formula:** `n × 4px` where n = scale value

| Token | Value | Calculation | Usage |
|-------|-------|-------------|-------|
| `--spacing-0` | 0 | 0 × 4 | No spacing |
| `--spacing-px` | 1px | - | Hairline borders |
| `--spacing-0.5` | 2px | 0.5 × 4 | Tight spacing |
| `--spacing-1` | 4px | 1 × 4 | Compact elements |
| `--spacing-1.5` | 6px | 1.5 × 4 | Small gaps |
| `--spacing-2` | 8px | 2 × 4 | Comfortable compact |
| `--spacing-2.5` | 10px | 2.5 × 4 | Small padding |
| `--spacing-3` | 12px | 3 × 4 | Default small |
| `--spacing-3.5` | 14px | 3.5 × 4 | Medium small |
| `--spacing-4` | 16px | 4 × 4 | Default medium |
| `--spacing-5` | 20px | 5 × 4 | Comfortable medium |
| `--spacing-6` | 24px | 6 × 4 | Default large |
| `--spacing-7` | 28px | 7 × 4 | Medium large |
| `--spacing-8` | 32px | 8 × 4 | Extra large |
| `--spacing-9` | 36px | 9 × 4 | Spacious |
| `--spacing-10` | 40px | 10 × 4 | Section spacing |
| `--spacing-11` | 44px | 11 × 4 | Large sections |
| `--spacing-12` | 48px | 12 × 4 | Very large |
| `--spacing-14` | 56px | 14 × 4 | Extra section |
| `--spacing-16` | 64px | 16 × 4 | Hero spacing |
| `--spacing-20` | 80px | 20 × 4 | Major sections |
| `--spacing-24` | 96px | 24 × 4 | Page breaks |
| `--spacing-28` | 112px | 28 × 4 | Hero sections |
| `--spacing-32` | 128px | 32 × 4 | Maximum spacing |

---

## Semantic Spacing Tokens

```css
/* Compact - Tight spaces */
--spacing-xs: 4px;    /* Icon + text, tight list items */
--spacing-sm: 8px;    /* Related elements, small gaps */

/* Default - Standard spacing */
--spacing-md: 16px;   /* Default padding, margins */

/* Comfortable - Breathing room */
--spacing-lg: 24px;   /* Section spacing, comfortable padding */

/* Spacious - Major separation */
--spacing-xl: 32px;   /* Large sections, hero padding */

/* Extra Spacious - Maximum separation */
--spacing-2xl: 48px;  /* Page sections */
--spacing-3xl: 64px;  /* Hero sections, major breaks */
```

---

## Component Spacing Patterns

### Buttons

```css
/* Padding */
--button-padding-sm: 8px 12px;    /* 32px height */
--button-padding-md: 10px 16px;   /* 40px height */
--button-padding-lg: 12px 20px;   /* 44px height */
--button-padding-xl: 14px 24px;   /* 48px height */

/* Gap between buttons */
--button-gap: 8px;
```

### Cards

```css
/* Padding */
--card-padding-sm: 12px;
--card-padding-md: 16px;
--card-padding-lg: 20px;
--card-padding-xl: 24px;

/* Gap between cards */
--card-gap: 16px;
```

### Inputs

```css
/* Padding */
--input-padding: 10px 12px;

/* Gap between inputs */
--input-gap: 12px;
```

### Lists

```css
/* Gap between list items */
--list-gap-sm: 8px;
--list-gap-md: 12px;
--list-gap-lg: 16px;
```

### Modals

```css
/* Padding */
--modal-padding: 24px;

/* Gap from screen edge */
--modal-margin: 16px;
```

---

## Layout Spacing

### Container Widths

```css
--container-sm: 640px;
--container-md: 768px;
--container-lg: 1024px;
--container-xl: 1280px;
--container-2xl: 1536px;
```

### Section Spacing

```css
/* Vertical spacing between sections */
--section-gap-sm: 48px;
--section-gap-md: 64px;
--section-gap-lg: 80px;
--section-gap-xl: 96px;
```

### Gutter (Horizontal Padding)

```css
--gutter-sm: 16px;
--gutter-md: 24px;
--gutter-lg: 32px;
--gutter-xl: 48px;
```

---

## CSS Variables (Copy-Paste Ready)

```css
:root {
  /* Base Scale */
  --spacing-0: 0;
  --spacing-px: 1px;
  --spacing-0.5: 2px;
  --spacing-1: 4px;
  --spacing-1.5: 6px;
  --spacing-2: 8px;
  --spacing-2.5: 10px;
  --spacing-3: 12px;
  --spacing-3.5: 14px;
  --spacing-4: 16px;
  --spacing-5: 20px;
  --spacing-6: 24px;
  --spacing-7: 28px;
  --spacing-8: 32px;
  --spacing-9: 36px;
  --spacing-10: 40px;
  --spacing-11: 44px;
  --spacing-12: 48px;
  --spacing-14: 56px;
  --spacing-16: 64px;
  --spacing-20: 80px;
  --spacing-24: 96px;
  --spacing-28: 112px;
  --spacing-32: 128px;

  /* Semantic */
  --spacing-xs: 4px;
  --spacing-sm: 8px;
  --spacing-md: 16px;
  --spacing-lg: 24px;
  --spacing-xl: 32px;
  --spacing-2xl: 48px;
  --spacing-3xl: 64px;

  /* Components */
  --button-padding-sm: 8px 12px;
  --button-padding-md: 10px 16px;
  --button-padding-lg: 12px 20px;
  --button-padding-xl: 14px 24px;
  --button-gap: 8px;

  --card-padding-sm: 12px;
  --card-padding-md: 16px;
  --card-padding-lg: 20px;
  --card-padding-xl: 24px;
  --card-gap: 16px;

  --input-padding: 10px 12px;
  --input-gap: 12px;

  --list-gap-sm: 8px;
  --list-gap-md: 12px;
  --list-gap-lg: 16px;

  --modal-padding: 24px;
  --modal-margin: 16px;

  /* Layout */
  --container-sm: 640px;
  --container-md: 768px;
  --container-lg: 1024px;
  --container-xl: 1280px;
  --container-2xl: 1536px;

  --section-gap-sm: 48px;
  --section-gap-md: 64px;
  --section-gap-lg: 80px;
  --section-gap-xl: 96px;

  --gutter-sm: 16px;
  --gutter-md: 24px;
  --gutter-lg: 32px;
  --gutter-xl: 48px;
}
```

---

## Tailwind Config (Copy-Paste Ready)

```javascript
module.exports = {
  theme: {
    spacing: {
      0: '0',
      px: '1px',
      0.5: '2px',
      1: '4px',
      1.5: '6px',
      2: '8px',
      2.5: '10px',
      3: '12px',
      3.5: '14px',
      4: '16px',
      5: '20px',
      6: '24px',
      7: '28px',
      8: '32px',
      9: '36px',
      10: '40px',
      11: '44px',
      12: '48px',
      14: '56px',
      16: '64px',
      20: '80px',
      24: '96px',
      28: '112px',
      32: '128px',
    },
    extend: {
      gap: {
        xs: '4px',
        sm: '8px',
        md: '16px',
        lg: '24px',
        xl: '32px',
        '2xl': '48px',
        '3xl': '64px',
      },
      padding: {
        button: {
          sm: '8px 12px',
          md: '10px 16px',
          lg: '12px 20px',
          xl: '14px 24px',
        },
        card: {
          sm: '12px',
          md: '16px',
          lg: '20px',
          xl: '24px',
        },
        input: '10px 12px',
        modal: '24px',
      },
    },
  },
};
```

---

## Spacing Patterns

### The 8-Point Grid

All elements align to an 8px grid:

```
┌─────────────────────────────────────┐
│ ┌───┐                               │
│ │   │  Content aligned to 8px grid │
│ └───┘                               │
│                                     │
│ ┌───────┐                           │
│ │       │  Each element 8px apart   │
│ └───────┘                           │
│                                     │
│ ┌───────────┐                       │
│ │           │  Consistent rhythm   │
│ └───────────┘                       │
└─────────────────────────────────────┘
```

### Vertical Rhythm

```
Heading (32px)
   ↓
Spacing (24px) ← 6 units
   ↓
Body (16px)
   ↓
Spacing (16px) ← 4 units
   ↓
Body (16px)
   ↓
Spacing (24px) ← 6 units
   ↓
Next Heading
```

---

## Responsive Spacing

### Mobile-First Spacing

| Context | Mobile | Tablet | Desktop |
|---------|--------|--------|---------|
| Container padding | 16px | 24px | 32px |
| Section gap | 48px | 64px | 80px |
| Card gap | 12px | 16px | 20px |

```css
/* Mobile default */
.container {
  padding: 16px;
}

/* Tablet */
@media (min-width: 768px) {
  .container {
    padding: 24px;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .container {
    padding: 32px;
  }
}
```

---

## Spacing for Touch Targets

**Minimum touch target:** 44×44px (Apple HIG)

```css
/* Calculate padding for 44px minimum */
.button {
  height: 44px;
  padding: 10px 16px;  /* 44px = 10 + text (20ish) + 10 */
}

.icon-button {
  min-width: 44px;
  min-height: 44px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}
```

---

## Safe Areas (Notch Awareness)

```css
/* iOS safe areas */
.container {
  padding-left: max(16px, env(safe-area-inset-left));
  padding-right: max(16px, env(safe-area-inset-right));
  padding-top: max(16px, env(safe-area-inset-top));
  padding-bottom: max(16px, env(safe-area-inset-bottom));
}
```

---

## Usage Guidelines

### DO:
- Use semantic names (sm, md, lg) for flexibility
- Maintain consistent rhythm
- Use generous spacing for emphasis
- Scale spacing with viewport

### DON'T:
- Use arbitrary values (use the scale)
- Use negative margin for layout (use grid/flex)
- Over-compress content
- Mix spacing systems

---

## Quick Reference

| Need | Use |
|------|-----|
| Tight gap between icon and text | `--spacing-xs` (4px) |
| Default padding for cards | `--spacing-md` (16px) |
| Section separation | `--spacing-2xl` (48px) |
| Button gap | `--spacing-sm` (8px) |
| Hero top/bottom padding | `--spacing-3xl` (64px) |

---

*Last updated: 2026-01-28*
*Status: FINAL*
