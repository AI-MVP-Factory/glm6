# App Privacy Details - Apple App Store
**Created:** 2026-01-28
**Purpose:** Map data collection for Apple's App Privacy Label

> Apple requires developers to disclose data collection in three categories:
> 1. Data Used to Track You
> 2. Data Linked to You
> 3. Data Not Linked to You

---

## Apple's Privacy Categories Reference

| Category | Description | Examples |
|----------|-------------|----------|
| **Contact Info** | Name, email, phone number | User profile, support |
| **User Content** | Content created by user | Tasks, memes, messages |
| **Identifiers** | User ID, device ID | User accounts, analytics |
| **Usage Data** | App interactions | Features used, session length |
| **Diagnostics** | Crash logs, performance | Bug tracking |
| **Location** | Approximate or precise | City-level for TeenPopTastic |
| **Financial Info** | Payment methods | Subscription data |
| **Health & Fitness** | Health data | N/A for our apps |
| **Sensitive Info** | Racial/ethnic, political | N/A for our apps |

---

## 1. TaskFlow v3 Privacy Details

### Data Used to Track You
**NONE** ✓

We do not track users across apps and websites.

---

### Data Linked to You

| Data Type | Purpose | Third Party Sharing? |
|-----------|---------|---------------------|
| **Contact Info** | Account creation, authentication | ❌ No (Supabase only) |
| - Email address | Login, password reset | Supabase Auth |
| - Display name | Profile display | Supabase Database |
| **User Content** | Core app functionality | ❌ No |
| - Task titles and descriptions | Task management | Supabase Database |
| - Categories and tags | Organization | Supabase Database |
| - Goals and notes | Goal tracking | Supabase Database |
| **Identifiers** | User identification | ❌ No |
| - User ID (UUID) | Account linking | Supabase Auth |
| - Device ID (optional) | Analytics | Mixpanel (anonymized) |
| **Usage Data** | Product improvement | ❌ No |
| - Features used | Analytics | Mixpanel (aggregated) |
| - Session duration | Analytics | Mixpanel (aggregated) |
| - Task completion rates | Product insights | Mixpanel (aggregated) |
| **Diagnostics** | Bug fixing | ❌ No |
| - Crash logs | Error tracking | Sentry |
| - Performance data | App optimization | Sentry |

---

### Data Not Linked to You

| Data Type | Purpose |
|-----------|---------|
| **Crash Data** | Anonymous crash reports |
| **Performance Data** | Anonymous app performance metrics |

---

### Third-Party SDK Data Collection

| SDK | Data Collected | Purpose | Link to User? |
|-----|----------------|---------|---------------|
| **Supabase** | Email, user ID, content | Backend, auth, database | Yes (required for app) |
| **Sentry** | Crash logs, breadcrumbs | Error tracking | No (anonymized) |
| **Mixpanel** | Events, session data | Analytics | No (aggregated) |
| **Paddle/Stripe** | Payment info (tokenized) | Subscriptions | Yes (PCI compliant) |
| **RevenueCat** | Subscription status | In-app purchases | Yes (minimal) |

---

### Apple App Privacy Label for TaskFlow v3

```
┌─────────────────────────────────────────────────────────┐
│  Data Linked to You                                     │
│  ✓ Contact Info                                         │
│  ✓ User Content                                         │
│  ✓ Identifiers                                          │
│  ✓ Usage Data                                           │
│  ✓ Diagnostics                                          │
├─────────────────────────────────────────────────────────┤
│  Data Not Linked to You                                 │
│  ✓ Diagnostics                                          │
├─────────────────────────────────────────────────────────┤
│  Data Used to Track You                                 │
│  None                                                   │
└─────────────────────────────────────────────────────────┘
```

---

## 2. TeenPopTastic Privacy Details

### Data Used to Track You
**NONE** ✓

We do not track users across apps and websites.

---

### Data Linked to You

| Data Type | Purpose | Third Party Sharing? |
|-----------|---------|---------------------|
| **Contact Info** | Account creation, safety | ❌ No |
| - Email address | Login, parent verification | Supabase Auth |
| - Display name | Profile display | Supabase Database |
| **User Content** | Core app functionality | ❌ No |
| - Music preferences | Music profile | Supabase Database |
| - Top artists/genres | Vibe matching | Supabase Database |
| - Music moments (photo/text) | Social sharing | Supabase Storage |
| - Group chat messages | Crew communication | Supabase Realtime |
| **Identifiers** | User identification | ❌ No |
| - User ID (UUID) | Account linking | Supabase Auth |
| - Spotify User ID | Music profile sync | Spotify API |
| - Apple Music User ID | Music profile sync | Apple Music API |
| **Usage Data** | Product improvement | ❌ No |
| - Features used | Analytics | Mixpanel (aggregated) |
| - Vibe match responses | Product insights | Mixpanel (aggregated) |
| - Session duration | Engagement metrics | Mixpanel (aggregated) |
| **Location** | Vibe matching | ❌ No (city-level only) |
| - City (approximate) | Find nearby users | Supabase Database |
| **Diagnostics** | Bug fixing | ❌ No |
| - Crash logs | Error tracking | Sentry |
| - Performance data | App optimization | Sentry |

