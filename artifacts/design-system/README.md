# SOLO Emotional Design System
**How Products Feel When Users Interact**
**Created:** 2026-01-28
**Version:** 1.0.0

---

## Overview

This design system provides the visual and emotional language for all SOLO products. Every component, token, and pattern is designed to create delightful user experiences that make users feel good.

**Core Thesis:** > *Products succeed by how they make users FEEL. Not features, but emotions.*

---

## Products Using This System

| Product | Feeling | Primary Color |
|---------|---------|----------------|
| **TaskFlow v3** | Productivity that celebrates | Purple (#a855f7) |
| **TeenPopTastic** (Vibe) | Music that connects | Pink → Purple gradient |
| **MemeCraftVibe** | Memes that delight | Cyan → Indigo gradient |

---

## Quick Start

### Design Tokens

All visual values are defined as CSS variables:

```css
/* Colors */
--taskflow-primary: #a855f7;
--vibe-primary-pink: #ec4899;
--meme-primary-cyan: #22d3ee;

/* Spacing */
--spacing-xs: 4px;
--spacing-sm: 8px;
--spacing-md: 16px;
--spacing-lg: 24px;

/* Typography */
--font-display: "SF Pro Display", "Inter", sans-serif;
--font-body: "SF Pro Text", "Inter", sans-serif;
```

### Components

```typescript
// Button
<Button variant="primary" onClick={handleClick}>
  Celebrate your wins
</Button>

// Card with celebration
<Card hover onCompleted={triggerConfetti}>
  Task content here
</Card>

// Input with friendly placeholder
<Input placeholder="What's on your mind?" />
```

---

## Directory Structure

```
/design-system/
├── tokens/                      # Design tokens
│   ├── README.md               # All tokens reference
│   ├── colors.md               # Color system
│   ├── typography.md           # Font scales
│   ├── spacing.md              # 4px grid
│   └── borders-shadows.md      # Radius, shadows
│
├── components/                  # Component library
│   ├── README.md               # Component reference
│   ├── celebration-components.md
│   ├── button-components.md
│   ├── input-components.md
│   ├── card-components.md
│   └── loading-states.md
│
├── patterns/                    # Design patterns
│   └── emotional-design.md     # How to make users FEEL
│
├── animations/                  # Animations
│   └── README.md               # All animations
│
├── screenshots/                 # Screenshot templates
│   └── README.md               # App Store screenshots
│
└── Figma files (when created)    # Visual mockups
```

---

## Design Principles

### 1. Emotional First
Every design decision answers: "How should this make the user feel?"

### 2. Dark-First
OLED black (#000000) saves battery, looks premium

### 3. Generous Spacing
White space is luxury, not waste

### 4. Native Feel
System fonts, platform conventions

### 5. Accessible Always
WCAG AA minimum, AAA where possible

---

## Token Reference

### Colors

| Type | Token | Value |
|------|-------|-------|
| TaskFlow Primary | `--taskflow-primary` | #a855f7 |
| Vibe Pink | `--vibe-primary-pink` | #ec4899 |
| Vibe Purple | `--vibe-primary-purple` | #8b5cf6 |
| Meme Cyan | `--meme-primary-cyan` | #22d3ee |
| Meme Indigo | `--meme-primary-indigo` | #6366f1 |
| Success | `--success` | #eab308 |
| Error | `--error` | #f43f5e |
| Warning | `--warning` | #f59e0b |
| Celebration | `--celebration` | #fbbf24 |

### Typography

| Use | Size | Weight |
|-----|------|--------|
| Display | 48px | 700 |
| Heading | 24px | 600 |
| Body | 16px | 400 |
| Micro | 11px | 500 |

### Spacing

| Name | Value |
|------|-------|
| XS | 4px |
| SM | 8px |
| MD | 16px |
| LG | 24px |
| XL | 32px |
| 2XL | 48px |

### Border Radius

| Name | Value | Use |
|------|-------|-----|
| SM | 4px | Buttons |
| MD | 8px | Cards (default) |
| LG | 12px | Modals |
| Full | 9999px | Pills |

---

## Component Library

### Available Components

- **Celebration:** Confetti, success modals, streak counter
- **Buttons:** Primary, secondary, destructive, ghost
- **Inputs:** Text, textarea, select, checkbox, switch
- **Cards:** Task card, profile card, notification
- **Loading:** Skeletons, progress bars, spinners

### Component States

Each component has:
- Default
- Hover
- Focus
- Active/Pressed
- Disabled
- Error (where applicable)
- Loading (where applicable)
- Success (where applicable)

---

## Emotional Design Patterns

### Warmth

```
✅ "Hey [Name]! Good to see you again"
❌ "Welcome back"
```

### Empathy

```
✅ "Having a tough day? That's okay."
❌ "You're behind schedule"
```

### Celebration

```
✅ "🎉 YOU CRUSHED IT!"
❌ "Task complete"
```

### Validation

```
✅ "Look how far you've come!"
❌ "50% complete"
```

---

## Animation Guidelines

### Duration

| Type | Duration |
|------|----------|
| Micro | 50ms |
| Fast | 150ms |
| Normal | 200ms |
| Slow | 300ms |
| Celebration | 500ms+ |

### Easing

- **ease-out:** Most transitions
- **ease-in-out:** Page transitions
- **ease-bounce:** Playful elements
- **ease-spring:** Natural movement

### Performance

- Always 60fps
- Use transform > top/left/width/height
- Will-change for heavy animations
- Respect prefers-reduced-motion

---

## Accessibility

- WCAG AA compliant (4.5:1 contrast minimum)
- Keyboard navigation
- Screen reader support
- Focus indicators
- Touch targets 44×44px minimum
- Reduced motion support

---

## Implementation Checklist

For each new feature:

- [ ] Use design tokens for all values
- [ ] Include loading state
- [ ] Include error state
- [ ] Add hover/focus states
- [ ] Support dark/light mode
- [ ] Keyboard accessible
- [ ] Screen reader friendly
- [ ] Responsive (mobile-first)
- [ ] Celebrate milestones
- [ ] Friendly copy

---

## Tailwind Configuration

```javascript
// tailwind.config.js
module.exports = {
  darkMode: 'class',
  theme: {
    extend: {
      colors: {
        taskflow: {
          500: '#a855f7',
          600: '#9333ea',
        },
        vibe: {
          pink: '#ec4899',
          purple: '#8b5cf6',
        },
        meme: {
          cyan: '#22d3ee',
          indigo: '#6366f1',
        },
        success: '#eab308',
        error: '#f43f5e',
        warning: '#f59e0b',
        celebration: '#fbbf24',
        neutral: {
          950: '#000000', // OLED black
          // ... see tokens/colors.md
        },
      },
      fontFamily: {
        display: ['SF Pro Display', 'Inter', 'sans-serif'],
        body: ['SF Pro Text', 'Inter', 'sans-serif'],
        mono: ['SF Mono', 'JetBrains Mono', 'monospace'],
      },
      spacing: {
        xs: '4px',
        sm: '8px',
        md: '16px',
        lg: '24px',
        xl: '32px',
        '2xl': '48px',
      },
      borderRadius: {
        sm: '4px',
        md: '8px',
        lg: '12px',
        xl: '16px',
        full: '9999px',
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

## Usage Guidelines

### DO

- Use semantic naming (sm, md, lg)
- Maintain consistent spacing
- Celebrate user achievements
- Provide helpful error messages
- Use friendly copy
- Test on real devices
- Honor accessibility

### DON'T

- Hard-code values
- Mix spacing systems
- Over-celebrate (diminishes impact)
- Show errors as "INVALID"
- Use robotic copy
- Skip loading states
- Ignore accessibility

---

## Changelog

### v1.0.0 (2026-01-28)

**Added:**
- Complete token system (colors, typography, spacing, borders)
- Component library documentation
- Animation library
- Emotional design patterns
- Screenshot templates
- Tailwind configuration

**Products:**
- TaskFlow v3
- TeenPopTastic (Vibe)
- MemeCraftVibe

---

## Related Documentation

- [Design Tokens](./tokens/README.md)
- [Component Library](./components/README.md)
- [Emotional Patterns](./patterns/emotional-design.md)
- [Animations](./animations/README.md)
- [Screenshots](./screenshots/README.md)

---

## Credits

**Created by:** SOLO Design Team
**Philosophy:** *"Features are what the product DOES. Design is how it FEELS."*

---

*Part of the SOLO Emotional Design System*
*Last updated: 2026-01-28*
*Status: COMPLETE*
