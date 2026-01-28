# Loading States
**Not Boring Spinners - Engaging Waiting**
**Created:** 2026-01-28

---

## Philosophy

**Loading is part of the journey.** Make waiting feel like progress, not a pause.

- **Skeleton Screens:** Show content shape, not empty gray boxes
- **Progress Indicators:** Give users hope
- **Encouraging Messages:** "Almost there!" not "Loading..."
- **Staggered Animation:** Not everything loads at once

---

## 1. Skeleton Screens

### Shimmer Effect

```
┌─────────────────────────────────────┐
│  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓                 │  ← Shimmer
│  ▓▓▓  ▓▓▓▓                        │
│  ▓▓▓▓▓  ▓▓▓                        │
└─────────────────────────────────────┘
   ← Shimmer moves left to right
```

### CSS

```css
.skeleton {
  background: linear-gradient(
    90deg,
    var(--bg-surface) 0%,
    rgba(255, 255, 255, 0.05) 50%,
    var(--bg-surface) 100%
  );
  background-size: 200% 100%;
  animation: shimmer 1.5s infinite;
  border-radius: var(--radius-md);
}

@keyframes shimmer {
  0% { background-position: 200% 0; }
  100% { background-position: -200% 0; }
}

/* Different skeleton sizes */
.skeleton-text { height: 16px; width: 100%; }
.skeleton-text.short { width: 60%; }
.skeleton-title { height: 24px; width: 40%; margin-bottom: 8px; }
.skeleton-avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
}
.skeleton-circle {
  width: 60px;
  height: 60px;
  border-radius: 50%;
}
```

### Staggered Skeletons

```css
.skeleton:nth-child(1) { animation-delay: 0s; }
.skeleton:nth-child(2) { animation-delay: 0.1s; }
.skeleton:nth-child(3) { animation-delay: 0.2s; }
.skeleton:nth-child(4) { animation-delay: 0.3s; }
```

---

## 2. Progress Bar

### Animated Fill

```
Progress:  ████████░░ 80%
```

### CSS

```css
.progress-bar {
  width: 100%;
  height: 8px;
  background: var(--bg-elevated);
  border-radius: var(--radius-full);
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background: var(--gradient-taskflow);
  border-radius: var(--radius-full);
  transition: width 0.3s ease;
  position: relative;
}

.progress-fill::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(
    90deg,
    transparent 0%,
    rgba(255, 255, 255, 0.3) 50%,
    transparent 100%
  );
  animation: progress-shimmer 1.5s infinite;
}

@keyframes progress-shimmer {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(100%); }
}

/* Color changes based on progress */
.progress-fill[data-progress="25"] { background: var(--info); }
.progress-fill[data-progress="50"] { background: var(--taskflow-primary); }
.progress-fill[data-progress="75"] { background: var(--vibe-primary-pink); }
.progress-fill[data-progress="90"] { background: var(--celebration); }
.progress-fill[data-progress="100"] { background: var(--success); }
```

### Percentage Counter

```javascript
function animateValue(element, start, end, duration) {
  const range = end - start;
  const startTime = performance.now();

  function update(currentTime) {
    const elapsed = currentTime - startTime;
    const progress = Math.min(elapsed / duration, 1);
    const eased = 1 - Math.pow(1 - progress, 3); // Ease out cubic
    const current = Math.floor(start + range * eased);
    element.textContent = current + '%';

    if (progress < 1) {
      requestAnimationFrame(update);
    }
  }

  requestAnimationFrame(update);
}
```

---

## 3. Spinner

### Modern Minimal

```
     ◐
    ○ ○
   ○ ○ ○    ← Rotating dots
```

### CSS

```css
.spinner {
  width: 40px;
  height: 40px;
  position: relative;
}

.spinner::before,
.spinner::after {
  content: '';
  position: absolute;
  inset: 0;
  border: 3px solid transparent;
  border-radius: 50%;
}

.spinner::before {
  border-top-color: var(--taskflow-primary);
  animation: spin 0.8s linear infinite;
}

.spinner::after {
  border-right-color: var(--vibe-primary-pink);
  animation: spin 0.8s linear infinite reverse;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}
```

### Dot Spinner

