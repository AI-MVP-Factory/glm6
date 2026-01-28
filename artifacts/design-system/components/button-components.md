# Button Components
**Action, Feedback, Personality**
**Created:** 2026-01-28

---

## Philosophy

**Buttons are promises.** Each button tells the user what will happen next.

- **Clear Intent:** Button text = action result
- **Immediate Feedback:** User knows button was pressed
- **Visual Hierarchy:** Primary action stands out
- **Personality:** Even buttons have character

---

## Button Variants

### 1. Primary Button

**Purpose:** Main action, "do this thing"

```
┌─────────────────────┐
│   Get Started       │  ← Gradient background
└─────────────────────┘
```

**States:**

| State | Background | Text | Effect |
|-------|-----------|------|--------|
| Default | Gradient | White | Subtle shimmer |
| Hover | Brighten | White | Lift + glow |
| Active/Press | Scale 0.98 | White | Ripple |
| Loading | Gradient + spinner | Dimmed | Pulse |
| Disabled | Neutral | Gray | No interaction |

**CSS:**

```css
.button-primary {
  background: var(--gradient-taskflow);
  color: white;
  padding: var(--button-padding-md);
  border-radius: var(--radius-sm);
  border: none;
  font-weight: var(--font-semibold);
  cursor: pointer;
  transition: all 0.15s ease;
  position: relative;
  overflow: hidden;
}

.button-primary:hover {
  filter: brightness(1.1);
  transform: translateY(-1px);
  box-shadow: var(--glow-primary);
}

.button-primary:active {
  transform: scale(0.98);
}

/* Loading state */
.button-primary.loading {
  pointer-events: none;
}

.button-primary.loading::after {
  content: '';
  position: absolute;
  width: 16px;
  height: 16px;
  border: 2px solid rgba(255,255,255,0.3);
  border-top-color: white;
  border-radius: 50%;
  animation: spin 0.8s linear infinite;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}
```

---

### 2. Secondary Button

**Purpose:** Alternative action, "do this other thing"

```
┌─────────────────────┐
│   Learn More        │  ← Outlined
└─────────────────────┘
```

**States:**

| State | Background | Border | Text | Effect |
|-------|-----------|--------|------|--------|
| Default | Transparent | Border | Primary | Clean |
| Hover | 10% primary | Border | Primary | Subtle fill |
| Active/Press | Transparent | Border | Primary | Scale 0.98 |

**CSS:**

```css
.button-secondary {
  background: transparent;
  color: var(--text-primary);
  padding: var(--button-padding-md);
  border-radius: var(--radius-sm);
  border: var(--border-default);
  font-weight: var(--font-semibold);
  cursor: pointer;
  transition: all 0.15s ease;
}

.button-secondary:hover {
  background: rgba(168, 85, 247, 0.1);
  border-color: var(--taskflow-primary);
}

.button-secondary:active {
  transform: scale(0.98);
}
```

---

### 3. Destructive Button

**Purpose:** Dangerous action, "be careful"

```
┌─────────────────────┐
│   Delete Task       │  ← Red gradient
└─────────────────────┘
```

**States:**

| State | Background | Text | Effect |
|-------|-----------|------|--------|
| Default | Red gradient | White | Serious |
| Hover | Brighten red | White | Shake |
| Active/Press | Scale 0.98 | White | Ripple |

**CSS:**

```css
.button-destructive {
  background: linear-gradient(135deg, #f43f5e 0%, #e11d48 100%);
  color: white;
  padding: var(--button-padding-md);
  border-radius: var(--radius-sm);
  border: none;
  font-weight: var(--font-semibold);
  cursor: pointer;
  transition: all 0.15s ease;
}

.button-destructive:hover {
  filter: brightness(1.1);
  animation: shake 0.3s ease;
}

@keyframes shake {
  0%, 100% { transform: translateX(0); }
  25% { transform: translateX(-2px); }
  75% { transform: translateX(2px); }
}

.button-destructive:active {
  transform: scale(0.98);
}
```

---

### 4. Ghost Button

**Purpose:** Low-emphasis action

```
┌─────────────────────┐
│   Cancel            │  ← Minimal styling
└─────────────────────┘
```

**CSS:**

```css
.button-ghost {
  background: transparent;
  color: var(--text-secondary);
  padding: var(--button-padding-md);
  border-radius: var(--radius-sm);
  border: none;
  font-weight: var(--font-medium);
  cursor: pointer;
  transition: all 0.15s ease;
}

.button-ghost:hover {
  color: var(--text-primary);
  background: rgba(255, 255, 255, 0.05);
}

.button-ghost:active {
  transform: scale(0.98);
}
```

---

### 5. Icon Button

**Purpose:** Action with icon only

```
┌───┐
│ ✕ │  ← Close, dismiss, etc.
└───┘
```

**CSS:**

