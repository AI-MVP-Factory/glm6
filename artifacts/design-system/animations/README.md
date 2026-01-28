# Animation Library
**Delightful Micro-Interactions**
**Created:** 2026-01-28

---

## Philosophy

**Animation is personality in motion.** Every animation should feel natural, not forced.

- **Purposeful:** Every animation has a reason
- **Subtle:** Less is more
- **Smooth:** 60fps always
- **Respectful:** Honors prefers-reduced-motion

---

## Animation Primitives

### Duration Scale

```css
/* Duration tokens */
--duration-instant: 50ms;    /* Micro-interactions */
--duration-fast: 150ms;      /* Button press */
--duration-normal: 200ms;    /* Transition */
--duration-slow: 300ms;      /* Modal open */
--duration-slower: 500ms;    /* Celebration */
--duration-slowest: 1000ms;  /* Page transition */
```

### Easing Functions

```css
/* Ease curves */
--ease-out: cubic-bezier(0, 0, 0.2, 1);           /* Fast out, smooth stop */
--ease-in: cubic-bezier(0.4, 0, 1, 1);            /* Slow start, fast end */
--ease-in-out: cubic-bezier(0.4, 0, 0.2, 1);      /* Slow both ends */
--ease-bounce: cubic-bezier(0.34, 1.56, 0.64, 1); /* Bouncy */
--ease-spring: cubic-bezier(0.175, 0.885, 0.32, 1.275); /* Spring */
```

---

## 1. Entry Animations

### Fade In + Slide Up

```css
@keyframes fade-in-up {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-in-up {
  animation: fade-in-up 0.3s var(--ease-out);
}
```

### Stagger List Items

```css
.list-item {
  opacity: 0;
  animation: fade-in-up 0.3s var(--ease-out) forwards;
}

.list-item:nth-child(1) { animation-delay: 0ms; }
.list-item:nth-child(2) { animation-delay: 50ms; }
.list-item:nth-child(3) { animation-delay: 100ms; }
.list-item:nth-child(4) { animation-delay: 150ms; }
.list-item:nth-child(5) { animation-delay: 200ms; }
```

### Scale In (Bounce)

```css
@keyframes scale-in-bounce {
  0% {
    opacity: 0;
    transform: scale(0);
  }
  50% {
    transform: scale(1.05);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

.scale-in-bounce {
  animation: scale-in-bounce 0.5s var(--ease-bounce);
}
```

### Hero Animation

```css
@keyframes hero-reveal {
  0% {
    opacity: 0;
    transform: translateY(40px) scale(0.95);
  }
  100% {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

.hero-reveal {
  animation: hero-reveal 0.8s var(--ease-spring);
}
```

---

## 2. Exit Animations

### Fade Out + Scale Down

```css
@keyframes fade-out-down {
  from {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
  to {
    opacity: 0;
    transform: translateY(20px) scale(0.95);
  }
}

.fade-out-down {
  animation: fade-out-down 0.2s var(--ease-in);
}
```

### Slide Out (Directional)

```css
/* Slide out to right (forward nav) */
@keyframes slide-out-right {
  to {
    transform: translateX(100%);
    opacity: 0;
  }
}

/* Slide out from right (back nav) */
@keyframes slide-out-left {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-30%);
    opacity: 0;
  }
}

.slide-out-right {
  animation: slide-out-right 0.2s var(--ease-in);
}
```

### Dismiss (Swipe Away)

```css
@keyframes dismiss {
  0% {
    transform: translateX(0) rotate(0);
    opacity: 1;
  }
  100% {
    transform: translateX(100%) rotate(5deg);
    opacity: 0;
  }
}

.dismiss {
  animation: dismiss 0.15s var(--ease-in);
}
```

---

## 3. Interaction Feedback

### Button Press

```css
.button:active {
  transform: scale(0.98);
  transition: transform 0.1s var(--ease-out);
}
```

### Card Hover

```css
.card:hover {
  transform: translateY(-4px);
  box-shadow: var(--elevation-3);
  transition: all 0.2s var(--ease-out);
}
```

### Toggle Switch

```css
@keyframes toggle-switch {
  0% { transform: translateX(0); }
  50% { transform: translateX(120%) scale(1.1); }
  100% { transform: translateX(120%) scale(1); }
}

.switch.active .thumb {
  animation: toggle-switch 0.3s var(--ease-spring);
}
```

### Checkbox Bounce

```css
@keyframes checkbox-check {
  0% { transform: scale(0); }
  50% { transform: scale(1.2); }
  100% { transform: scale(1); }
}

.checkbox:checked .checkmark {
  animation: checkbox-check 0.3s var(--ease-bounce);
}
```

### Radio Selection

