# Mobile App Architect — Phase Templates

Replace all `[PLACEHOLDERS]` with user-specific values before generating output.

---

## Phase 1: App Blueprint (Product Strategy)

**Prompt:**
> Act as principal mobile product architect. I'm creating `[APP NAME]` for `[TARGET USERS]` to solve `[PROBLEM]`. Create a mobile-first blueprint with:
> - **Personas:** 2-3 detailed personas (name, age, goals, frustrations, behavior patterns)
> - **Pain Points:** Top 5 problems the app solves, ranked by severity
> - **Value Proposition:** Single sentence + 3 supporting differentiators
> - **Features by scope:**
>   - **MVP** (must-have, ship in 4-6 weeks)
>   - **V1** (core enhancement, ship in 8-12 weeks)
>   - **V2** (growth features, 16+ weeks)
> - **User Flow:** End-to-end happy path (5-8 steps)
> - **Monetization:** Model (subscription/freemium/ads/one-time), pricing tier, conversion triggers
> - **Risks:**
>   - Product risks (3+)
>   - UX risks (3+)
>   - Technology risks (3+)
>
> Format: **table** for features + risks. **Summary paragraph** for flow and monetization.

**Output template:**
```markdown
# App Blueprint: [APP NAME]
## Personas
| Name | Age | Role | Goals | Frustrations | Behavior |
|------|-----|------|-------|--------------|----------|
| ... | ... | ... | ... | ... | ... |

## Pain Points
1. [problem] — severity: high/medium/low
2. ...

## Value Proposition
**[One sentence.]**
1. Differentiator 1
2. Differentiator 2
3. Differentiator 3

## Features
| Scope | Feature | Description | Effort |
|-------|---------|-------------|--------|
| MVP | ... | ... | ... |
| V1 | ... | ... | ... |
| V2 | ... | ... | ... |

## User Flow
1. → 2. → 3. → 4. → 5. → 6. → 7. → 8.

## Monetization
**Model:** [subscription/freemium/ads/one-time]
**Tiers:** [pricing]
**Conversion triggers:** [what makes users pay]

## Risks
| Category | Risk | Likelihood | Mitigation |
|----------|------|------------|------------|
| Product | ... | H/M/L | ... |
| UX | ... | H/M/L | ... |
| Technology | ... | H/M/L | ... |
```

---

## Phase 2: App Structure (Mobile Architecture)

**Prompt:**
> Act as senior mobile architect. Design the production-ready structure of `[APP NAME]` in `[iOS/Android/Flutter/React Native]`. Include:
> - **Folder structure** (tree view)
> - **Screens** (list with navigation route)
> - **Reusable components** (shared widgets)
> - **State management** (approach, store shape, data flow)
> - **API layer** (service classes, interceptors, error mapping)
> - **Authentication flow** (login, token refresh, logout, protected routes)
> - **Navigation** (stack, tab, modal patterns)
> - **Storage** (local cache, secure storage, preferences)
> - **Error handling** (global handler, retry, offline)
> - **Analytics** (events, screen tracking, crash reporting)

**Output template:**
```markdown
# App Structure: [APP NAME]

## Folder Structure
```
lib/
├── app/
│   ├── app.dart
│   └── router.dart
├── core/
│   ├── api/
│   ├── auth/
│   ├── storage/
│   ├── error/
│   └── analytics/
├── features/
│   ├── auth/
│   ├── home/
│   ├── profile/
│   └── ...
└── shared/
    ├── widgets/
    └── theme/
