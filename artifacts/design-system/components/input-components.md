# Input Components
**Encouraging, Helpful, Clear**
**Created:** 2026-01-28

---

## Philosophy

**Inputs are conversations.** We're asking the user for information, make it feel good.

- **Friendly Placeholders:** "What's on your mind?" not "Enter text"
- **Helpful Errors:** "Let's fix this together" not "INVALID"
- **Smooth Focus:** Glow, expand, gentle transition
- **Validation Feedback:** Subtle, not aggressive

---

## 1. Text Input

### Design

```
┌─────────────────────────────────────┐
│ What's your task name?              │  ← Friendly placeholder
└─────────────────────────────────────┘
```

**Focus State:**

```
┌─────────────────────────────────────┐
│ Buy groceries for dinner            │  ← Glow border
└─────────────────────────────────────┘
   ↑ Helper text appears
```

**Error State:**

```
┌─────────────────────────────────────┐
│                                     │  ← Gentle red
└─────────────────────────────────────┘
   ⚠️ Task names need at least 2 characters
```

**Success State:**

```
┌─────────────────────────────────────┐
│ Buy groceries ✓                      │  ← Green checkmark
└─────────────────────────────────────┘
```

### CSS

```css
.input {
  width: 100%;
  padding: 10px 12px;
  background: var(--bg-surface);
  border: var(--border-subtle);
  border-radius: var(--radius-md);
  color: var(--text-primary);
  font-family: var(--font-body);
  font-size: var(--text-body-lg);
  transition: all 0.15s ease;
}

.input::placeholder {
  color: var(--text-tertiary);
}

.input:focus {
  outline: none;
  border: var(--border-focus);
  box-shadow: var(--glow-primary);
}

.input:focus + .helper-text {
  opacity: 1;
  transform: translateY(0);
}

/* Error state */
.input.error {
  border-color: var(--error);
  box-shadow: 0 0 0 1px var(--error);
}

.input.error + .helper-text {
  color: var(--error);
}

/* Success state */
.input.success {
  border-color: var(--success);
}

.input.success + .helper-text::before {
  content: '✓ ';
  color: var(--success);
}
```

---

## 2. Textarea

### Auto-Expand

```javascript
function autoResize(textarea) {
  textarea.style.height = 'auto';
  textarea.style.height = Math.min(textarea.scrollHeight, 200) + 'px';
}
```

### Character Count

```
┌─────────────────────────────────────┐
│ Write a description...             │
│                                     │
│                                     │
└─────────────────────────────────────┘
                    42/200  ← Encouraging, not limiting
```

### CSS

```css
.textarea {
  width: 100%;
  min-height: 80px;
  max-height: 200px;
  padding: 10px 12px;
  background: var(--bg-surface);
  border: var(--border-subtle);
  border-radius: var(--radius-md);
  color: var(--text-primary);
  font-family: var(--font-body);
  font-size: var(--text-body-lg);
  resize: none;
  transition: all 0.15s ease;
}

.textarea:focus {
  outline: none;
  border: var(--border-focus);
  box-shadow: var(--glow-primary);
}

.char-count {
  text-align: right;
  font-size: var(--text-body-sm);
  color: var(--text-tertiary);
  margin-top: 4px;
}

.char-count.near-limit {
  color: var(--warning);
}

.char-count.at-limit {
  color: var(--error);
}
```

---

## 3. Select / Dropdown

### Custom Styling

```
┌─────────────────────────────────────┐
│ Choose a category ▼                │  ← Custom arrow
└─────────────────────────────────────┘
   ↓ Open
┌─────────────────────────────────────┐
│ 🔍 Search categories...            │  ← Search/filter
├─────────────────────────────────────┤
│ ★ Work                              │
│   Personal                          │
│   Shopping                          │
└─────────────────────────────────────┘
```

### CSS

