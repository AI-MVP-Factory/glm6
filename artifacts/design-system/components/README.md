# Component Library - Complete Reference
**Emotional Components for SOLO Products**
**Created:** 2026-01-28
**Version:** 1.0.0

---

## Overview

This component library provides the building blocks for all SOLO products. Every component is designed to evoke positive emotions and create delightful user experiences.

**Products using this library:**
- TaskFlow v3 - Productivity that celebrates
- TeenPopTastic (Vibe) - Music that connects
- MemeCraftVibe - Memes that delight

---

## Component Categories

| Category | File | Components |
|----------|------|------------|
| **Celebration** | `celebration-components.md` | Confetti, Success Modal, Progress Celebration, Streak Counter, Achievement Reveal |
| **Buttons** | `button-components.md` | Primary, Secondary, Destructive, Ghost, Icon, FAB |
| **Inputs** | `input-components.md` | Text, Textarea, Select, Checkbox, Radio, Switch, Search |
| **Cards** | `card-components.md` | Task Card, Profile Card, Meme Card, Notification, Achievement, Stats |
| **Loading** | `loading-states.md` | Skeleton, Progress Bar, Spinner, Full-page, Pull to Refresh |

---

## Quick Reference

### Button Variants

| Variant | Use For | Emotion |
|---------|---------|---------|
| Primary | Main action | Confident |
| Secondary | Alternative | Considered |
| Destructive | Dangerous | Serious |
| Ghost | Low-emphasis | Subtle |

### Input States

| State | Visual | Feeling |
|-------|--------|---------|
| Default | Gray border | Neutral |
| Focus | Glow border | Attentive |
| Error | Red border + helper | Helpful |
| Success | Green checkmark | Validated |

### Card Interactions

| Interaction | Effect | Emotion |
|-------------|--------|---------|
| Hover | Lift + glow | Interested |
| Drag | Scale + shadow | In control |
| Complete | Dim + checkmark | Satisfied |

---

## Component Props (TypeScript)

```typescript
// Base component props
interface BaseProps {
  className?: string;
  testId?: string;
  children?: ReactNode;
}

// Button props
interface ButtonProps extends BaseProps {
  variant?: 'primary' | 'secondary' | 'destructive' | 'ghost';
  size?: 'sm' | 'md' | 'lg' | 'xl';
  disabled?: boolean;
  loading?: boolean;
  fullWidth?: boolean;
  icon?: ReactNode;
  onClick?: () => void;
}

// Input props
interface InputProps extends BaseProps {
  type?: 'text' | 'email' | 'password' | 'search';
  placeholder?: string;
  label?: string;
  error?: string;
  helper?: string;
  value?: string;
  onChange?: (value: string) => void;
}

// Card props
interface CardProps extends BaseProps {
  variant?: 'default' | 'elevated' | 'outlined';
  padding?: 'compact' | 'default' | 'comfortable';
  hover?: boolean;
  clickable?: boolean;
  onClick?: () => void;
}
```

---

## Design Tokens Used

All components reference the design tokens:

```css
/* From tokens/colors.md */
--taskflow-primary: #a855f7;
--vibe-primary-pink: #ec4899;
--meme-primary-cyan: #22d3ee;

/* From tokens/spacing.md */
--spacing-sm: 8px;
--spacing-md: 16px;
--spacing-lg: 24px;

/* From tokens/borders-shadows.md */
--radius-sm: 4px;
--radius-md: 8px;
--radius-lg: 12px;
--border-subtle: 1px solid rgba(255, 255, 255, 0.05);
```

---

## Component Composition

### Example: Task Card with Actions

```typescript
function TaskCard({ task, onToggle, onDelete }) {
  return (
    <Card hover clickable>
      <Flex gap="md" align="center">
        <Checkbox checked={task.completed} onChange={onToggle} />
        <Box flex>
          <Text>{task.title}</Text>
          {task.dueDate && (
            <Text variant="secondary" size="sm">
              📅 {formatDate(task.dueDate)}
            </Text>
          )}
        </Box>
        <IconButton icon="trash" onClick={onDelete} />
      </Flex>
    </Card>
  );
}
```

### Example: Celebration Button