```

## Screens
| Route | Screen | Auth req'd | Description |
|-------|--------|------------|-------------|
| /splash | SplashScreen | No | ... |
| /login | LoginScreen | No | ... |
| /home | HomeScreen | Yes | ... |

## State Management
- **Approach:** [e.g., Riverpod/Redux/Bloc]
- **Store shape:** [JSON structure of app state]
- **Data flow:** [unidirectional diagram description]

## API Layer
- **HTTP client:** [e.g., Dio/Alamofire/URLSession]
- **Base URL:** [value]
- **Interceptors:** [auth, logging, retry]
- **Error mapping:** [APIException → DomainException]

## Authentication
- **Flow:** login → JWT → secure storage → auto-attach → refresh → logout
- **Protected routes:** [mechanism]
- **Session persistence:** [secure storage + biometric]

## Navigation
- **Main navigation:** [bottom tabs / drawer / tab bar]
- **Modals:** [full-screen / bottom sheet]
- **Deep linking:** [scheme + path structure]

## Storage
| Type | Tool | Data |
|------|------|------|
| Secure | ... | tokens, keys |
| Cache | ... | user data, preferences |
| DB | ... | offline records |

## Error Handling
- **Global handler:** [error boundary / middleware]
- **Retry:** [exponential backoff, max 3]
- **Offline queue:** [write local, sync on reconnect]

## Analytics
| Provider | Events | Purpose |
|----------|--------|---------|
| ... | screen_view, login, purchase | engagement |
| ... | crash, error | stability |
```

---

## Phase 3: UX Flow (UX Design)

**Prompt:**
> Act as senior mobile UX designer. Create screen-by-screen UX plan for `[APP NAME]` for `[TARGET USERS]` in `[STYLE]` style. For each screen include:
> - **Objective** (user goal on this screen)
> - **Main action** (primary interaction)
> - **UI elements** (list with layout description)
> - **States:** empty, loading, error, success
> - **CTA** (button text, placement, behavior)
> - **Microcopy** (key labels, placeholders, error messages)
> - **Retention opportunity** (what brings user back)

**Output template:**
```markdown
# UX Flow: [APP NAME]

## Screen 1: Splash
| Element | Detail |
|---------|--------|
| Objective | Brand intro, check auth |
| Main action | Auto-check → navigate |
| UI | Logo centered, loading spinner below |
| Loading | Lottie animation (2s max) |
| Error | Offline state with retry button |
| CTA | None (auto-transition) |
| Microcopy | None |
| Retention | - |

## Screen 2: [Screen Name]
...

*(Repeat for every screen in the app)*
```

---

## Phase 4: PRD (Product Requirements Document)

**Prompt:**
> Act as CTO + PM of a startup. Write a concise PRD for `[APP NAME]`. Include:
> - **Product overview** (one paragraph)
> - **User problem** (the job to be done)
> - **Goals** (3-5 OKRs)
> - **Non-goals** (explicitly excluded from scope)
> - **Target audience** (demographics, tech literacy, platform)
> - **Core features** (list with acceptance criteria per feature)
> - **Requirements** (functional + non-functional)
> - **Edge cases** (offline, slow network, empty state, concurrent access, account deletion)
> - **Technical considerations** (platform choice, 3rd-party dependencies, compliance)
> - **Success metrics** (DAU/MAU, retention D1/D7/D30, conversion rate, NPS, crash rate)
> - **Launch scope** (what ships in v1.0)
> - **Roadmap** (6-month timeline with milestones)

**Output template:**
```markdown
# PRD: [APP NAME]

## Product Overview
[1 paragraph]

## User Problem
**Job to be done:** [statement]

## Goals
1. **Objective:** [KR1, KR2]

## Non-Goals
- [excluded feature 1]
- [excluded feature 2]

## Target Audience
- **Demographics:** [age, location, income]
- **Tech literacy:** [low/medium/high]
- **Platform:** [iOS/Android/both]

## Core Features
| Feature | Acceptance Criteria | Priority |
|---------|-------------------|----------|
| [name] | Given/when/then | P0 |

## Edge Cases
- **Offline:** ...
- **Empty state:** ...
- **Account deletion:** ...

## Success Metrics
| Metric | Target | Measurement |
|--------|--------|------------|
| D1 retention | >40% | Amplitude |
| D7 retention | >20% | Amplitude |
| Crash rate | <0.1% | Firebase |

## Launch Scope (v1.0)
[Features that ship]

## 6-Month Roadmap
| Month | Milestone |
|-------|-----------|
| 1 | MVP alpha |
| 2 | Beta launch |
| 3-4 | V1 features |
| 5-6 | Growth + V2 |
```

---

## Phase 5: Backend Logic (Backend Architecture)

