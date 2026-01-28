# Card Components
**Breathing, Alive, Interactive**
**Created:** 2026-01-28

---

## Philosophy

**Cards are containers for stories.** Each card holds content, not just data.

- **Breathing Room:** Generous padding, not cramped
- **Subtle Depth:** Elevation through borders, not heavy shadows
- **Hover Feedback:** Cards respond to interaction
- **Purposeful:** Every element has a reason

---

## 1. Task Card (TaskFlow)

### Default State

```
┌─────────────────────────────────────┐
│ ◉  Buy groceries for dinner         │  ← Checkbox + task
│     📅 Today 3pm                    │  ← Meta info
│     🏷️ Shopping                     │  ← Category tag
└─────────────────────────────────────┘
```

### Hover State

```
┌─────────────────────────────────────┐
│ ◉  Buy groceries for dinner     ⋮   │  ← Actions appear
│     📅 Today 3pm                    │  ← Subtle lift + glow
│     🏷️ Shopping                     │
└─────────────────────────────────────┘
```

### Drag State

```
┌─────────────────────────────────────┐
│ ◉  Buy groceries for dinner         │  ← Lift effect
│     📅 Today 3pm                    │  ← Shadow
│     🏷️ Shopping                     │
└─────────────────────────────────────┘
    ⋮⋮⋮  ← Drag handle visible
```

### Completed State

```
┌─────────────────────────────────────┐
│ ✓  Buy groceries for dinner         │  ← Dimmed + check
│     📅 Completed 2pm ago             │  ← Timestamp
│     🏷️ Shopping                     │
└─────────────────────────────────────┘
```

### CSS

```css
.task-card {
  background: var(--bg-card);
  border: var(--border-subtle);
  border-radius: var(--radius-md);
  padding: 12px 16px;
  cursor: grab;
  transition: all 0.15s ease;
  position: relative;
}

.task-card:hover {
  border: var(--border-default);
  transform: translateY(-2px);
  box-shadow: var(--elevation-2);
}

.task-card.dragging {
  opacity: 0.9;
  transform: rotate(2deg) scale(1.02);
  box-shadow: var(--elevation-4);
  cursor: grabbing;
}

.task-card.completed {
  opacity: 0.6;
}

.task-card.completed .task-title {
  text-decoration: line-through;
  color: var(--text-tertiary);
}

/* Checkbox animation */
.task-checkbox {
  transition: all 0.2s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.task-checkbox:checked {
  animation: checkbox-bounce 0.3s ease;
}

@keyframes checkbox-bounce {
  0% { transform: scale(1); }
  50% { transform: scale(1.2); }
  100% { transform: scale(1); }
}
```

---

## 2. Profile Card (Vibe)

### Design

```
┌─────────────────────────────────────┐
│         ┌─────────┐                 │
│         │   🎵   │  Music Lover     │  ← Avatar + personality
│         └─────────┘                 │
│                                     │
│  Top Artists:                        │
│  🎤 Taylor Swift 🎤 Drake 🎤 Weeknd │
│                                     │
│  Vibe Compatibility: 85%             │  ← Score prominent
│                                     │
│  [Send Vibe Wave]                   │
└─────────────────────────────────────┘
```

### CSS

```css
.profile-card {
  background: var(--bg-card);
  border: var(--border-subtle);
  border-radius: var(--radius-lg);
  padding: 20px;
  text-align: center;
  transition: all 0.2s ease;
}

.profile-card:hover {
  border: var(--border-default);
  transform: translateY(-4px);
}

.profile-avatar {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  border: 3px solid var(--vibe-gradient);
  padding: 3px;
  margin: 0 auto 12px;
}

.profile-avatar-ring {
  /* Activity ring that glows */
  animation: pulse-ring 2s ease-in-out infinite;
}

@keyframes pulse-ring {
  0%, 100% { box-shadow: 0 0 0 0 rgba(236, 72, 153, 0.4); }
  50% { box-shadow: 0 0 0 8px rgba(236, 72, 153, 0); }
}

.compatibility-score {
  font-size: 32px;
  font-weight: var(--font-bold);
  background: var(--vibe-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

---

## 3. Meme Card (MemeCraft)

### Template Card

```
┌─────────────────────────────────────┐
│                                     │
│         [Meme Template]             │  ← Preview
│                                     │
│  🔥 Trending #3                     │
│                                     │
│  [Use this template]                │
└─────────────────────────────────────┘
```

### Generated Meme Card

```
┌─────────────────────────────────────┐
│                                     │
│     [Generated Meme]                │
│                                     │
│  [Share] [Save] [Regenerate]        │  ← Actions
└─────────────────────────────────────┘
```

### CSS

```css
.meme-card {
  background: var(--bg-card);
  border: var(--border-subtle);
  border-radius: var(--radius-md);
  overflow: hidden;
  transition: all 0.2s ease;
  cursor: pointer;
}

.meme-card:hover {
  border: var(--border-default);
  transform: scale(1.02);
  box-shadow: 0 0 20px rgba(34, 211, 238, 0.2);
}

