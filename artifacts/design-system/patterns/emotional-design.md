# Emotional Design Patterns
**How Products Should Make Users FEEL**
**Created:** 2026-01-28

---

## Core Thesis

> **"Products succeed by how they make users FEEL. Not features, but emotions."**

Every interaction in our products should evoke a specific emotional response. This document provides patterns for creating those feelings.

---

## 1. Warmth Patterns

**Goal:** Make users feel welcome and valued

### Greeting

```
❌ "Welcome back"
✅ "Hey [Name]! Good to see you again"
✅ "Welcome back! Ready to crush some tasks?"
```

### Empty States

```
❌ "No tasks yet"
✅ "Your first win awaits! Let's get started."
✅ "Empty canvas, infinite possibilities. Create your first task."
```

### Errors

```
❌ "Invalid input"
✅ "Oops! Let's fix this together."
✅ "Hmm, that didn't work. Let's try something else."
```

### Success

```
❌ "Complete"
✅ "You crushed it!"
✅ "Another win for you! Great job."
```

### Copy Voice

```
❌ "Please enter your email address"
✅ "What's your email? We'll only send good stuff."
✅ "Where should we send your wins?"
```

---

## 2. Empathy Patterns

**Goal:** Understand and validate user feelings

### First Run

```
❌ "Create account"
✅ "Let's get you set up. This only takes a minute."
✅ "Starting something new is exciting. Let's do this together!"
```

### Returning User

```
❌ "Login"
✅ "Welcome back! Pick up where you left off."
✅ "Hey [Name]! Ready to continue your streak?"
```

### After Break

```
❌ "You missed 3 days"
✅ "No worries! Life happens. Let's get back on track."
✅ "Three days off, no problem. Your streak is waiting when you're ready."
```

### Struggling

```
❌ "You're behind schedule"
✅ "Having a tough day? That's okay. Let's focus on just one thing."
✅ "We all have those days. What's ONE thing you can do today?"
```

### Celebrating Effort

```
❌ "Good job"
✅ "You showed up today. That matters."
✅ "Progress over perfection. You're doing great!"
```

---

## 3. Celebration Patterns

**Goal:** Make achievements feel meaningful

### First Win

```
Pattern: Maximum celebration
Animation: Full confetti burst + sound
Message: "🎉 YOUR FIRST WIN! You're amazing!"
Duration: 3 seconds (longer than usual)
Why: Sets the tone that achievements matter
```

### Milestone Recognition

```
Pattern: Tiered celebration based on difficulty
- 10 tasks: "Nice start!" (confetti)
- 50 tasks: "Halfway there!" (more confetti)
- 100 tasks: "Century club!" (full celebration)
- 1000 tasks: "LEGENDARY!" (epic celebration)
```

### Streak Celebration

```
Day 3: "3-day streak! Building momentum..." 💪
Day 7: "WEEK MASTER! 🔥 You're on fire!"
Day 14: "TWO WEEKS! 🏆 Consistency king!"
Day 30: "MONTHLY LEGEND! 👑 You're unstoppable!"
```

### Achievement Unlock

```
Visual: Badge reveal with glow
Animation: Staggered entrance
Sound: Achievement chime
Message: "ACHIEVEMENT UNLOCKED: [Name]!"
Action: Share button prominent
```

### Surprise Delight

```
Random: 5% chance of special celebration on task completion
Trigger: Normal action, extraordinary response
Message: "✨ EXTRAORDINARY WORK! ✨"
Effect: Creates anticipation
```

---

## 4. Validation Patterns

**Goal:** Make users feel understood and accepted

### Feelings Acknowledged

```
❌ "Stop complaining"
✅ "It's okay to feel overwhelmed. Let's break this down."
✅ "I hear you. This is a lot. Let's take it one step at a time."
```

### Progress Validated

```
❌ "50% complete"
✅ "Look how far you've come! Halfway there!"
✅ "You've made amazing progress. Keep it up!"
```

### Struggles Normalized

```
❌ "You're failing"
✅ "Everyone has days like this. Tomorrow is a fresh start."
✅ "Even the best have off days. You're not alone."
```

### Choices Affirmed

```
❌ "Confirm deletion"
✅ "Are you sure? We'll miss this task."
✅ "Delete this task? You can always create a new one."
```

### Mistakes Forgiven

```
❌ "Error occurred"
✅ "Oops! Something went wrong. Let's try again."
✅ "My bad! That's on me. Let's fix it."
```

---

## 5. Encouragement Patterns

**Goal:** Motivate action through positivity

### Starting

```
❌ "Begin"
✅ "You've got this!"
✅ "Let's do this! One task at a time."
✅ "Ready when you are. No pressure."
```

### In Progress

```
❌ "60% done"
✅ "Keep going! You're doing great."
✅ "More than halfway there! Push through!"
✅ "Amazing progress! Don't stop now!"
```

### Stuck Point

```
❌ "No progress"
✅ "Stuck? Let's break this down into smaller pieces."
✅ "Need a hand? Here's a suggestion to get moving."
```

### Almost There

```
❌ "90% complete"
✅ "SO CLOSE! One final push!"
✅ "This is it! Last stretch, you got this!"
```

