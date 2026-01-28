# Screenshot Templates
**App Store Screenshots - Production Ready**
**Created:** 2026-01-28

---

## Overview

These templates provide a consistent format for App Store screenshots across all SOLO products. Each template is designed to showcase features while maintaining brand consistency.

**Products:**
- TaskFlow v3 - Productivity that celebrates
- TeenPopTastic (Vibe) - Music that connects
- MemeCraftVibe - Memes that delight

---

## Device Frames

### iPhone 15 Pro Max

**Dimensions:** 1290 × 2796 pixels

```css
.iphone-frame {
  width: 1290px;
  height: 2796px;
  background: #000;
  border-radius: 80px;
  position: relative;
  overflow: hidden;
}

/* Dynamic Island placeholder */
.dynamic-island {
  position: absolute;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  width: 200px;
  height: 40px;
  background: #000;
  border-radius: 20px;
}

/* Home indicator */
.home-indicator {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  width: 240px;
  height: 6px;
  background: rgba(255, 255, 255, 0.3);
  border-radius: 3px;
}
```

### iPad 13"

**Dimensions:** 2048 × 2732 pixels

```css
.ipad-frame {
  width: 2048px;
  height: 2732px;
  background: #000;
  border-radius: 40px;
  position: relative;
  overflow: hidden;
}

/* Camera placeholder */
.ipad-camera {
  position: absolute;
  top: 24px;
  left: 50%;
  transform: translateX(-50%);
  width: 16px;
  height: 16px;
  background: #000;
  border-radius: 8px;
}

/* Home indicator */
.ipad .home-indicator {
  width: 620px;
}
```

---

## Layout Templates

### Template 1: Single Screen with Caption

**Use:** Hero screenshot, primary feature

```
┌─────────────────────────────────────┐
│                                     │
│                                     │
│         [APP SCREENSHOT]            │
│                                     │
│                                     │
│                                     │
├─────────────────────────────────────┤
│                                     │
│   Celebrate your wins               │  ← Caption
│                                     │
└─────────────────────────────────────┘
```

**Specs:**
- Screenshot: 85% of height
- Caption area: 15% of height
- Caption background: Gradient or solid
- Caption text: White, bold, 32px

### Template 2: Two-Screen Comparison

**Use:** Before/after, comparison

```
┌─────────────────────────────────────┐
│         Before          After       │
│  ┌──────────┐    ┌──────────┐      │
│  │  SCREEN  │    │  SCREEN  │      │
│  └──────────┘    └──────────┘      │
│                                     │
│    Stress          Success!        │
└─────────────────────────────────────┘
```

**Specs:**
- Each screen: 45% of width
- Gap: 10% of width
- Labels below each screen

### Template 3: Three-Screen Feature Flow

**Use:** Feature sequence

```
┌─────────────────────────────────────┐
│   ①           ②           ③        │
│ ┌────┐      ┌────┐      ┌────┐     │
│ │    │      │    │      │    │     │
│ └────┘      └────┘      └────┘     │
│                                     │
│  Create      Plan       Celebrate  │
└─────────────────────────────────────┘
```

**Specs:**
- Each screen: 28% of width
- Gap: 8% between screens
- Number circles: 48px, gradient background
- Labels: 16px below each screen

---

## Text Overlay System

### Headline Styles

```css
/* Hero Headline */
.screenshot-headline {
  font-family: var(--font-display);
  font-size: 48px;
  font-weight: var(--font-bold);
  color: white;
  text-align: center;
  line-height: 1.1;
}

/* Subheadline */
.screenshot-subheadline {
  font-family: var(--font-body);
  font-size: 24px;
  font-weight: var(--font-medium);
  color: rgba(255, 255, 255, 0.9);
  text-align: center;
  line-height: 1.3;
}
```

### Overlay Backgrounds

```css
/* Bottom gradient fade */
.overlay-bottom {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 40%;
  background: linear-gradient(
    to top,
    rgba(0, 0, 0, 0.8) 0%,
    rgba(0, 0, 0, 0) 100%
  );
}

/* Full overlay with cutout */
.overlay-full {
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.3);
  backdrop-filter: blur(20px);
}
```

### Callout Style

```css
/* Points to feature */
.callout {
  position: absolute;
  display: flex;
  align-items: center;
  gap: 8px;
}

.callout-line {
  width: 2px;
  height: 40px;
  background: var(--celebration);
}

.callout-dot {
  width: 12px;
  height: 12px;
  background: var(--celebration);
  border-radius: 50%;
  box-shadow: 0 0 10px var(--celebration);
}

.callout-label {
  background: var(--celebration);
  color: black;
  padding: 4px 12px;
  border-radius: var(--radius-full);
  font-size: 14px;
  font-weight: var(--font-semibold);
}
```

