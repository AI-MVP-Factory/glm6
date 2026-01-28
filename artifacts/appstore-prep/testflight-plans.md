# TestFlight Plans
**Created:** 2026-01-28
**Purpose:** Beta testing infrastructure for all 3 apps

---

## Universal TestFlight Strategy

### Testing Philosophy

**Quality Over Quantity:** 100 engaged testers > 10,000 passive testers

**Target Tester Profile:**
- Early adopters who provide feedback
- Representative of target audience
- Willing to tolerate bugs
- Available for follow-up questions

---

## 1. TaskFlow v3 TestFlight Plan

### Phase 1: Internal Testing (Week 1-2)

**Duration:** 1-2 weeks
**Tester Count:** 5-10

**Target Testers:**
- Team members
- Friends/family
- Fellow founders/power users
- Productivity enthusiasts

**Focus:**
- Critical bugs (crashes, data loss)
- Core functionality (task CRUD, sync)
- AI Daily Focus accuracy
- Celebration animations (emotional response)

**Distribution:**
- Direct email invitation
- 1-on-1 onboarding walkthrough
- Slack/Discord for quick feedback

**Success Criteria:**
- No crashes in 48 hours
- All 15 features functional
- At least 50% of testers use daily

---

### Phase 2: External Beta (Week 3-6)

**Duration:** 3-4 weeks
**Tester Count:** 50-100 (then scale to 1,000+)

**Target Testers:**
- Productivity app enthusiasts
- Todoist/Things 3 users looking for alternatives
- Reddit r/productivity members
- Twitter productivity community

**Recruitment:**
- Reddit: r/productivity, r/todoist
- Twitter: Productivity Twitter threads
- Product Hunt: "Seeking beta testers"
- Waitlist email blast

**Focus:**
- UX and flows
- Edge cases
- Performance on older devices
- Feature requests
- Emotional response to celebrations

**Builds:**
- Frequency: Weekly
- Numbering: 1.0.0-beta.1, 1.0.0-beta.2, etc.
- What's New: Brief summary of changes

---

### TaskFlow Test Case Checklist

| Feature | Test Case | Expected Result |
|---------|-----------|-----------------|
| **Sign Up** | Create account with email | Account created, logged in |
| **Task CRUD** | Create, edit, delete task | All operations sync correctly |
| **NL Input** | Type "Call mom tomorrow 3pm !!" | Task created with correct date/time |
| **Kanban** | Drag task from Todo → Done | Task moves, celebrates |
| **AI Focus** | Request daily focus | 3-5 tasks returned with reasoning |
| **Pomodoro** | Start 25-min timer | Timer counts down, plays sound |
| **Celebration** | Complete 3 tasks in a row | Streak celebration triggers |
| **Goals** | Create goal, link tasks | Goal progress updates |
| **Analytics** | View analytics dashboard | Charts display correctly |
| **Dependencies** | Create blocked task | Visual indicator shows |
| **Recurring** | Create daily recurring task | New task appears next day |
| **Templates** | Create task template | Template available for reuse |
| **Time Tracking** | Start timer on task | Elapsed time tracks |
| **Keyboard Nav** | Press j/k to navigate | Selection moves correctly |
| **Dark Mode** | Toggle dark mode | Theme switches instantly |
| **Offline** | Create task offline | Syncs when online |

**Edge Cases to Test:**
- Very long task names
- Many tasks in one day (100+)
- Rapid-fire task creation
- Network interruption during sync
- Multiple devices logged in simultaneously

---

### Feedback Collection

**In-App:**
- Feedback button in settings
- Bug report form with screenshots
- "Report a problem" on each screen

**External:**
- Discord server for real-time chat
- Weekly feedback survey (Typeform)
- 1-on-1 interviews with power users

**Response Time:**
- Critical bugs: Within 4 hours
- Feature requests: Within 24 hours
| General feedback: Within 48 hours

---

### Release Notes Template

```markdown
### TaskFlow v1.0.0-beta.X (Date)

**What's New:**
- Feature: [Brief description]
- Improvement: [What got better]
- Bug fix: [What broke and is now fixed]

**Known Issues:**
- [List any non-critical issues]

**Testers:**
- Thank you to @user1, @user2 for the bug reports!

**Focus This Week:**
- Please test [feature X] - we need feedback on [specific aspect]

**How to Report:**
- Join Discord: [link]
- Email: support@taskflow.app
```

---

## 2. TeenPopTastic TestFlight Plan

### Phase 1: Internal Testing (Week 1-2)