```css
.select-wrapper {
  position: relative;
}

.select {
  width: 100%;
  padding: 10px 32px 10px 12px;
  background: var(--bg-surface);
  border: var(--border-subtle);
  border-radius: var(--radius-md);
  color: var(--text-primary);
  font-family: var(--font-body);
  font-size: var(--text-body-lg);
  cursor: pointer;
  appearance: none;
  transition: all 0.15s ease;
}

.select:focus {
  outline: none;
  border: var(--border-focus);
  box-shadow: var(--glow-primary);
}

.select-wrapper::after {
  content: '▼';
  position: absolute;
  right: 12px;
  top: 50%;
  transform: translateY(-50%);
  font-size: 10px;
  color: var(--text-tertiary);
  pointer-events: none;
}

/* Dropdown menu */
.dropdown-menu {
  position: absolute;
  top: calc(100% + 4px);
  left: 0;
  right: 0;
  background: var(--bg-elevated);
  border: var(--border-default);
  border-radius: var(--radius-md);
  box-shadow: var(--elevation-4);
  z-index: 100;
  max-height: 200px;
  overflow-y: auto;
}

.dropdown-search {
  padding: 8px;
  border-bottom: var(--border-subtle);
}

.dropdown-item {
  padding: 8px 12px;
  cursor: pointer;
  transition: background 0.1s ease;
}

.dropdown-item:hover {
  background: rgba(255, 255, 255, 0.05);
}

.dropdown-item.selected {
  background: rgba(168, 85, 247, 0.1);
}
```

---

## 4. Checkbox

### Custom Styling

```
☑️ Remember me        ← Checked state
☐ Send notifications  ← Unchecked
```

### CSS

```css
.checkbox-wrapper {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  cursor: pointer;
}

.checkbox-input {
  appearance: none;
  width: 20px;
  height: 20px;
  border: 2px solid var(--text-tertiary);
  border-radius: 4px;
  cursor: pointer;
  position: relative;
  transition: all 0.15s ease;
}

.checkbox-input:hover {
  border-color: var(--taskflow-primary);
}

.checkbox-input:checked {
  background: var(--taskflow-primary);
  border-color: var(--taskflow-primary);
}

.checkbox-input:checked::after {
  content: '✓';
  position: absolute;
  color: white;
  font-size: 14px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.checkbox-input:focus {
  outline: none;
  box-shadow: 0 0 0 2px var(--glow-primary);
}
```

---

## 5. Radio / Toggle

```
○ Daily reminder    ← Unselected
● Push enabled      ← Selected
○ Email summary
```

### CSS

```css
.radio-wrapper {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  cursor: pointer;
}

.radio-input {
  appearance: none;
  width: 20px;
  height: 20px;
  border: 2px solid var(--text-tertiary);
  border-radius: 50%;
  cursor: pointer;
  position: relative;
  transition: all 0.15s ease;
}

.radio-input:hover {
  border-color: var(--taskflow-primary);
}

.radio-input:checked {
  border-color: var(--taskflow-primary);
}

.radio-input:checked::after {
  content: '';
  position: absolute;
  width: 10px;
  height: 10px;
  background: var(--taskflow-primary);
  border-radius: 50%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

---

## 6. Switch

### Toggle Design

```
○────────○  ← Off
●────────○  ← On
```

### CSS

```css
.switch {
  position: relative;
  width: 44px;
  height: 24px;
  background: var(--bg-card);
  border: var(--border-subtle);
  border-radius: 12px;
  cursor: pointer;
  transition: all 0.2s ease;
}

.switch::after {
  content: '';
  position: absolute;
  width: 20px;
  height: 20px;
  background: var(--text-tertiary);
  border-radius: 50%;
  top: 1px;
  left: 1px;
  transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
}

.switch.active {
  background: var(--taskflow-primary);
  border-color: var(--taskflow-primary);
}

.switch.active::after {
  background: white;
  left: 22px;
}

.switch:hover::after {
  transform: scale(1.05);
}
```

---

## 7. Search Input

### With Clear Button

```
┌─────────────────────────────────────┐
│ 🔍 Search tasks...          ✕     │  ← Clear on type
└─────────────────────────────────────┘
```

### CSS

```css
.search-wrapper {
  position: relative;
}