---

### Data Not Linked to You

| Data Type | Purpose |
|-----------|---------|
| **Crash Data** | Anonymous crash reports |
| **Performance Data** | Anonymous app performance metrics |

---

### Third-Party SDK Data Collection

| SDK | Data Collected | Purpose | Link to User? |
|-----|----------------|---------|---------------|
| **Supabase** | Email, user ID, content | Backend, auth, database | Yes (required) |
| **Sentry** | Crash logs, breadcrumbs | Error tracking | No (anonymized) |
| **Mixpanel** | Events, session data | Analytics | No (aggregated) |
| **Spotify SDK** | Music profile data | Music integration | Yes (user grants access) |
| **Apple Music Kit** | Music profile data | Music integration | Yes (user grants access) |
| **Paddle/RevenueCat** | Subscription status | In-app purchases | Yes (minimal) |

---

### Important: Spotify/Apple Music Data

**What we collect from Spotify:**
- Top artists (name, ID, image)
- Top genres
- Recently played tracks

**What we DON'T collect:**
- Full listening history
- Playlist names
- Private playlists
- Payment data from Spotify

**User Control:**
- User can revoke access at any time
- Data is refreshed weekly (not real-time)
- Users can hide specific artists from profile

---

### Apple App Privacy Label for TeenPopTastic

```
┌─────────────────────────────────────────────────────────┐
│  Data Linked to You                                     │
│  ✓ Contact Info                                         │
│  ✓ User Content                                         │
│  ✓ Identifiers                                          │
│  ✓ Usage Data                                           │
│  ✓ Diagnostics                                          │
│  ✓ Location (approximate/city-level only)               │
├─────────────────────────────────────────────────────────┤
│  Data Not Linked to You                                 │
│  ✓ Diagnostics                                          │
├─────────────────────────────────────────────────────────┤
│  Data Used to Track You                                 │
│  None                                                   │
└─────────────────────────────────────────────────────────┘
```

---

## 3. MemeCraftVibe Privacy Details

### Data Used to Track You
**NONE** ✓

We do not track users across apps and websites.

---

### Data Linked to You

| Data Type | Purpose | Third Party Sharing? |
|-----------|---------|---------------------|
| **Contact Info** | Account creation (optional) | ❌ No |
| - Email address | Login, sync across devices | Supabase Auth (if logged in) |
| **User Content** | Core app functionality | ❌ No |
| - Meme captions/text | Meme generation | Supabase Database (if saved) |
| - Generated memes | User history, favorites | Supabase Storage (if saved) |
| - Template favorites | Quick access | Supabase Database (if logged in) |
| **Identifiers** | User identification | ❌ No |
| - User ID (UUID) | Account sync | Supabase Auth (if logged in) |
| - Device ID (optional) | Analytics | Mixpanel (anonymized) |
| **Usage Data** | Product improvement | ❌ No |
| - Templates used | Trending algorithm | Internal only |
| - Generation count | Feature usage | Mixpanel (aggregated) |
| - Sharing actions | Platform optimization | Mixpanel (aggregated) |
| **Diagnostics** | Bug fixing | ❌ No |
| - Crash logs | Error tracking | Sentry |
| - Performance data | App optimization | Sentry |

---

### Data Not Linked to You

| Data Type | Purpose |
|-----------|---------|
| **Crash Data** | Anonymous crash reports |
| **Performance Data** | Anonymous app performance metrics |
| **Usage Data** | Aggregated trending data |

---

### Third-Party SDK Data Collection

| SDK | Data Collected | Purpose | Link to User? |
|-----|----------------|---------|---------------|
| **Supabase** | Email, user ID, content | Backend, auth, storage | Yes (if logged in) |
| **Sentry** | Crash logs, breadcrumbs | Error tracking | No (anonymized) |
| **Mixpanel** | Events, session data | Analytics | No (aggregated) |
| **OpenAI API** | Meme captions (text only) | AI template matching | No (not linked to user) |
| **Paddle/RevenueCat** | Subscription status | In-app purchases | Yes (minimal) |

---

### Important: AI Data Handling

**What we send to AI (OpenAI):**
- Meme caption text only
- No user identifiers
- No personal information