**Duration:** 2 weeks (longer due to safety)
**Tester Count:** 5-10

**Target Testers:**
- Team members
- Trusted Gen Z friends/family
- Parents of teens (for parent features)
- Safety consultants (if available)

**Focus:**
- Safety features (blocking, reporting, moderation)
- Age verification flow
- Music integration (Spotify/Apple Music)
- Vibe matching algorithm
- COPPA compliance

**Distribution:**
- Direct invitation only
- Parent consent for under-18 testers
- Signed beta tester agreement

**Success Criteria:**
- Zero safety incidents
- Age gate working correctly
- Music integrations functional
- Parent tools functional

---

### Phase 2: External Beta (Week 3-6)

**Duration:** 4 weeks
**Tester Count:** Start with 100, scale to 1,000

**Target Testers:**
- High school/college students
- Gen Z music enthusiasts
- Spotify power users
- BeReal/Locket users

**Recruitment:**
- TikTok: "Join Vibe beta" creator collabs
- Instagram Stories: Test call-to-action
- Reddit: r/teenagers (organic, not spam)
- Campus reps: 3-5 colleges to start

**Safety First:**
- Real-time moderation active
- Daily safety review
- Crisis response plan ready
- Parent email notifications for under-16

---

### TeenPopTastic Test Case Checklist

| Feature | Test Case | Expected Result |
|---------|-----------|-----------------|
| **Age Gate** | Enter age under 13 | Account rejected |
| **Parent Verify** | Sign up as age 14 | Parent email sent |
| **Spotify Connect** | Authorize Spotify | Top artists imported |
| **Music Profile** | View profile after import | Vibe DNA shown |
| **Vibe Match** | Find matches | Compatible users shown |
| **Vibe Wave** | Send wave to match | Match notified |
| **Mutual Match** | Both users wave | Match revealed |
| **Music Moment** | Share photo + song | Moment appears in feed |
| **Moment Reaction** | React to friend's moment | Reaction shown |
| **Vibe Check** | Respond to daily check | Check appears in feed |
| **Group Vibe** | Create crew | Crew created, playlist synced |
| **Crew Chat** | Send message in crew | Message delivered |
| **Block User** | Block a user | User blocked, no contact |
| **Report** | Report inappropriate content | Report submitted, auto-hidden |
| **Location** | Check location display | City-level only shown |
| **Parent Tools** | Parent requests access | Activity summary shown |

**Safety-Specific Tests:**
- Attempt sign-up as under-13 (should fail)
- Report abusive content (should auto-hide and notify)
- Block user (no further contact possible)
- Parent access request for under-16 (should work)
- Search for user by exact location (should not work)

---

### Feedback Collection

**In-App:**
- Safety-focused feedback flow
- "Report a safety issue" prominent
- Age-appropriate feedback prompts

**External:**
- Private Discord (age-gated)
- Weekly survey with anonymity option
- Parent feedback channel separate from teen channel

**Moderation:**
- 24-hour moderation coverage (or as close as possible)
- Escalation path for safety issues
- Law enforcement contact protocol ready

---

### Release Notes Template

```markdown
### Vibe v1.0.0-beta.X (Date)

**What's New:**
- Feature: [Brief description]
- Safety: [Any safety improvements]
- Bug fix: [What broke and is now fixed]

**Safety Updates:**
- [Any moderation/reporting improvements]

**Known Issues:**
- [List any non-critical issues]

**Testers:**
- Shoutout to [usernames] for the vibes! 🎵

**Focus This Week:**
- Please test [feature X] - does it match your vibe?

**Safety Reminder:**
- See something? Say something. Report in-app or email safety@joinvibe.app
```

---

## 3. MemeCraftVibe TestFlight Plan

### Phase 1: Internal Testing (Week 1)

**Duration:** 1 week
**Tester Count:** 5-10

**Target Testers:**
- Team members
- Friends who love memes
- Discord meme communities
- Content creators

**Focus:**
- AI template matching quality
- Generated meme quality
- Sharing functionality
- Template library freshness

**Distribution:**
- Direct invitation
- Meme community Discord servers

**Success Criteria:**
- AI match accuracy >75%
- Generated memes look good
- Sharing works on all platforms
- No crashes during generation

---

### Phase 2: External Beta (Week 2-4)

**Duration:** 3 weeks
**Tester Count:** 100-500, then scale to 10,000

**Target Testers:**
- Meme enthusiasts
- Content creators
- Social media managers
- Gen Z humor enjoyers