**Prompt:**
> Act as senior backend architect. For `[APP NAME]` with features `[FEATURES]`, generate backend requirements:
> - **DB schema** (tables, relationships, indexes, migration strategy)
> - **Auth/roles** (user model, roles/permissions, OAuth providers, MFA)
> - **APIs** (endpoints grouped by domain, methods, request/response, pagination)
> - **Integrations** (3rd-party services, webhooks, web sockets)
> - **Notifications** (push, email, in-app — triggers and delivery)
> - **Storage** (file uploads, CDN, signed URLs)
> - **Payments** (provider, products, webhooks, receipts, refunds)
> - **Admin panel** (dashboard, user management, analytics, moderation)
> - **Rate limits** (tiered limits, burst handling, throttle strategy)
> - **Security risks** (OWASP top 10, data privacy, GDPR, compliance)
>
> Keep it **MVP-friendly** — flag what's deferred.

**Output template:**
```markdown
# Backend Logic: [APP NAME]

## Database Schema
| Table | Columns | Indexes | Relations |
|-------|---------|---------|-----------|
| users | id, email, name, ... | email UNIQUE | → sessions |
| ... | ... | ... | ... |

## Auth & Roles
- **Auth method:** [JWT / OAuth / custom]
- **Roles:** [user, admin, moderator]
- **OAuth providers:** [Google, Apple, email/password]
- **MFA:** [SMS/TOTP/biometric — deferred to v1]

## APIs
| Method | Endpoint | Auth | Description |
|--------|----------|------|-------------|
| GET | /api/v1/items | JWT | List items (paginated) |
| POST | /api/v1/items | JWT | Create item |
| ... | ... | ... | ... |

## Integrations
| Service | Purpose | Deferred? |
|---------|---------|-----------|
| Stripe | Payments | No |
| SendGrid | Emails | No |
| Firebase Cloud Messaging | Push | No |

## Notifications
- **Triggers:** [e.g., new follower, payment received, account alert]
- **Delivery:** Push (FCM/APNs) + Email (SendGrid) + In-app feed

## Storage
- **Provider:** [S3 / Cloud Storage / Azure Blob]
- **Policy:** Signed URLs, 15-min expiry, CDN cache 24h

## Payments
- **Provider:** Stripe
- **Products:** [subscription_monthly, subscription_yearly, consumable_credit]
- **Webhooks:** checkout.session.completed, invoice.paid, customer.subscription.deleted

## Admin Panel
- **Dashboard:** DAU, MRR, crash rate, active users
- **User management:** search, ban, delete, export
- **Content moderation:** flag, review, remove

## Rate Limits
| Tier | Requests/min | Burst |
|------|-------------|-------|
| Free | 60 | 10 |
| Pro | 300 | 50 |
| Admin | 1000 | 200 |

## Security Risks
| Risk | Impact | Mitigation | Deferred |
|------|--------|------------|----------|
| SQL injection | Critical | Parameterized queries | No |
| Rate limit bypass | High | IP + user-based limits | No |
| GDPR compliance | High | Data deletion API | V1 |
```

---

## Phase 6: UI Design System (Visual Design)

**Prompt:**
> Act as world-class mobile UI designer. Create a UI design system for `[APP NAME]` for `[TARGET USERS]` with a `[BRAND STYLE]` style. Include:
> - **Colors** (primary, secondary, accent, neutral, semantic — hex codes, usage rules)
> - **Typography** (typeface, scale, weights, line heights, usage per element)
> - **Spacing** (4px grid system, padding for all breakpoints)
> - **Buttons** (primary, secondary, ghost, icon, destructive — states: default, pressed, disabled, loading)
> - **Inputs** (text, search, password, textarea, dropdown — states: empty, focused, error, disabled)
> - **Cards** (default, elevated, tappable — padding, radius, shadow)
> - **Navigation patterns** (tab bar, navbar, bottom sheet, modal)
> - **Icons** (style: outlined/filled, weight, sizing grid)
> - **Onboarding style** (illustration type, animation direction, skip/paginate)
> - **Premium visual direction** (animations, micro-interactions, transitions, elevation cues)

