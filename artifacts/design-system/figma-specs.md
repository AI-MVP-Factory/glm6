# Figma Mockup Specifications
**Screen-by-Screen Guide for All 3 Apps**
**Created:** 2026-01-28

---

## Overview

This document provides detailed specifications for all Figma mockups needed for the 3 SOLO MVPs. Use these specifications to create comprehensive, production-ready designs.

**Products:**
- TaskFlow v3 - Productivity that celebrates
- TeenPopTastic (Vibe) - Music that connects
- MemeCraftVibe - Memes that delight

---

## Figma File Structure

```
SOLO Design System
├── Design Tokens (shared)
│   ├── Colors
│   ├── Typography
│   ├── Components
│   └── Styles
│
├── TaskFlow v3
│   ├── Onboarding (4 screens)
│   ├── App Screens (7 screens)
│   └── App Store Screenshots (10 screens)
│
├── TeenPopTastic (Vibe)
│   ├── Onboarding (3 screens)
│   ├── App Screens (9 screens)
│   └── App Store Screenshots (10 screens)
│
└── MemeCraftVibe
    ├── Onboarding (3 screens)
    ├── App Screens (7 screens)
    └── App Store Screenshots (10 screens)
```

---

## 1. TaskFlow v3 Screens

### Onboarding Flow (4 Screens)

#### Screen 1: Welcome

```
┌─────────────────────────────────────┐
│                                     │
│          [LOGO: Checkmark]          │
│                                     │
│       TaskFlow                       │
│   Celebrate Your Wins                │
│                                     │
│   [Illustration: Person celebrating]  │
│                                     │
│  The task app that makes            │
│  completing tasks feel good          │
│                                     │
│         [Get Started →]              │
│                                     │
└─────────────────────────────────────┘
```