```css
.dot-spinner {
  display: flex;
  gap: 8px;
  justify-content: center;
}

.dot-spinner .dot {
  width: 8px;
  height: 8px;
  background: var(--taskflow-primary);
  border-radius: 50%;
  animation: dot-bounce 1.4s ease-in-out infinite both;
}

.dot-spinner .dot:nth-child(1) { animation-delay: -0.32s; }
.dot-spinner .dot:nth-child(2) { animation-delay: -0.16s; }
.dot-spinner .dot:nth-child(3) { animation-delay: 0s; }

@keyframes dot-bounce {
  0%, 80%, 100% {
    transform: scale(0.6);
    opacity: 0.5;
  }
  40% {
    transform: scale(1);
    opacity: 1;
  }
}
```

---

## 4. Full-Page Loading

### Hero Animation

```
         ┌─────────────┐
         │             │
         │   [Logo]    │  ← Animated logo
         │             │
         │   Loading...│  ← Encouraging message
         │   ████░░░░░ │  ← Progress bar
         └─────────────┘
```

### CSS

```css
.full-page-loader {
  position: fixed;
  inset: 0;
  background: var(--bg-base);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 24px;
  z-index: 9999;
}

.loader-logo {
  width: 80px;
  height: 80px;
  animation: logo-pulse 2s ease-in-out infinite;
}

@keyframes logo-pulse {
  0%, 100% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.05);
    opacity: 0.9;
  }
}

.loader-message {
  font-size: var(--text-body-lg);
  color: var(--text-secondary);
}
```

### Encouraging Messages

```javascript
const loadingMessages = [
  "Almost there...",
  "Getting things ready...",
  "Preparing your workspace...",
  "Loading the good stuff...",
  "Just a moment more...",
  "Worth the wait...",
  "Building something great...",
];

function getRandomMessage() {
  return loadingMessages[Math.floor(Math.random() * loadingMessages.length)];
}

// Update message every 2 seconds
setInterval(() => {
  element.textContent = getRandomMessage();
}, 2000);
```

---

## 5. Pull to Refresh

### Animation States

```
Pulling...
     ↓
  [↓]     ↓
  [↓↓]   ↓↓
  [↓↓↓] ↓↓↓  ← Release to refresh
```

### CSS

```css
.pull-to-refresh {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 80px;
  opacity: 0;
  transition: opacity 0.2s ease;
}

.pull-to-refresh.visible {
  opacity: 1;
}

.pull-indicator {
  width: 40px;
  height: 40px;
  border: 3px solid var(--border-default);
  border-radius: 50%;
  position: relative;
  transition: all 0.3s ease;
}

.pull-indicator.pulling {
  transform: scale(1.2);
}

.pull-indicator.ready {
  background: var(--taskflow-primary);
  border-color: var(--taskflow-primary);
  animation: pulse-ready 1s infinite;
}

@keyframes pulse-ready {
  0%, 100% { box-shadow: 0 0 0 0 rgba(168, 85, 247, 0.4); }
  50% { box-shadow: 0 0 0 10px rgba(168, 85, 247, 0); }
}
```

---

## 6. Infinite Scroll Loading

### Bottom of List Indicator

```
┌─────────────────────────────────────┐
│  Item 1                             │
│  Item 2                             │
│  Item 3                             │
│                                     │
│         ● ● ●    ← Loading more     │
└─────────────────────────────────────┘
```

### CSS

```css
.infinite-loader {
  display: flex;
  justify-content: center;
  padding: 24px;
}

.infinite-loader .dots {
  display: flex;
  gap: 8px;
}

.infinite-loader .dot {
  width: 8px;
  height: 8px;
  background: var(--text-tertiary);
  border-radius: 50%;
  animation: dot-pulse 1.4s ease-in-out infinite both;
}

.infinite-loader .dot:nth-child(1) { animation-delay: -0.32s; }
.infinite-loader .dot:nth-child(2) { animation-delay: -0.16s; }
.infinite-loader .dot:nth-child(3) { animation-delay: 0s; }

@keyframes dot-pulse {
  0%, 80%, 100% {
    transform: scale(0.6);
    opacity: 0.5;
  }
  40% {
    transform: scale(1);
    opacity: 1;
  }
}
```

---

## 7. Button Loading State

### Spinner Inside Button