**Output template:**
```markdown
# UI Design System: [APP NAME]

## Colors
| Token | Hex | Usage |
|-------|-----|-------|
| primary | #... | CTAs, active states |
| secondary | #... | accents, links |
| neutral-100 | #... | background |
| neutral-900 | #... | text primary |
| success | #... | confirmations |
| error | #... | errors |
| warning | #... | warnings |

## Typography
| Style | Font | Size | Weight | Line H | Usage |
|-------|------|------|--------|--------|-------|
| h1 | [font] | 32 | Bold | 40 | Screen title |
| body | [font] | 16 | Regular | 24 | Paragraph |
| caption | [font] | 12 | Regular | 16 | Helper text |

## Spacing
**Grid:** 4px base. Increments: 4, 8, 12, 16, 20, 24, 32, 40, 48, 56, 64.

## Buttons
| Type | Height | Radius | Text | States |
|------|--------|--------|------|--------|
| Primary | 52 | 12 | 16/600 | bg-primary, opacity-0.5 disabled, spinner loading |
| Secondary | 48 | 12 | 16/600 | border + transparent bg |
| Ghost | 44 | 8 | 14/500 | no bg, text only |

## Inputs
| State | Border | BG | Label |
|-------|--------|----|-------|
| Empty | neutral-300 | white | neutral-500 |
| Focused | primary | white | primary |
| Error | error | error-50 | error |
| Disabled | neutral-200 | neutral-100 | neutral-400 |

## Cards
| Variant | Radius | Padding | Shadow |
|---------|--------|---------|--------|
| Default | 12 | 16 | 0 2 8 rgba(0,0,0,0.06) |
| Elevated | 16 | 20 | 0 8 24 rgba(0,0,0,0.10) |
| Tappable | 12 | 16 | + press scale(0.98) |

## Navigation
- **Tab bar:** 4-5 icons + labels, active = primary, inactive = neutral-400
- **Bottom sheet:** grabber handle, 60% / 90% snap points
- **Modal:** full-screen with close icon, slide-up transition (250ms ease-out)

## Icons
- **Style:** outlined, 1.5px stroke
- **Size grid:** 20, 24, 28, 32
- **Weight:** regular (20x20), medium (24x24), large (28x28)

## Onboarding
- **Illustrations:** Isometric 3D style, warm color palette
- **Animation:** Lottie — fade in from bottom, stagger 200ms per slide
- **Navigation:** Skip button top-right, dot indicators, "Next" / "Get Started"
- **Max slides:** 4

## Premium Visual Direction
- **Micro-interactions:** button press scale(0.95), card spring animation, pull-to-refresh custom icon
- **Transitions:** shared element hero animations, page curl between tabs
- **Elevation:** custom shadow paths (not default box-shadow), 3 levels
- **Loading:** shimmer skeleton screens (not spinners)
- **Empty states:** illustrated + CTA (not plain text)
```

---

## Phase 7: Starter Code (Code Scaffolding)

**Prompt:**
> Act as senior engineer in `[SwiftUI/Kotlin/Flutter/React Native]`. Generate the starter codebase for `[APP NAME]` with `[FEATURES]`. Include:
> - **Project setup** (initialization commands, dependencies, config files)
> - **Navigation setup** (route definitions, tab navigation, stack navigation)
> - **Authentication flow** (login screen, auth provider, token storage, protected routes)
> - **Home screen** (list/grid, pull-to-refresh, skeleton loading)
> - **API layer** (HTTP client, interceptors, endpoint definitions, error handling)
> - **Reusable components** (button, card, input, loading, empty state, error state)
> - **State management** (store, actions/reducers, selectors)
> - **Mock data** (fixtures, mock API responses, development mode toggle)
> - **Loading & error handling** (global error boundary, retry, offline banner, toast)

**Output template:**
```markdown
# Starter Code: [APP NAME]

## Tech Stack
- **Framework:** [React Native / Flutter / SwiftUI / Jetpack Compose]
- **State management:** [Redux Toolkit / Riverpod / Combine / MutableState]
- **Navigation:** [React Navigation / Navigator 2.0 / NavigationStack / NavHost]
- **HTTP client:** [Axios / Dio / URLSession / Retrofit]
- **Storage:** [AsyncStorage / SharedPreferences / UserDefaults / DataStore]
- **Auth:** [JWT with refresh rotation]

## Setup
```bash
# React Native
npx react-native init [AppName] --template react-native-template-typescript
cd [AppName]
npm install @react-navigation/native @react-navigation/bottom-tabs axios ...