---

## Badge System

### Feature Badges

```css
/* NEW badge */
.badge-new {
  background: linear-gradient(135deg, #22c55e, #16a34a);
  color: white;
  padding: 4px 12px;
  border-radius: var(--radius-full);
  font-size: 12px;
  font-weight: var(--font-bold);
  letter-spacing: 0.05em;
}

/* PRO badge */
.badge-pro {
  background: linear-gradient(135deg, #fbbf24, #f59e0b);
  color: black;
  padding: 4px 12px;
  border-radius: var(--radius-full);
  font-size: 12px;
  font-weight: var(--font-bold);
  letter-spacing: 0.05em;
}
```

---

## Export Specifications

### File Naming

```
[app]-[screen]-[device]-[locale].png

Examples:
taskflow-dashboard-iphone-15pm-en.png
taskflow-kanban-ipad-13-en.png
vibe-profile-iphone-15pm-en.png
meme-gallery-iphone-15pm-en.png
```

### Export Settings

| Setting | Value |
|---------|-------|
| Format | PNG (lossless) |
| Quality | Highest |
| Color Profile | sRGB |
| Resolution | 1x (use @2x for retina preview) |
| File Size | Under 500KB each |

---

## App-Specific Templates

### TaskFlow v3

**Color Palette:**
- Primary: #a855f7 (Purple)
- Accent: #fbbf24 (Celebration Gold)
- Gradient: Purple to Indigo

**Screenshot List:**
1. Dashboard with celebration
2. Natural language input parsing
3. Kanban board drag-drop
4. AI Daily Focus selection
5. Analytics dashboard
6. Goal progress
7. Pomodoro timer
8. Dark mode toggle
9. Task detail view
10. Settings/profile

### TeenPopTastic (Vibe)

**Color Palette:**
- Primary: #ec4899 (Pink)
- Secondary: #8b5cf6 (Purple)
- Gradient: Pink to Purple

**Screenshot List:**
1. Music profile reveal
2. Vibe matching interface
3. Mutual match celebration
4. Music moment with song
5. Group vibe interface
6. Daily vibe check
7. Music discovery
8. Safety features
9. Onboarding
10. Settings

### MemeCraftVibe

**Color Palette:**
- Primary: #22d3ee (Cyan)
- Secondary: #6366f1 (Indigo)
- Gradient: Cyan to Indigo

**Screenshot List:**
1. Template gallery (trending)
2. AI text input
3. Generated meme result
4. Share sheet
5. Saved/favorites
6. Text search
7. Editor interface
8. Onboarding
9. Premium features
10. Settings

---

## Figma Template Structure

```
Screenshot Templates
├── 📱 iPhone 15 Pro Max
│   ├── TaskFlow
│   │   ├── 01-Hero
│   │   ├── 02-Feature
│   │   └── ...
│   ├── Vibe
│   └── MemeCraft
├── 📱 iPad 13"
│   ├── TaskFlow
│   ├── Vibe
│   └── MemeCraft
└── 🎨 Overlays
    ├── Text
    ├── Badges
    └── Backgrounds
```

---

## Production Checklist

### Before Export

- [ ] All text is legible at thumbnail size
- [ ] No UI glitches or artifacts
- [ ] Consistent style across all screenshots
- [ ] Brand colors accurate
- [ ] No status bar (use clean frame)
- [ ] No personal/sensitive data

### After Export

- [ ] File size under 500KB
- [ ] Resolution matches spec
- [ ] File naming follows convention
- [ ] Organized in correct folders
- [ ] Backed up to cloud storage

---

## A/B Testing Variations

### Test Variables

1. **Hero Screenshot**
   - Version A: Dashboard
   - Version B: Celebration moment

2. **Caption Style**
   - Version A: Emotional ("Celebrate your wins")
   - Version B: Functional ("Task management app")

3. **Layout**
   - Version A: Single screen
   - Version B: Feature comparison

4. **Order**
   - Version A: Benefits first
   - Version B: Features first

---

## Quick Reference

| Device | Resolution | Max Screens |
|--------|------------|-------------|
| iPhone 15 Pro Max | 1290×2796 | 10 |
| iPhone 15 Pro | 1290×2796 | 10 |
| iPad 13" | 2048×2732 | 10 |

---

## Usage Guide

1. **Open Figma template**
2. **Select app (TaskFlow/Vibe/MemeCraft)**
3. **Select device (iPhone/iPad)**
4. **Replace screenshot content**
5. **Adjust overlay text**
6. **Export as PNG**
7. **Verify file size and naming**
8. **Organize in folder structure**

---

*Part of the SOLO Design System*
*For use with App Store Connect*