**Specs:**
- Background: True black (#000000)
- Logo: 80px, gradient fill
- Title: Display 48px, bold
- Subtitle: Body 20px, secondary color
- Illustration: 200px tall
- Button: Primary, full width
- Status bar: Hidden

---

#### Screen 2: Value Proposition

```
┌─────────────────────────────────────┐
│                                     │
│   [Illustration: AI Focus]           │
│                                     │
│   AI picks what matters              │
│                                     │
│   Stop wondering what to do.         │
│   Our AI analyzes your tasks          │
│   and selects your daily focus.       │
│                                     │
│         [Continue →]                │
│                                     │
└─────────────────────────────────────┘
```

**Specs:**
- Illustration: AI character with sparkles
- Title: Display 32px, centered
- Description: Body 16px, 3 lines max
- Button: Primary
- Back button: Top left, ghost

---

#### Screen 3: First Task

```
┌─────────────────────────────────────┐
│                                     │
│   [Task Input Box]                   │
│                                     │
│   "Call mom tomorrow 3pm"           │
│                                     │
│   ↓                                 │
│   [Parsing Preview]                  │
│   ✓ Due: Tomorrow 3pm                │
│   ✓ Priority: Normal                │
│                                     │
│         [Add Task →]                 │
│                                     │
└─────────────────────────────────────┘
```

**Specs:**
- Input: Auto-focus on mount
- Parsing preview: Animated appearance
- Button: Primary, disabled until valid
- Hint: "Try saying: Meeting with team tomorrow at 2pm"

---

#### Screen 4: Celebration

```
┌─────────────────────────────────────┐
│                                     │
│         🎉 CONFETTI 🎉              │
│                                     │
│   [Illustration: Happy character]     │
│                                     │
│   Your first win!                    │
│   You're awesome!                    │
│                                     │
│         [Start Crushing →]           │
│                                     │
└─────────────────────────────────────┘
```

**Specs:**
- Confetti: Full screen burst (2 seconds)
- Illustration: Character with arms raised
- Message: Personalized "Your first win!"
- Button: Primary
- Background: Celebration gradient overlay

---

### App Screens

#### Dashboard (Empty State)

```
┌─────────────────────────────────────┐
│  ← TaskFlow              + ⚙️        │
│                                     │
│  ┌─────────────────────────────┐   │
│  │                             │   │
│  │      [Empty State Art]       │   │
│  │                             │   │
│  │   Your tasks will appear    │   │
│  │   when you add them.         │   │
│  │                             │   │
│  │   [+ Add your first task]    │   │
│  │                             │   │
│  └─────────────────────────────┘   │
│                                     │
│  🔥 0 day streak                    │
└─────────────────────────────────────┘
```

**Specs:**
- Empty state art: Friendly character or illustration
- CTA button: Primary style
- Streak counter: Bottom center
- Navigation: Bottom tab bar (hidden on this screen)

---

#### Dashboard (Populated)

```
┌─────────────────────────────────────┐
│  ← TaskFlow              🔍 ⚙️        │
│                                     │
│  Good morning, Alex! 👋              │
│                                     │
│  Today's Focus (3 tasks)             │
│  ┌─────────────────────────────┐   │
│  │ ◉ Call mom                   │   │
│  │    📅 3:00 PM                 │   │
│  │    🏷️ Family                  │   │
│  ├─────────────────────────────┤   │
│  │ ○ Review project proposal    │   │
│  │    📅 5:00 PM                 │   │
│  │    🏷️ Work                    │   │
│  ├─────────────────────────────┤   │
│  │ ○ Plan weekend trip           │   │
│  │    📅 Saturday                │   │
│  │    🏷️ Personal                │   │
│  └─────────────────────────────┘   │
│                                     │
│  [View All Tasks]                    │
│                                     │
│  🔥 3 day streak                    │
└─────────────────────────────────────┘
```

**Specs:**
- Greeting: Personalized, time-aware
- Focus cards: Drag-reorderable
- Completion checkbox: Triggers celebration
- Streak fire: Animated when >3 days

---

#### Kanban Board

```
┌─────────────────────────────────────┐
│  ← ← Kanban           [+ New Task]    │
│                                     │
│  ┌──────────┬──────────┬──────────┐ │
│  │  Today   │Upcoming │ Someday  │ │
│  ├──────────┼──────────┼──────────┤ │
│  │ ◉ Task 1 │ ○ Task 3 │ ○ Task 5 │ │
│  │ ◉ Task 2 │ ○ Task 4 │          │ │
│  └──────────┴──────────┴──────────┘ │
│                                     │
│  Drag tasks to organize your day     │
└─────────────────────────────────────┘
```

**Specs:**
- Columns: 3 (Today, Upcoming, Someday)
- Cards: Drag-reorderable with lift effect
- Drop zones: Highlight on drag over
- Quick add: Opens new task modal

---

#### Task Detail

```
┌─────────────────────────────────────┐
│  ← ← Task              ⋮ More          │
│                                     │
│  ◉ Call mom                         │
│  📅 Tomorrow, 3:00 PM                 │
│  🏷️ Family                           │
│                                     │
│  Description                          │
│  Discuss holiday plans               │
│                                     │
│  Subtasks                             │
│  ☑ Confirm time                     │
│  ☐ Buy gift                          │
│  [+ Add subtask]                     │
│                                     │
│  [AI Focus] [Complete ✓]            │
└─────────────────────────────────────┘
```

**Specs:**
- Complete button: Triggers celebration
- AI Focus: Highlights important tasks
- Subtasks: Checkboxes with strikethrough
- More menu: Delete, snooze, move options

---

#### Settings

```
┌─────────────────────────────────────┐
│  ← Settings                          │
│                                     │
│  👤 Alex Johnson                     │
│  alex@email.com                      │
│  [Edit Profile →]                    │
│                                     │
│  ┌─────────────────────────────┐   │
│  │ Appearance                     │   │
│  │ ◉ Dark Mode                    │   │
│  │ ○ Light Mode                   │   │
│  │ ○ System                       │   │
│  └─────────────────────────────┘   │
│                                     │
│  ┌─────────────────────────────┐   │
│  │ Notifications                  │   │
│  │ ☑ Task reminders              │   │
│  │ ☑ Streak alerts                │   │
│  │ ☑ Celebration sounds          │   │
│  └─────────────────────────────┘   │
│                                     │
│  ┌─────────────────────────────┐   │
│  │ ⭐ Upgrade to Pro              │   │
│  │ Unlock unlimited tasks         │   │
│  └─────────────────────────────┘   │
│                                     │
│  [Sign Out]                         │
└─────────────────────────────────────┘
```

---

#### Analytics Dashboard

```
┌─────────────────────────────────────┐
│  ← Analytics                        │
│                                     │
│  This Week                          │
│  ┌─────────────────────────────┐   │
│  │   Tasks Completed             │   │
│  │        42                      │   │
│  │   ▁▃▃▃▄▄▅▅▅▅▆▆▆▇▇████        │   │
│  │   ↑ 12% from last week        │   │
│  └─────────────────────────────┘   │
│                                     │
│  Streak History                      │
│  ┌─────────────────────────────┐   │
│  │   7   14  21  28              │   │
│  │   🏆  🏆  🏆  🏆               │   │
│  └─────────────────────────────┘   │
│                                     │
│  Achievements                        │
│  [🏆] [⚔️] [🎯] [🌟]               │
│                                     │
└─────────────────────────────────────┘
```

---

### App Store Screenshots (10 screens)

| # | Screen | Caption | Text Overlay |
|---|-------|--------|--------------|
| 1 | Dashboard with celebration | Celebrate your wins | Bottom |
| 2 | Natural language input parsing | Just type it out | Bottom |
| 3 | Kanban board drag-drop | See your progress | Bottom |
| 4 | AI Daily Focus selection | Know what matters | Bottom |
| 5 | Celebration animation | Done never felt so good | Bottom |
| 6 | Analytics dashboard | Track your streaks | Bottom |
| 7 | Goals tracking | Reach your goals | Bottom |
| 8 | Pomodoro timer | Focus for 25 minutes | Bottom |
| 9 | Dark mode | Beautiful in any theme | Bottom |
| 10 | Empty state with CTA | Start celebrating today | Bottom |

---

## 2. TeenPopTastic (Vibe) Screens

### Onboarding (3 screens)

#### Screen 1: Music Preferences

```
┌─────────────────────────────────────┐
│                                     │
│          [MUSIC LOGOS]               │
│                                     │
│       Connect your music            │
│                                     │
│   Choose your music platform        │
│   to find your vibe tribe.           │
│                                     │
│  ┌──────────┐  ┌──────────┐          │
│  │ Spotify  │  │Apple Music│          │
│  └──────────┘  └──────────┘          │
│                                     │
│         [Continue →]                │
│                                     │
└─────────────────────────────────────┘
```

#### Screen 2: Permission

```
┌─────────────────────────────────────┐
│                                     │
│   [Illustration: Music connection]    │
│                                     │
│   We access your music to           │
│   find people with your taste.       │
│                                     │
│   • We never share your data        │
│   • You control what we see         │
│   • Disconnect anytime               │
│                                     │
│         [Allow →]                   │
│                                     │
└─────────────────────────────────────┘
```

#### Screen 3: Create Profile

```
┌─────────────────────────────────────┐
│                                     │
│   Create your music identity        │
│                                     │
│   [Avatar Upload Circle]             │
│   @vibeguru                          │
│                                     │
│   Display Name                        │
│   [_________________________]         │
│                                     │
│   Bio (optional)                     │
│   [_________________________]         │
│                                     │
│         [Create Profile →]           │
│                                     │
└─────────────────────────────────────┘
```

---

### App Screens

#### Vibe Matching

```
┌─────────────────────────────────────┐
│  ← Vibe           [Filter]            │
│                                     │
│  Match: 85%                          │
│                                     │
│  ┌─────────────────────────────┐   │
│  │                             │   │
│  │   [Avatar: Music Profile]    │   │
│  │                             │   │
│  │   MusicLover92                │   │
│  │   🎵 Top 3: Taylor, Drake    │   │
│  │   🎵 Genres: Pop, Hip-hop    │   │
│  │                             │   │
│  │   ⚡ 85% match with you    │   │
│  │                             │   │
│  └─────────────────────────────┘   │
│                                     │
│    [⟵ Pass]  [🌊 Wave]               │
└─────────────────────────────────────┘
```

#### Profile Card

```
┌─────────────────────────────────────┐
│                                     │
│         ┌─────────┐                 │
│         │ 🎵🎵🎵 │  Music Lover      │
│         └─────────┘                 │
│                                     │
│  Vibe Personality                    │
│  🎵 "Party Starter Mix"             │
│                                     │
│  Top Artists                         │
│  🎤 Taylor Swift                    │
│  🎤 Drake                          │
│  🎤 The Weeknd                      │
│                                     │
│  Top Genres                          │
│  Pop 40%  Hip-hop 35%  R&B 25%       │
│                                     │
│  [Share Profile]                     │
│                                     │
└─────────────────────────────────────┘
```

---

### App Store Screenshots (10 screens)

| # | Screen | Caption |
|---|-------|--------|
| 1 | Music profile reveal | Your music is your vibe |
| 2 | Vibe matching interface | Find friends through music |
| 3 | Mutual match celebration | Someone gets your music |
| 4 | Music moment with song | Share your mood with music |
| 5 | Group vibe interface | Music connects us all |
| 6 | Daily vibe check | What's your vibe right now? |
| 7 | Music discovery | Find new music through friends |
| 8 | Safety features | Stay safe while vibing |
| 9 | Chat with music | Share music, not just text |
| 10 | Settings/profile | Make it your vibe |

---

## 3. MemeCraftVibe Screens

### App Screens

#### Template Gallery

```
┌─────────────────────────────────────┐
│  ← Gallery      [🔥 Trending]        │
│                                     │
│  🔍 [Search templates...]           │
│                                     │
│  ┌────┐ ┌────┐ ┌────┐ ┌────┐       │
│  │ 📷 │ │ 🎭 │ │ 😂 │ │ 💀 │       │
│  │Drake│ │Dist│ │Guy│ │Bruh│       │
│  │    │ │rguy│ │Flin│ │    │       │
│  └────┘ └────┘ └────┘ └────┘       │
│  #1   #2   #3   #4               │
│                                     │
│  [Load More...]                     │
└─────────────────────────────────────┘
```

#### Editor

```
┌─────────────────────────────────────┐
│  ← ←              [Generate →]     │
│                                     │
│  ┌─────────────────────────────┐   │
│  │                             │   │
│  │     [Template Preview]      │   │
│  │                             │   │
│  │     "When you realize..."    │   │
│  │                             │   │
│  └─────────────────────────────┘   │
│                                     │
│  Your idea:                          │
│  [When you realize it's...]        │
│                                     │
│  AI Suggestions:                      │
│  ✓ Confused Travolta                │
│  ✓ Drake Hotline Bling              │
│  ✓ Distracted Boyfriend            │
│                                     │
│  [Font:] [Size:] [Color:]           │
│                                     │
└─────────────────────────────────────┘
```

---

### App Store Screenshots (10 screens)

| # | Screen | Caption |
|---|-------|--------|
| 1 | Template gallery with trending | Always fresh with viral memes |
| 2 | AI text input with suggestions | Turn ideas into memes in seconds |
| 3 | Generated meme result | AI memes that actually get laughs |
| 4 | Share sheet | Share everywhere in one tap |
| 5 | Saved/favorites grid | Your personal meme library |
| 6 | Text search interface | Find the perfect template |
| 7 | Editor interface | Make it yours |
| 8 | Trending templates | What's actually viral right now |
| 9 | Onboarding | Start creating in seconds |
| 10 | Premium features | Unlimited memes + exclusive features |

---

## Figma Best Practices

### Naming Conventions

```
Pages: Page / {Screen Name}
Frames: {Screen Name} - {Variant}
Components: Component / {Name}
Text: Body / {Size} / {Weight}
Colors: / Colors / {Category}
Effects: / Effects / {Name}
```

### Layers

```
📁 TaskFlow v3
  📁 Pages
    📄 Dashboard - Empty
    📄 Dashboard - Populated
    📄 Kanban Board
  📁 Components
    📄 Task Card
    📄 Button Primary
    📄 Confetti
```

### Components

Create master components for:
- Buttons (all variants)
- Inputs (all types)
- Cards (task, profile, etc.)
- Navigation bars
- Status bars
- Device frames

---

## Export Settings

### For Development Handoff

| Format | Settings |
|--------|----------|
| Screenshots | PNG @2x, transparent background |
| Icons | SVG |
| Assets | Export as @2x |
| Redlines | Include for spacing reference |

### For App Store

| Device | Size | Format |
|--------|------|--------|
| iPhone 15 Pro Max | 1290×2796 | PNG |
| iPad 13" | 2048×2732 | PNG |

---

## Implementation Checklist

For each screen:

- [ ] Frame created at correct resolution
- [ ] Design tokens applied
- [ ] All text layers use typography tokens
- [ ] Components used (not re-creating)
- [ ] Dark mode variant (if applicable)
- [ ] Loading state designed
- [ ] Empty state designed
- [ ] Error state designed
- [ ] Success state designed
- [ ] Named convention followed
- [ ] Export-ready

---

## Next Steps

1. **Create Figma file** using SOLO Emotional Design System
2. **Build screens** following these specifications
3. **Create components** from component library
4. **Design tokens** imported as styles
5. **Test on devices** using Figma Mirror
6. **Export** for development handoff
7. **Create screenshots** using screenshot templates

---

*Part of the SOLO Design System*
*For use with TRACK 5: Design System & UI Pre-Build*