```
┌─────────────────────┐
│  ⏳ Saving...       │  ← Dimmed text + spinner
└─────────────────────┘
```

### CSS

```css
.button.loading {
  pointer-events: none;
  position: relative;
  color: transparent;
}

.button.loading::after {
  content: '';
  position: absolute;
  width: 16px;
  height: 16px;
  top: 50%;
  left: 50%;
  margin-left: -8px;
  margin-top: -8px;
  border: 2px solid rgba(255, 255, 255, 0.3);
  border-top-color: white;
  border-radius: 50%;
  animation: spin 0.8s linear infinite;
}

/* Large button loader */
.button.loading.lg::after {
  width: 20px;
  height: 20px;
  margin-left: -10px;
  margin-top: -10px;
}
```

---

## 8. Image Loading

### Placeholder to Loaded

```
Before:     After:
┌─────┐      ┌─────┐
│ ⚙️  │  →   │ IMG │
└─────┘      └─────┘
```

### CSS

```css
.image-loader {
  position: relative;
  overflow: hidden;
}

.image-loader img {
  opacity: 0;
  transition: opacity 0.3s ease;
}

.image-loader img.loaded {
  opacity: 1;
}

.image-loader::before {
  content: '';
  position: absolute;
  inset: 0;
  background: var(--bg-card);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1;
}

.image-loader img.loaded + .image-loader::before {
  display: none;
}

/* Blur-up effect */
.image-loader.blur-up img {
  filter: blur(10px);
  transform: scale(1.05);
}

.image-loader.blur-up img.loaded {
  filter: blur(0);
  transform: scale(1);
}
```

---

## 9. Pulsing Dot (Waiting)

### Connection Status

```
Status: ● Waiting for response...
```

### CSS

```css
.pulse-dot {
  width: 8px;
  height: 8px;
  background: var(--info);
  border-radius: 50%;
  animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
  0%, 100% {
    opacity: 1;
    transform: scale(1);
  }
  50% {
    opacity: 0.5;
    transform: scale(0.8);
  }
}

/* For connection states */
.pulse-dot.connecting { background: var(--warning); }
.pulse-dot.connected { background: var(--success); animation: none; }
.pulse-dot.error { background: var(--error); animation: none; }
```

---

## Loading Message Templates

| Context | Message | Subtext |
|---------|---------|---------|
| App Launch | "Getting things ready..." | "First time? This might take a moment." |
| Sync | "Syncing your data..." | "Almost there..." |
| Upload | "Uploading..." | "45% complete" |
| AI Processing | "AI is thinking..." | "This takes a few seconds" |
| Network | "Connecting..." | "Check your connection" |
| General | "Loading..." | "Just a moment..." |

---

## TypeScript Interfaces

```typescript
interface LoadingProps {
  type?: 'skeleton' | 'spinner' | 'dots' | 'bar';
  size?: 'sm' | 'md' | 'lg';
  message?: string;
  progress?: number; // 0-100
  fullScreen?: boolean;
}

interface SkeletonProps extends LoadingProps {
  width?: string;
  height?: string;
  circle?: boolean;
}

interface ProgressProps {
  value: number;
  max?: number;
  showPercentage?: boolean;
  color?: string;
  animated?: boolean;
}
```

---

## Best Practices

### DO:
- Show content shape (skeletons)
- Provide progress feedback
- Use encouraging messages
- Stagger animations naturally
- Set reasonable timeouts

### DON'T:
- Make users wait without feedback
- Use boring spinners exclusively
- Hide loading state
- Make loading animations too long
- Block entire interface unnecessarily

---

## Performance

- **Lazy Load:** Load images as needed
- **Preload:** Critical assets before needed
- **Code Split:** Load only what's needed
- **Skeleton First:** Show skeleton, then content
- **Optimize:** Keep animations 60fps

---

## Accessibility

- **ARIA:** Announce loading state to screen readers
- **Focus:** Manage focus during loading
- **Timeouts:** Provide error if loading fails
- **Escapable:** Allow canceling long loads

```html
<div role="status" aria-live="polite">
  <span class="sr-only">Loading</span>
  <div class="spinner"></div>
  <span>Loading your tasks...</span>
</div>
```

---

*Part of the SOLO Emotional Component Library*