**Recruitment:**
- Reddit: r/memes, r/dankmemes (organic posts)
- Discord: Meme server partnerships
- TikTok: "Test our meme generator" creator collabs
- Twitter: Post memes, share link in comments

**Focus:**
- Meme quality and humor
- Template variety
- Virality of generated memes
- Feature requests
- Monetization feedback

**Gamification:**
- "Best meme of the week" contest
- Most shared meme gets featured
- Template naming contests

---

### MemeCraftVibe Test Case Checklist

| Feature | Test Case | Expected Result |
|---------|-----------|-----------------|
| **AI Generation** | Enter text idea | Appropriate templates suggested |
| **Template Selection** | Select suggested template | Meme generated with formatted text |
| **Text Search** | Search for template | Relevant templates found |
| **Customization** | Change font size/position | Changes apply correctly |
| **Save to Camera** | Save generated meme | Meme in photos at full resolution |
| **Share IG Story** | Share to Instagram | Opens Instagram with meme attached |
| **Share Twitter** | Share to Twitter | Opens Twitter composer with image |
| **Favorites** | Favorite a template | Template in favorites list |
| **History** | View generated memes | Previously generated memes shown |
| **Trending** | Browse trending templates | Current viral templates shown |
| **Onboarding** | Complete 3-screen intro | Understand app value |
| **Empty State** | First launch | Prompt to create first meme |
| **Offline** | Generate meme offline | Works, syncs when online |
| **Upload Image** | Use custom image | Works as template |

**Quality Tests:**
- Generate 10 memes, rate humor (subjective but helpful)
- Check text readability on various templates
- Test with very long captions
- Test with special characters/emojis
- Verify image quality after export

---

### Feedback Collection

**In-App:**
- "Rate this meme" after generation
- "Report this template" if inappropriate
- Feature request in settings

**External:**
- Discord server with meme sharing channels
- Weekly "best meme" contest
- Template suggestion form

**Metrics:**
- Meme generation rate
- Share rate by platform
- Template match acceptance rate
- Favorite templates

---

### Release Notes Template

```markdown
### MemeCraft v1.0.0-beta.X (Date)

**What's New:**
- Feature: [Brief description]
- New Templates: [Count] fresh templates added
- Bug fix: [What broke and is now fixed]

**Trending This Week:**
- [Showcase top 3 templates]

**Meme of the Week:**
- 🏆 @[username] with [description]

**Known Issues:**
- [List any non-critical issues]

**Focus This Week:**
- Please test [feature X] - make some memes and share them!

**Share Your Memes:**
- Tag us @[handle] for a chance to be featured!
```

---

## Universal Testing Best Practices

### Tester Communication

**Onboarding:**
- Welcome email with expectations
- How to provide feedback
- What to do if you find a bug
- Response time expectations

**Ongoing:**
- Weekly email updates
- Changelog in-app
- Tester shoutouts in release notes
- Feature sneak peeks

**Closing:**
- Thank you message
- App Store launch notification
- Special offer (free Pro month, etc.)

### Bug Reporting Format

```
**Bug Title:** [Brief description]

**Steps to Reproduce:**
1. [Action 1]
2. [Action 2]
3. [Action 3]

**Expected Result:** [What should happen]
**Actual Result:** [What actually happened]

**Device:** [iPhone 15 Pro Max, etc.]
**iOS Version:** [iOS 17.x]
**App Version:** [1.0.0-beta.X]

**Screenshots:** [If applicable]
**Logs:** [If available]
```

---

## Timeline Summary

| App | Internal Beta | External Beta | Total |
|-----|---------------|---------------|-------|
| TaskFlow v3 | 1-2 weeks | 3-4 weeks | 4-6 weeks |
| TeenPopTastic | 2 weeks | 4 weeks | 6 weeks |
| MemeCraftVibe | 1 week | 3 weeks | 4 weeks |

**Parallel Execution:** All three apps can be in beta simultaneously.

---

## TestFlight Setup Checklist

### For Each App:

- [ ] Create app record in App Store Connect
- [ ] Add builds from CI/CD (EAS/GitHub Actions)
- [ ] Configure test information (what to test)
- [ ] Set up beta groups (internal, external)
- [ ] Create feedback collection channels
- [ ] Prepare beta tester agreements
- [ ] Set up analytics for beta users
- [ ] Configure crash reporting
- [ ] Prepare onboarding materials
- [ ] Schedule weekly build cadence

---

*Last updated: 2026-01-28*
*Status: READY FOR EXECUTION*