```typescript
function CelebrateButton({ onClick }) {
  const [celebrating, setCelebrating] = useState(false);

  const handleClick = () => {
    setCelebrating(true);
    triggerConfetti();
    onClick?.();
    setTimeout(() => setCelebrating(false), 2000);
  };

  return (
    <Button
      variant="primary"
      onClick={handleClick}
      success={celebrating}
    >
      {celebrating ? '🎉 Awesome!' : 'Complete Task'}
    </Button>
  );
}
```

---

## Animation Patterns

All components use consistent animation timing:

```css
/* Duration */
--duration-instant: 0.1s;
--duration-fast: 0.15s;
--duration-normal: 0.2s;
--duration-slow: 0.3s;
--duration-slower: 0.5s;

/* Easing */
--ease-out: cubic-bezier(0, 0, 0.2, 1);
--ease-in-out: cubic-bezier(0.4, 0, 0.2, 1);
--bounce: cubic-bezier(0.34, 1.56, 0.64, 1);
```

---

## State Management

### Loading State Pattern

```typescript
function Component() {
  const [state, setState] = useState<'idle' | 'loading' | 'success' | 'error'>('idle');

  const handleSubmit = async () => {
    setState('loading');
    try {
      await api.save();
      setState('success');
      setTimeout(() => setState('idle'), 2000);
    } catch {
      setState('error');
    }
  };

  return (
    <Button
      loading={state === 'loading'}
      success={state === 'success'}
      onClick={handleSubmit}
    >
      {state === 'success' ? '✓ Saved!' : 'Save Changes'}
    </Button>
  );
}
```

---

## Theming

Components adapt to each app's theme:

```typescript
const themes = {
  taskflow: {
    primary: '#a855f7',
    gradient: 'linear-gradient(135deg, #a855f7 0%, #6366f1 100%)',
  },
  vibe: {
    primary: '#ec4899',
    gradient: 'linear-gradient(135deg, #ec4899 0%, #8b5cf6 100%)',
  },
  meme: {
    primary: '#22d3ee',
    gradient: 'linear-gradient(135deg, #22d3ee 0%, #6366f1 100%)',
  },
};
```

---

## Accessibility Features

All components include:

- **Keyboard Navigation** - Full keyboard support
- **Screen Reader** - ARIA labels and roles
- **Focus Indicators** - Visible focus rings
- **Touch Targets** - Minimum 44×44px
- **Color Contrast** - WCAG AA compliant
- **Reduced Motion** - Respects prefers-reduced-motion

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## Component Checklist

When creating a new component:

- [ ] Uses design tokens for all values
- [ ] Has TypeScript props interface
- [ ] Includes loading state (if applicable)
- [ ] Includes error state (if applicable)
- [ ] Has hover/focus states
- [ ] Supports dark/light mode
- [ ] Keyboard accessible
- [ ] Screen reader friendly
- [ ] Responsive (mobile-first)
- [ ] Documentation with examples

---

## Usage Guidelines

### DO:
- Compose components together
- Use semantic HTML
- Provide feedback for all actions
- Keep components focused (single purpose)
- Test with real users

### DON'T:
- Create overly complex components
- Hard-code values (use tokens)
- Ignore accessibility
| Skip loading states
| Over-nest components

---

## Migration Guide

From existing components to this library:

1. **Replace hard-coded values** with design tokens
2. **Add loading states** where missing
3. **Improve error states** with friendly messages
4. **Add animations** using shared patterns
5. **Test accessibility** with keyboard and screen reader

---

## File Organization

```
/design-system/
├── tokens/
│   ├── README.md           (All tokens)
│   ├── colors.md           (Color system)
│   ├── typography.md       (Fonts, sizes)
│   ├── spacing.md          (4px grid)
│   └── borders-shadows.md  (Radius, shadows)
├── components/
│   ├── README.md           (This file)
│   ├── celebration-components.md
│   ├── button-components.md
│   ├── input-components.md
│   ├── card-components.md
│   └── loading-states.md
├── patterns/
│   └── emotional-design.md
└── animations/
    └── README.md
```

---

## Related Documentation

- [Design Tokens](../tokens/README.md)
- [Emotional Design Patterns](../patterns/emotional-design.md)
- [Animation Library](../animations/README.md)

---

## Changelog

### v1.0.0 (2026-01-28)
- Initial component library release
- 20+ components documented
- Full TypeScript support
- Accessibility guidelines
- Animation patterns

---

*Part of the SOLO Emotional Design System*