.meme-card .trending-badge {
  position: absolute;
  top: 8px;
  right: 8px;
  background: linear-gradient(135deg, #f59e0b, #ef4444);
  color: white;
  font-size: var(--text-micro-md);
  font-weight: var(--font-semibold);
  padding: 4px 8px;
  border-radius: var(--radius-full);
}

.meme-card .trending-badge::before {
  content: '🔥 ';
}
```

---

## 4. Notification Card

### Slide-in Animation

```
From right:
                      ┌──────────┐
                  →    │          │
                      │  Alert!  │
                      └──────────┘
```

### Dismissible Swipe

```
← Swipe to dismiss
┌─────────────────────────────────────┐
│  ✓ Task completed!           [×]    │
│     Great work on that one          │
└─────────────────────────────────────┘
```

### CSS

```css
.notification-card {
  position: fixed;
  top: 16px;
  right: 16px;
  max-width: 320px;
  background: var(--bg-elevated);
  border: var(--border-default);
  border-radius: var(--radius-lg);
  box-shadow: var(--elevation-4);
  padding: 12px 16px;
  animation: slide-in 0.3s ease;
  z-index: 9999;
}

.notification-card.success {
  border-left: 4px solid var(--success);
}

.notification-card.error {
  border-left: 4px solid var(--error);
}

@keyframes slide-in {
  from {
    transform: translateX(100%);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}

@keyframes slide-out {
  to {
    transform: translateX(100%);
    opacity: 0;
  }
}
```

---

## 5. Achievement Card

### Reveal Animation

```
Initial:    →    Revealed:
┌─────┐          ┌─────────────────┐
│  ?  │    →     │      🏆         │
└─────┘          │  First Win!     │
                  │  Complete...    │
                  └─────────────────┘
```

### CSS

```css
.achievement-card {
  background: var(--bg-card);
  border: var(--border-default);
  border-radius: var(--radius-lg);
  padding: 24px;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.achievement-card::before {
  content: '';
  position: absolute;
  inset: 0;
  background: var(--gradient-party);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.achievement-card.revealed::before {
  opacity: 0.1;
}

.achievement-icon {
  font-size: 48px;
  animation: achievement-pop 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
}

@keyframes achievement-pop {
  0% { transform: scale(0) rotate(-180deg); opacity: 0; }
  100% { transform: scale(1) rotate(0deg); opacity: 1; }
}

.achievement-card.revealed .achievement-icon {
  filter: drop-shadow(0 0 10px rgba(251, 191, 36, 0.5));
}
```

---

## 6. Stats Card

### Mini Sparkline

```
┌─────────────────────────────────────┐
│  Tasks Completed                    │
│                                     │
│  127              ━━━━━━━━━━▁      │  ← Sparkline
│     ↑ 12% from last week             │
└─────────────────────────────────────┘
```

### CSS

```css
.stats-card {
  background: var(--bg-card);
  border: var(--border-subtle);
  border-radius: var(--radius-md);
  padding: 16px;
}

.stats-value {
  font-size: var(--text-display-xl);
  font-weight: var(--font-bold);
  background: var(--gradient-taskflow);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.stats-label {
  font-size: var(--text-body-sm);
  color: var(--text-tertiary);
}

.stats-change {
  font-size: var(--text-body-md);
  font-weight: var(--font-medium);
}

.stats-change.positive {
  color: var(--success);
}

.stats-change.negative {
  color: var(--error);
}
```

---

## 7. Swipe Actions

### iOS Style Swipe

```
Normal:     Swipe left:
┌─────────┐  ┌─────┬─────┬─────┐
│  Task   │  │Done │ Snooze│Delete│
└─────────┘  └─────┴─────┴─────┘
```

### CSS

```css
.swipeable-card {
  position: relative;
  overflow: hidden;
}

.swipeable-card .actions {
  position: absolute;
  right: 0;
  top: 0;
  bottom: 0;
  display: flex;
  transform: translateX(100%);
  transition: transform 0.2s ease;
}

.swipeable-card.swiping .actions {
  transform: translateX(0);
}

.swipe-action {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 20px;
  color: white;
}

.swipe-action.complete { background: var(--success); }
.swipe-action.snooze { background: var(--warning); }
.swipe-action.delete { background: var(--error); }
```

---

## Card Sizes

| Size | Padding | Use Case |
|------|---------|----------|
| Compact | 8px 12px | Dense lists |
| Default | 12px 16px | Standard cards |
| Comfortable | 16px 20px | Emphasized content |
| Spacious | 20px 24px | Feature highlights |

---

## TypeScript Interfaces

```typescript
interface CardProps {
  variant?: 'default' | 'elevated' | 'outlined' | 'flat';
  padding?: 'compact' | 'default' | 'comfortable' | 'spacious';
  hover?: boolean;
  clickable?: boolean;
  draggable?: boolean;
  completed?: boolean;
  onClick?: () => void;
  children: ReactNode;
}

interface TaskCardProps extends CardProps {
  task: {
    id: string;
    title: string;
    completed: boolean;
    dueDate?: Date;
    category?: string;
  };
  onToggle?: (id: string) => void;
  onDelete?: (id: string) => void;
}
```

---

## Best Practices

### DO:
- Keep content focused (one primary action)
- Use subtle elevation for depth
- Provide clear hover feedback
- Make swipe actions discoverable
- Show card state clearly (completed, disabled)

### DON'T:
- Overload cards with too much info
- Use heavy shadows
- Hide actions without hints
- Make cards too tall (scrolling within cards)
- Use inconsistent spacing

---

## Accessibility

- **Keyboard:** Cards are focusable when clickable
- **Screen Reader:** Card content is announced
- **Touch:** 44×44px minimum touch targets
- **Focus:** Visible focus indicator

```html
<div
  class="card"
  role="button"
  tabindex="0"
  aria-label="View task: Buy groceries"
>
  <!-- Card content -->
</div>
```

---

*Part of the SOLO Emotional Component Library*