# Flutter
flutter create [app_name]
flutter pub add go_router dio flutter_secure_storage riverpod ...
```

## Navigation Structure
```dart
// Flutter: go_router
final router = GoRouter(
  initialLocation: '/splash',
  routes: [
    GoRoute(path: '/splash', builder: (_, __) => SplashScreen()),
    GoRoute(path: '/login', builder: (_, __) => LoginScreen()),
    ShellRoute(
      builder: (_, __, child) => MainShell(child: child),
      routes: [
        GoRoute(path: '/home', builder: (_, __) => HomeScreen()),
        GoRoute(path: '/search', builder: (_, __) => SearchScreen()),
        GoRoute(path: '/profile', builder: (_, __) => ProfileScreen()),
      ],
    ),
  ],
);
```

## Authentication Flow
[Code for auth provider, token interceptor, login/logout, auto-refresh]

## API Layer
[Code for HTTP client, endpoint classes, error mapping, response types]

## Reusable Components
[Tabs for: Button, Card, TextInput, LoadingSkeleton, EmptyState, ErrorState]

## Mock Data
[Fixture JSON, mock interceptor, dev-mode toggle]

## Error Handling
[Error boundary widget, retry logic, offline banner, toast notifications]
```

---

## Phase 8: Brutal Audit (QA + Growth)

**Prompt:**
> Act as brutally honest mobile QA lead + growth PM. Audit this app idea: `[APP NAME]` — `[APP DESCRIPTION FROM PHASE 1]`. Find:
> - **Weak UX** (friction points, confusing navigation, poor affordance)
> - **Confusing flows** (drop-off points, unclear CTAs, dead ends)
> - **Retention risks** (no reason to return, boring onboarding, notification fatigue)
> - **Monetization errors** (paywall too early, wrong pricing, no perceived value)
> - **App Store risks** (rejected design patterns, guideline violations, screenshot weaknesses)
> - **Privacy issues** (unnecessary permissions, data collection, GDPR blind spots)
> - **Tech debt traps** (over-engineering, wrong state management, unscalable schema)
> - **Unnecessary features** (YAGNI violations, feature creep)
>
> For each finding: **rating** (critical/major/minor), **impact** (retention/revenue/trust/performance), and **suggested fix**.

**Output template:**
```markdown
# Brutal Audit: [APP NAME]

| # | Category | Finding | Rating | Impact | Fix |
|---|----------|---------|--------|--------|-----|
| 1 | UX | [finding] | Critical | Retention | [fix] |
| 2 | Flow | [finding] | Major | Revenue | [fix] |
| 3 | Retention | [finding] | Critical | Retention | [fix] |
| 4 | Monetization | [finding] | Major | Revenue | [fix] |
| 5 | App Store | [finding] | Minor | Trust | [fix] |
| 6 | Privacy | [finding] | Critical | Trust | [fix] |
| 7 | Tech Debt | [finding] | Major | Performance | [fix] |
| 8 | Unnecessary | [finding] | Minor | All | [fix] |

## Priority Fixes
1. [Fix 1] — do before launch
2. [Fix 2] — do before launch
3. [Fix 3] — do in V1
```

---

## Phase 9: Launch Plan (GTM Strategy)

**Prompt:**
> Act as mobile launch strategist. Create a GTM plan for `[APP NAME]` for `[TARGET USERS]`. Include:
> - **Pre-launch checklist** (30-day, 14-day, 7-day, 1-day before)
> - **Beta plan** (TestFlight/Play Console, cohort size, feedback cadence, NPS target)
> - **Onboarding improvement** (first-run funnel, activation step, time-to-value, aha moment)
> - **App Store strategy** (keywords, category, subtitle, description hook, screenshot copy, rating prompt)
> - **Launch content** (blog post, demo video, social carousel, press release)
> - **Influencer/community ideas** (niche creators, subreddits, Discord, Twitter/X threads)
> - **Push notification plan** (welcome, re-engagement, feature announcement, transactional — cadence per type)
> - **Referral loop** (share mechanism, reward structure, viral coefficient target)
> - **30-day retention metrics** (D1, D7, D14, D30 targets + action plan per day)