```css
.button-icon {
  width: 40px;
  height: 40px;
  border-radius: var(--radius-full);
  background: transparent;
  border: none;
  color: var(--text-secondary);
  display: inline-flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.15s ease;
}

.button-icon:hover {
  background: rgba(255, 255, 255, 0.1);
  color: var(--text-primary);
}

.button-icon:active {
  transform: scale(0.95);
}
```

---

### 6. Floating Action Button (FAB)

**Purpose:** Primary action on screen

```
    ┌─────┐
    │  +  │  ← Floating
    └─────┘
```

**CSS:**

```css
.fab {
  width: 56px;
  height: 56px;
  border-radius: var(--radius-full);
  background: var(--gradient-taskflow);
  border: none;
  color: white;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
  transition: all 0.2s ease;
}

.fab:hover {
  transform: scale(1.05);
  box-shadow: var(--glow-primary);
}

.fab:active {
  transform: scale(0.95);
}
```

---

## Button Sizes

| Size | Height | Padding | Font Size | Icon Size |
|------|--------|---------|-----------|-----------|
| Small | 32px | 6px 12px | 12px | 14px |
| Medium | 40px | 10px 16px | 14px | 16px |
| Large | 44px | 12px 20px | 16px | 18px |
| XLarge | 52px | 14px 24px | 18px | 20px |

**CSS:**

```css
.button-sm { height: 32px; padding: 6px 12px; font-size: 12px; }
.button-md { height: 40px; padding: 10px 16px; font-size: 14px; }
.button-lg { height: 44px; padding: 12px 20px; font-size: 16px; }
.button-xl { height: 52px; padding: 14px 24px; font-size: 18px; }
```

---

## Button with Icon

```
┌─────────────────────┐
│ ←  Go Back          │  ← Icon + text
└─────────────────────┘
```

**CSS:**

```css
.button-with-icon {
  display: inline-flex;
  align-items: center;
  gap: 8px;
}

.button-with-icon .icon {
  width: 16px;
  height: 16px;
}

.button-with-icon.icon-start {
  flex-direction: row;
}

.button-with-icon.icon-end {
  flex-direction: row-reverse;
}
```

---

## Button States

### Loading State

```
┌─────────────────────┐
│   ⏳ Saving...      │  ← Spinner + dimmed
└─────────────────────┘
```

### Success State

```
┌─────────────────────┐
│   ✓ Saved!         │  ← Green flash
└─────────────────────┘
```

**CSS:**

```css
.button-success {
  background: var(--success);
  animation: success-flash 0.5s ease;
}

@keyframes success-flash {
  0% { background: var(--gradient-taskflow); }
  50% { background: #22c55e; box-shadow: 0 0 20px rgba(34, 197, 94, 0.5); }
  100% { background: var(--success); }
}
```

---

## Ripple Effect

```css
.button-ripple {
  position: relative;
  overflow: hidden;
}

.button-ripple::after {
  content: '';
  position: absolute;
  width: 100px;
  height: 100px;
  background: radial-gradient(circle, rgba(255,255,255,0.3) 0%, transparent 70%);
  border-radius: 50%;
  transform: scale(0);
  opacity: 0;
  pointer-events: none;
}

.button-ripple:active::after {
  transform: scale(2);
  opacity: 1;
  transition: transform 0.5s, opacity 0.3s;
}
```

---

## TypeScript Interface

```typescript
interface ButtonProps {
  variant?: 'primary' | 'secondary' | 'destructive' | 'ghost' | 'icon';
  size?: 'sm' | 'md' | 'lg' | 'xl';
  disabled?: boolean;
  loading?: boolean;
  success?: boolean;
  icon?: ReactNode;
  iconPosition?: 'start' | 'end';
  fullWidth?: boolean;
  onClick?: () => void;
  children: ReactNode;
}
```

---

## Best Practices

### DO:
- Use clear, action-oriented text
- Show loading state for async actions
- Provide haptic feedback
- Make touch targets at least 44×44px
- Use descriptive labels for icon-only buttons

### DON'T:
- Use "OK" - be specific
- Make disabled buttons look like errors
- Put more than one primary button per screen
- Use all caps (harder to read)
- Hide important actions in dropdowns

---

## Button Copy Guidelines

| Action | Good | Bad |
|--------|------|-----|
| Sign up | "Get Started" | "Submit" |
| Purchase | "Upgrade Now" | "Buy" |
| Cancel | "Keep Editing" | "Cancel" |
| Delete | "Delete Task" | "Remove" |
| Save | "Save Changes" | "Submit" |
| Continue | "Continue" | "Next" |
| Dismiss | "Got it" | "OK" |

---

## Accessibility

- **Focus Ring:** Always visible on keyboard navigation
- **ARIA Labels:** For icon-only buttons
- **Disabled State:** Clearly communicated
- **Loading State:** Screen reader announces "loading"

```html
<!-- Icon button with label -->
<button aria-label="Close dialog">
  <CloseIcon />
</button>

<!-- Loading state -->
<button aria-busy="true">
  <span aria-hidden="true">⏳</span>
  <span>Saving...</span>
</button>
```

---

*Part of the SOLO Emotional Component Library*