### After Setback

```
❌ "Streak lost"
✅ "Streak over? Time to start a new one!"
✅ "Every streak starts with a single task. Begin again?"
✅ "The only real failure is not trying. Start fresh today!"
```

---

## 6. Anti-Patterns to Avoid

### Never Say These

| ❌ Anti-Pattern | ✅ Replacement |
|-----------------|----------------|
| "Invalid input" | "Let's fix this together" |
| "Error" | "Oops! Let's try again" |
| "Failed" | "Not this time, but next time!" |
| "You must" | "Ready when you are" |
| "Required" | "Recommended" |
| "Warning" | "Heads up!" |
| "Loading..." | "Getting things ready..." |
| "No results" | "Nothing here yet. Be the first!" |
| "Access denied" | "This needs a quick setup first" |

### Never Do These

| ❌ Action | Why | ✅ Alternative |
|-----------|------|-----------------|
| Block progress with celebration | Disrupts flow | Celebrate after action completes |
| Shame for inactivity | Creates guilt | Gentle encouragement |
| Hide important actions in menus | Frustrating | Make actions discoverable |
| Prevent "Undo" | Anxiety-inducing | Always offer undo |
| Force tutorial | Boring, skippable | Make tutorial fun, optional |
| Over-celebrate trivial actions | Diminishes impact | Reserve celebration for real wins |

---

## 7. Context-Aware Messaging

### Time of Day

```
Morning (5am-12pm):
  "Good morning! Let's make today count."
  "Rise and grind! What's your first win?"

Afternoon (12pm-5pm):
  "Good afternoon! How's your day going?"
  "Midday check-in! You're doing great."

Evening (5pm-10pm):
  "Good evening! Time to wrap up."
  "Evening vibes! Let's finish strong."

Night (10pm-5am):
  "Burning the midnight oil? That's dedication!"
  "Late night? Tomorrow you'll thank yourself for resting."
```

### Day of Week

```
Monday:
  "New week, new opportunities!"
  "Monday momentum! Let's start strong."

Friday:
  "Friyay! Finish strong and enjoy your weekend."
  "Almost there! Weekend is calling."

Sunday:
  "Sunday funday! Plan for an amazing week."
  "Rest up or prep for tomorrow—your choice."
```

### Seasonal

```
January:
  "New year, new you! Let's crush those goals."
  "Fresh start energy! What will you achieve?"

Summer:
  "Summer vibes! Keep the momentum going."
  "Sun's out, guns out! (Metaphorically) 🌞"

December:
  "End of year reflection! Look how far you've come."
  "Holiday season! Balance is everything."
```

---

## 8. Emotional State Matching

### When User Seems Frustrated

```
Signals: Rapid tapping, closing/reopening, abandoning tasks
Response: "Having a tough time? Let's simplify."
Action: Offer easier tasks, suggest break
```

### When User Is Flowing

```
Signals: Fast task completion, multiple actions
Response: Get out of the way!
Action: Minimize interruptions, celebrate silently
```

### When User Returns After Break

```
Signal: Not seen in 3+ days
Response: "Welcome back! We missed you."
Action: Highlight what's new, don't overwhelm
```

### When User Is New

```
Signal: First time using app
Response: Excitement, guidance, patience
Action: Friendly walkthrough, no walls
```

---

## 9. Copywriting Guidelines

### Voice Principles

1. **Be Human** - Write like you talk
2. **Be Positive** - Find the good in everything
3. **Be Brief** - Respect attention spans
4. **Be Clear** - Jargon confuses
5. **Be Honest** - Authenticity builds trust

### DO Write

```
✅ "Let's do this!"
✅ "You got this!"
✅ "Almost there!"
✅ "Nice work!"
✅ "One more thing..."
✅ "Here's what I'm thinking..."
✅ "Pro tip:" (not "Tip:")
✅ "Good news:" (not "Info:")
```

### DON'T Write

```
❌ "Please complete the following"
❌ "Error: Operation failed"
❌ "Loading data..."
❌ "Contact support"
❌ "End of list"
❌ "No items found"
❌ "Access denied"
❌ "Fatal error"
```

---

## 10. Implementation Checklist

When building features, ask:

- [ ] What should the user feel at each step?
- [ ] Does the copy reflect that emotion?
- [ ] Is there celebration for milestones?
- [ ] Are errors helpful, not blaming?
- [ ] Is empty state encouraging?
- [ ] Does loading state provide hope?
- [ ] Is success acknowledged?
- [ ] Is failure forgiven?
- [ ] Are users treated like friends?

---

## Quick Reference Card

| Feeling | Copy Pattern | Animation |
|---------|--------------|-----------|
| Welcome | "Hey [Name]!" | Wave |
| Celebrate | "You crushed it!" | Confetti |
| Encourage | "You've got this!" | Pulse |
| Forgive | "Tomorrow is fresh!" | Fade |
| Validate | "That's totally normal" | Nod |
| Excite | "Big things coming!" | Sparkle |

---

*Part of the SOLO Emotional Design System*
*Remember: Features are what the product DOES. Design is how it FEELS.*