```css
@keyframes radio-select {
  0% { transform: scale(0); }
  100% { transform: scale(1); }
}

.radio:checked::before {
  animation: radio-select 0.2s var(--ease-bounce);
}
```

---

## 4. Celebration Animations

### Confetti Burst

```css
@keyframes confetti-fall {
  0% {
    transform: translateY(0) rotate(0deg);
    opacity: 1;
  }
  100% {
    transform: translateY(100vh) rotate(720deg);
    opacity: 0;
  }
}

.confetti {
  animation: confetti-fall 1.5s var(--ease-out) forwards;
}
```

### Success Checkmark Draw

```css
@keyframes checkmark-draw {
  0% {
    stroke-dashoffset: 100;
  }
  100% {
    stroke-dashoffset: 0;
  }
}

.checkmark-path {
  stroke-dasharray: 100;
  stroke-dashoffset: 100;
  animation: checkmark-draw 0.5s var(--ease-out) forwards;
}
```

### Progress Fill

```css
@keyframes progress-fill {
  from {
    width: 0%;
  }
  to {
    width: var(--progress);
  }
}

.progress-bar {
  animation: progress-fill var(--duration, 300ms) var(--ease-out);
}
```

### Streak Fire Pulse

```css
@keyframes fire-pulse {
  0%, 100% {
    transform: scale(1);
    filter: brightness(1);
  }
  50% {
    transform: scale(1.1);
    filter: brightness(1.2);
  }
}

.streak-fire {
  animation: fire-pulse 2s var(--ease-in-out) infinite;
}
```

### Achievement Reveal

```css
@keyframes achievement-reveal {
  0% {
    transform: scale(0) rotate(-180deg);
    opacity: 0;
  }
  60% {
    transform: scale(1.1) rotate(10deg);
  }
  100% {
    transform: scale(1) rotate(0deg);
    opacity: 1;
  }
}

.achievement-icon {
  animation: achievement-reveal 0.8s var(--ease-bounce);
}
```

---

## 5. Loading Animations

### Skeleton Shimmer

```css
@keyframes shimmer {
  0% {
    background-position: -200% 0;
  }
  100% {
    background-position: 200% 0;
  }
}

.skeleton {
  background: linear-gradient(
    90deg,
    var(--bg-surface) 0%,
    rgba(255, 255, 255, 0.05) 50%,
    var(--bg-surface) 100%
  );
  background-size: 200% 100%;
  animation: shimmer 1.5s infinite;
}
```

### Spinner Rotation

```css
@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

.spinner {
  animation: spin 0.8s linear infinite;
}
```

### Progress Bar Animation

```css
@keyframes progress-pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0.8;
  }
}

.progress-fill.animated {
  animation: progress-fill var(--duration) var(--ease-out),
             progress-pulse 2s ease-in-out infinite;
}
```

### Pulsing Dot (Waiting)

```css
@keyframes pulse-dot {
  0%, 100% {
    opacity: 1;
    transform: scale(1);
  }
  50% {
    opacity: 0.5;
    transform: scale(0.8);
  }
}

.pulse-dot {
  animation: pulse-dot 2s var(--ease-in-out) infinite;
}
```

---

## 6. Page Transitions

### Slide Transition (Mobile)

```css
@keyframes page-slide-in {
  from {
    transform: translateX(100%);
  }
  to {
    transform: translateX(0);
  }
}

@keyframes page-slide-out {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-30%);
    opacity: 0;
  }
}

.page-enter {
  animation: page-slide-in 0.3s var(--ease-out);
}

.page-exit {
  animation: page-slide-out 0.3s var(--ease-in);
}
```

### Fade Transition

```css
@keyframes page-fade-in {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes page-fade-out {
  from { opacity: 1; }
  to { opacity: 0; }
}

.page-enter.fade {
  animation: page-fade-in 0.2s var(--ease-out);
}

.page-exit.fade {
  animation: page-fade-out 0.2s var(--ease-in);
}
```

---

## 7. Gesture Feedback

### Swipe to Delete

```css
@keyframes swipe-hint {
  0%, 100% {
    transform: translateX(0);
  }
  25% {
    transform: translateX(10px);
  }
  75% {
    transform: translateX(10px);
  }
}

.swipe-hint {
  animation: swipe-hint 2s ease-in-out 2;
}
```

### Pull to Refresh

```css
@keyframes pull-indicator {
  0% {
    transform: rotate(0deg) scale(1);
  }
  100% {
    transform: rotate(180deg) scale(1.2);
  }
}

.pull-indicator.pulling {
  animation: pull-indicator 0.3s var(--ease-out);
}
```

### Pinch to Zoom

```css
.zoomable {
  transition: transform 0.2s var(--ease-out);
}

.zoomable.zooming {
  transform: scale(1.5);
}
```

---

## 8. Micro-Interactions

### Heart/Like Animation