.search-input {
  width: 100%;
  padding: 10px 12px 10px 36px;
  background: var(--bg-surface);
  border: var(--border-subtle);
  border-radius: var(--radius-md);
  color: var(--text-primary);
  font-family: var(--font-body);
  font-size: var(--text-body-lg);
}

.search-icon {
  position: absolute;
  left: 10px;
  top: 50%;
  transform: translateY(-50%);
  color: var(--text-tertiary);
  pointer-events: none;
}

.search-clear {
  position: absolute;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  color: var(--text-tertiary);
  cursor: pointer;
  padding: 4px;
  opacity: 0;
  pointer-events: none;
  transition: all 0.15s ease;
}

.search-wrapper:not(:empty) .search-clear {
  opacity: 1;
  pointer-events: auto;
}
```

---

## 8. Date/Time Picker

### iOS Style (Native)

```javascript
// Use native pickers for best experience
<input type="date" class="input" />
<input type="time" class="input" />
```

### CSS Override

```css
input[type="date"],
input[type="time"] {
  appearance: none;
  -webkit-appearance: none;
  background: var(--bg-surface);
  border: var(--border-subtle);
  border-radius: var(--radius-md);
  padding: 10px 12px;
  color: var(--text-primary);
  font-family: var(--font-body);
}

/* Dark mode calendar icon */
input[type="date"]::-webkit-calendar-picker-indicator {
  filter: invert(1);
}
```

---

## Helper Text & Labels

### Structure

```
Task Name
┌─────────────────────────────────────┐
│ Buy groceries                       │
└─────────────────────────────────────┘
   What do you need to accomplish?  ← Helper text
```

### CSS

```css
.input-group {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.input-label {
  font-size: var(--text-body-sm);
  font-weight: var(--font-medium);
  color: var(--text-secondary);
}

.input-helper {
  font-size: var(--text-body-sm);
  color: var(--text-tertiary);
  min-height: 16px;
  transition: all 0.15s ease;
}
```

---

## Error Messages

### Friendly Copy

| Error Type | Friendly Message | Technical Message |
|------------|------------------|------------------|
| Required | "This field is required" | "Field is required" |
| Too short | "Let's add a bit more detail" | "Must be at least X characters" |
| Invalid email | "Hmm, that doesn't look like an email" | "Invalid email format" |
| Mismatch | "These don't match" | "Passwords do not match" |
| Taken | "This is already taken, try another?" | "Already exists" |

---

## Validation Timing

| Strategy | When | Feel |
|----------|------|------|
| On blur | After leaving field | Non-intrusive |
| On type (debounced) | After 500ms pause | Helpful feedback |
| On submit | Before form submit | Catch-all |

---

## TypeScript Interfaces

```typescript
interface InputProps {
  type?: 'text' | 'email' | 'password' | 'search' | 'number';
  placeholder?: string;
  label?: string;
  helper?: string;
  error?: string;
  success?: boolean;
  disabled?: boolean;
  value?: string;
  onChange?: (value: string) => void;
  onFocus?: () => void;
  onBlur?: () => void;
  maxLength?: number;
  showCharCount?: boolean;
  autoFocus?: boolean;
}
```

---

## Best Practices

### DO:
- Use friendly placeholder text
- Provide helpful error messages
- Show validation state clearly
- Use appropriate input type (email, number, etc.)
- Support keyboard navigation
- Show loading state for async validation

### DON'T:
- Use "Enter text" as placeholder
- Show errors while user is still typing
- Clear input on error (let user fix)
- Disable form without explanation
- Use placeholder as label (accessibility)

---

## Accessibility

- **Labels:** Every input has a visible or hidden label
- **ARIA:** ARIA attributes for validation state
- **Focus:** Visible focus ring
- **Errors:** Associated with input via `aria-describedby`
- **Required:** Mark required fields clearly

```html
<div class="input-group">
  <label for="task-name" class="input-label">Task Name</label>
  <input
    id="task-name"
    type="text"
    aria-describedby="task-name-helper"
    aria-invalid="false"
    required
  />
  <span id="task-name-helper" class="input-helper">
    What do you need to accomplish?
  </span>
</div>
```

---

*Part of the SOLO Emotional Component Library*