**Output template:**
```markdown
# Launch Plan: [APP NAME]

## Pre-Launch Checklist
| When | Task | Owner |
|------|------|-------|
| T-30 | Finalize app icon + screenshots | Design |
| T-30 | Write privacy policy + ToS | Legal |
| T-14 | Submit to App Store + Play Store | Dev |
| T-7 | Prepare press kit + assets | Marketing |
| T-1 | Final server scaling test | Backend |
| T-0 | Flip the switch | PM |

## Beta Plan
- **Platform:** TestFlight + Play Console internal testing
- **Cohort:** 500 users
- **Feedback:** In-app survey (NPS) + weekly 1:1 calls with top 10
- **Target NPS:** >40 at beta exit

## Onboarding
- **First-run funnel:** Sign up → Permission request → Quick tutorial (3 steps) → First value action
- **Activation step:** [specific action that predicts retention]
- **Time-to-value:** <90 seconds from install to aha moment

## App Store Strategy
| Element | Strategy |
|---------|----------|
| Keywords | [top 10 keywords] |
| Category | [primary + secondary] |
| Subtitle | [30 chars] |
| Description hook | [first 2 lines] |
| Screenshot copy | [per screenshot plan] |

## Launch Content
1. Blog post: "Why we built [APP NAME]" (ProductHunt + Medium)
2. Demo video: 60s, social-first (vertical), 3 hook cuts
3. Social carousel: 5-slide Instagram/LinkedIn explainer
4. Press release: distributed via [wire service]

## Influencer & Community
- **Creators:** 5 micro-influencers in [niche] — free lifetime Pro in exchange for post
- **Subreddits:** r/[niche] — value post (not link drop)
- **Discord:** Launch day AMA in 3 relevant servers
- **Twitter/X:** Thread with 10 tips → CTA to download

## Push Notification Plan
| Type | Trigger | Cadence | Copy style |
|------|---------|---------|------------|
| Welcome | Install +60 min | 1x only | Warm, benefit-driven |
| Re-engagement | 3d inactive | Max 2/week | Curiosity + FOMO |
| Feature | New feature | 1x per feature | Educational |
| Transactional | User action | Real-time | Neutral, info |

## Referral Loop
- **Mechanism:** Share invite link → both get [reward]
- **Reward:** [1 month Pro / 5 credits / exclusive content]
- **Target viral coefficient:** >0.3

## 30-Day Retention Plan
| Day | Target | Action |
|-----|--------|--------|
| D1 | >40% | Push: "You're in! Try [core action]" |
| D7 | >25% | Notification + email: "Your weekly summary" |
| D14 | >20% | Feature announcement push |
| D30 | >15% | "You've been here 30 days! Here's what you achieved" |
```

---

## Phase 10: Complete Lead (Program Management)

**Prompt:**
> Act as my senior mobile apps leader. I'm creating `[APP NAME]` for `[TARGET USERS]` using `[TECHNOLOGY STACK]`. Divide the project into phases: strategy, UX, architecture, backend, code, QA, and launch. For each phase, give me:
> - **Deliverables** (artifacts produced)
> - **Key decisions** (choices that must be locked before proceeding)
> - **Risks** (what could go wrong + contingency)
> - **Next prompts** (specific questions to ask your team / the AI)
>
> Format: **table** per phase, summary timeline at end.