```css
@keyframes heart-pop {
  0% { transform: scale(1); }
  25% { transform: scale(0.8); }
  50% { transform: scale(1.3); }
  75% { transform: scale(0.9); }
  100% { transform: scale(1); }
}

.heart:active {
  animation: heart-pop 0.4s var(--ease-bounce);
}
```

### Haptic Feedback Pattern

```javascript
// Timing for haptic feedback
const hapticPatterns = {
  light: 0.01,    // 10ms - subtle confirmation
  medium: 0.02,   // 20ms - button press
  heavy: 0.03,    // 30ms - important action
  success: [0.02, 0.05, 0.02], // celebration
  error: [0.03, 0.03, 0.03],    // warning
};

function triggerHaptic(pattern) {
  navigator.vibrate(pattern);
}
```

### Focus Ring Animation

```css
@keyframes focus-ring-expand {
  from {
    transform: scale(0.95);
    opacity: 0;
  }
  to {
    transform: scale(1);
    opacity: 1;
  }
}

.focus-visible:focus::after {
  content: '';
  position: absolute;
  inset: -4px;
  border: 2px solid var(--taskflow-primary);
  border-radius: inherit;
  animation: focus-ring-expand 0.2s var(--ease-out);
}
```

---

## 9. Reduced Motion Support

```css
@media (prefers-reduced-motion: reduce) {
  /* Respect user preference */
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }

  /* Keep essential animations */
  .essential-animation {
    animation-duration: 0.3s !important;
  }
}

/* JavaScript check */
const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)');

function animateWithFallback(element, animationName, fallbackClass) {
  if (prefersReducedMotion.matches) {
    element.classList.add(fallbackClass);
  } else {
    element.style.animation = animationName;
  }
}
```

---

## 10. Lottie JSON Snippets

### Confetti

```json
{
  "v": "5.5.7",
  "fr": 60,
  "ip": 0,
  "op": 1,
  "w": 512,
  "h": 512,
  "nm": "Confetti",
  "ddd": 0,
  "assets": [],
  "layers": [{
    "ty": 4,
    "nm": "Confetti Particle",
    "sr": 1,
    "ks": {
      "o": {"a": 0, "k": 0},
      "r": {"a": 0, "k": 180},
      "s": {"a": 1, "k": [8, 8]},
      "p": {"a": 0, "k": [256, 256]}
    },
    "ao": 0,
    "shapes": [{
      "ty": "gr",
      "it": [{
        "d": {
          "a": 0,
          "k": [0, 0, 512, 512]
        },
        "s": {"a": 0, "k": 100}
      }]
    }],
    "ks": {
      "o": {"a": 1, "k": 100},
      "r": {"a": 0, "k": 0},
      "p": {"a": 0, "k": [0, 500]}
    }
  }]
}
```

### Success Checkmark

```json
{
  "v": "5.5.7",
  "fr": 60,
  "ip": 0,
  "op": 1,
  "w": 100,
  "h": 100,
  "nm": "Checkmark",
  "layers": [{
    "ty": 4,
    "nm": "Check",
    "sr": 1,
    "ks": {
      "o": {"a": 1, "k": 0},
      "r": {"a": 0, "k": -45},
      "s": {"a": 0, "k": [100, 100]},
      "p": {"a": 0, "k": [50, 50]}
    },
    "shapes": [{
      "ty": "gr",
      "it": [{
        "ty": "st",
        "d": {
          "a": 0,
          "k": {
            "i": [[0, 0], [30, 30], [30, 70], [0, 100]]
          }
        },
        "s": {"a": 0, "k": 10}
      }]
    }],
    "ks": {
      "o": {"a": 0, "k": 100},
      "r": {"a": 0, "k": 0},
      "p": {"a": 0, "k": [50, 50]}
    }
  }]
}
```

---

## Quick Reference

| Animation | Duration | Easing | Use For |
|-----------|----------|--------|---------|
| Button press | 100ms | ease-out | Click feedback |
| Card hover | 200ms | ease-out | Focus indication |
| Modal open | 300ms | ease-bounce | Draw attention |
| Confetti | 1500ms | ease-out | Celebration |
| Skeleton | 1500ms | linear | Loading |
| Page transition | 200ms | ease-in-out | Navigation |

---

## Performance Guidelines

- **60fps target:** All animations must run at 60fps
- **Transform > Properties:** Use transform/opacity for better performance
- **Will-change:** Use sparingly for heavy animations
- **Contain:** Use `contain: layout paint` for animated elements
- **GPU acceleration:** Use `transform: translateZ(0)` to force GPU

```css
/* Performance optimization */
.animated-element {
  will-change: transform, opacity;
  contain: layout style paint;
}

/* Remove when done */
.animation-finished {
  will-change: auto;
}
```

---

*Part of the SOLO Emotional Design System*