**What we DON'T send:**
- User account information
- Generated meme images
- User preferences
- Any linked data

**AI Data Retention:**
- OpenAI does not train on API data
- Data is deleted after 30 days
- User can opt-out in settings

---

### Apple App Privacy Label for MemeCraftVibe

```
┌─────────────────────────────────────────────────────────┐
│  Data Linked to You                                     │
│  ✓ Contact Info (if account created)                    │
│  ✓ User Content (if saved)                              │
│  ✓ Identifiers (if logged in)                           │
│  ✓ Usage Data                                           │
│  ✓ Diagnostics                                          │
├─────────────────────────────────────────────────────────┤
│  Data Not Linked to You                                 │
│  ✓ Diagnostics                                          │
│  ✓ Usage Data (aggregated)                              │
├─────────────────────────────────────────────────────────┤
│  Data Used to Track You                                 │
│  None                                                   │
└─────────────────────────────────────────────────────────┘
```

---

## Summary: All Three Apps

| App | Contact Info | User Content | Identifiers | Usage Data | Location |
|-----|--------------|--------------|-------------|------------|----------|
| TaskFlow v3 | ✓ | ✓ | ✓ | ✓ | ✗ |
| TeenPopTastic | ✓ | ✓ | ✓ | ✓ | City-level |
| MemeCraftVibe | Optional | Optional (if saved) | Optional | ✓ | ✗ |

**Common across all apps:**
- ✓ Diagnostics (linked)
- ✓ Diagnostics (not linked)
- ✗ Tracking across apps/sites

---

## Third-Party SDK Summary

| SDK | Used By | Data | Linked? |
|-----|---------|------|---------|
| **Supabase** | All 3 | Auth, content | Yes (required) |
| **Sentry** | All 3 | Crashes, errors | No (anonymized) |
| **Mixpanel** | All 3 | Analytics events | No (aggregated) |
| **Paddle/RevenueCat** | All 3 | Subscription status | Yes (minimal) |
| **Spotify SDK** | TeenPopTastic | Music profile | Yes (user-granted) |
| **Apple Music Kit** | TeenPopTastic | Music profile | Yes (user-granted) |
| **OpenAI API** | MemeCraftVibe | Text only | No |

---

## Data Collection Minimization Strategy

### Design Principles
1. **Collect only what's necessary** - Every data point must justify its existence
2. **Local-first when possible** - Process data on device when feasible
3. **Aggregate for analytics** - No PII in analytics events
4. **User control** - Clear opt-out for data collection
5. **Delete by default** - Auto-delete after retention period

### Specific Implementations

**TaskFlow v3:**
- All task data encrypted at rest
- Analytics events contain no task content
- AI focus selection uses anonymized task patterns

**TeenPopTastic:**
- Location is city-level only (not precise)
- Music profile data cached, not real-time
- Under-16: additional data minimization

**MemeCraftVibe:**
- Can use without account
- Local generation before cloud save
- AI requests contain no user identifiers

---

## App Store Connect Input Guide

When completing App Store Connect privacy details:

### For TaskFlow v3
- **Linked to You:** Contact Info, User Content, Identifiers, Usage Data, Diagnostics
- **Not Linked to You:** Diagnostics
- **Tracking:** None
- **Third-party:** Supabase, Sentry, Mixpanel, Paddle/RevenueCat

### For TeenPopTastic
- **Linked to You:** Contact Info, User Content, Identifiers, Usage Data, Diagnostics, Location
- **Not Linked to You:** Diagnostics
- **Tracking:** None
- **Third-party:** Supabase, Sentry, Mixpanel, Spotify, Apple Music, Paddle/RevenueCat

### For MemeCraftVibe
- **Linked to You:** Contact Info (optional), User Content (optional), Identifiers (optional), Usage Data, Diagnostics
- **Not Linked to You:** Diagnostics, Usage Data
- **Tracking:** None
- **Third-party:** Supabase, Sentry, Mixpanel, OpenAI, Paddle/RevenueCat

---

## Compliance Notes

### GDPR Compliance
- All data collection has lawful basis (contract, legitimate interest)
- User rights implemented (access, deletion, portability)
- Data minimization applied across all apps
- Clear disclosure in privacy policy

### CCPA Compliance
- No sale of personal data
- "Do Not Sell" not required (but will include for transparency)
- California residents can request deletion
- Non-discrimination policy documented

### COPPA Compliance (TeenPopTastic)
- Under 13: not allowed
- Ages 13-15: parental consent required
- Data minimization for minors
- Parent tools implemented

---

*Last updated: 2026-01-28*
*Status: READY FOR APP STORE CONNECT*