**Output template:**
```markdown
# Complete Lead: [APP NAME]

## Phase Map

| Phase | Timeline | Deliverables | Gate |
|-------|----------|--------------|------|
| 1. Strategy | Week 1-2 | Blueprint doc, personas, value prop | Approved by stakeholders |
| 2. UX | Week 2-3 | UX flow, wireframes, microcopy | Usability test pass |
| 3. Architecture | Week 3-4 | App structure, DB schema, API design | Tech review sign-off |
| 4. Backend | Week 4-8 | DB deployed, APIs live, admin panel | API integration test pass |
| 5. Design | Week 4-6 | Design system, all screens | Design QA pass |
| 6. Code | Week 5-12 | Starter code, all features | Sprint demo acceptance |
| 7. QA | Week 12-14 | Audit report, bug fixes, performance | Crash rate <0.1% |
| 8. Launch | Week 14-16 | App Store submission, GTM plan | Launch day checklist |

## Phase Details

### Phase 1: Strategy
| Area | Detail |
|------|--------|
| Deliverables | Blueprint doc, personas, value prop, feature matrix |
| Key decisions | Platform first: iOS vs Android vs both. Monetization model. MVP scope boundary. |
| Risks | Unvalidated demand (do surveys first). Scope creep (hold MVP line). |
| Next prompts | "Rank these 3 persona segments by revenue potential." "What assumptions need validation before building?" |

### Phase 2: UX
| Area | Detail |
|------|--------|
| Deliverables | Screen-by-screen UX plan, onboarding flow, error/empty states, microcopy sheet |
| Key decisions | Navigation pattern (tabs vs drawer). Permission request timing. First-run flow order. |
| Risks | Over-designed first version (ship simpler). Permission prompt rejection (delay non-critical). |
| Next prompts | "Show me the onboarding funnel with drop-off estimates." "Which screen has the highest cognitive load?" |

### Phase 3: Architecture
| Area | Detail |
|------|--------|
| Deliverables | Folder structure, state management plan, API contracts, DB schema, navigation map |
| Key decisions | State management library. Offline-first vs online-first. Local DB choice. |
| Risks | Wrong abstraction layer (too generic). Over-engineering early (YAGNI). |
| Next prompts | "Draw the data flow from API → state → UI for the home screen." "Estimate API response sizes." |

### Phase 4: Backend
| Area | Detail |
|------|--------|
| Deliverables | DB migrations, REST/GraphQL endpoints, auth system, admin dashboard, CI/CD |
| Key decisions | Serverless vs dedicated. SQL vs NoSQL. REST vs GraphQL. Image processing approach. |
| Risks | Scaling too early (stay monolithic). Payment integration errors (test webhooks thoroughly). |
| Next prompts | "What's the peak concurrent user estimate? Does the architecture handle 10x?" "Run through the payment failure flow." |

### Phase 5: Design
| Area | Detail |
|------|--------|
| Deliverables | Design system (colors, fonts, components), final screen designs, asset exports |
| Key decisions | Animation library. Icon set (custom vs system). Dark mode scope. |
| Risks | Design mismatch with platform conventions. Heavy animations hurting performance. |
| Next prompts | "Show screenshots on iPhone SE and Android small screen." "Is the design system accessible (WCAG AA)?" |

### Phase 6: Code
| Area | Detail |
|------|--------|
| Deliverables | Working app with all MVP features, test coverage, CI pipeline |
| Key decisions | Testing framework. Code review process. Branch strategy. |
| Risks | Incomplete error handling (ship with global error boundary only). Missing analytics (add early). |
| Next prompts | "Generate the API client classes for all endpoints." "What's the test coverage report?" |

### Phase 7: QA
| Area | Detail |
|------|--------|
| Deliverables | Audit report, bug tracker, crash-free rate, performance benchmarks |
| Key decisions | Which bugs block launch. Performance budget for each screen. |
| Risks | Launching with known critical bugs. Weak error states discovered late. |
| Next prompts | "Run a brutal audit on the current build." "What's the app size on device?" |

### Phase 8: Launch
| Area | Detail |
|------|--------|
| Deliverables | App Store submission, GTM calendar, press kit, beta cohort results |
| Key decisions | Launch day: soft vs hard. Pricing finalization. Country rollout order. |
| Risks | App Store rejection (budget 2 weeks). Server overload on launch day (auto-scale). |
| Next prompts | "Generate the App Store description with keywords." "Create the 30-day push notification plan." |

## Timeline
```
Week 1  | Strategy
Week 2  | UX + Architecture start
Week 3  | Architecture + Backend start
Week 4  | Backend + Design
Week 5  | Backend + Code start
Week 6  | Code
Week 7  | Code
Week 8  | Code + Integration
Week 9  | Code
Week 10 | Code
Week 11 | QA
Week 12 | QA + Launch prep
Week 13 | Launch
```
```
