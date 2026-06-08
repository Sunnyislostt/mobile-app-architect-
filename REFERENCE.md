# Mobile App Architect — Phase Templates

Replace `[PLACEHOLDERS]` with user-specific values before generation.

---

## Phase 1: App Blueprint (Product Strategy)

**Prompt:**
> Act as principal mobile product architect. Build `[APP NAME]` for `[TARGET USERS]` solving `[PROBLEM]`. Mobile-first blueprint with:
> - **Personas:** 2-3 detailed (name, age, goals, frustrations, behavior)
> - **Pain Points:** Top 5 problems solved, ranked by severity
> - **Value Proposition:** 1 sentence + 3 differentiators
> - **Features by scope:**
>   - **MVP** (must-have, ship 4-6 weeks)
>   - **V1** (enhancement, ship 8-12 weeks)
>   - **V2** (growth, 16+ weeks)
> - **User Flow:** End-to-end happy path (5-8 steps)
> - **Monetization:** Model (subscription/freemium/ads/one-time), pricing tier, conversion triggers
> - **Risks:** Product (3+), UX (3+), Technology (3+)
>
> Format: **table** for features + risks. **Summary paragraph** for flow + monetization.

**Output template:**
```markdown
# App Blueprint: [APP NAME]
## Personas
| Name | Age | Role | Goals | Frustrations | Behavior |
|------|-----|------|-------|--------------|----------|
| ... | ... | ... | ... | ... | ... |

## Pain Points
1. [problem] — severity: high/medium/low

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
> Act as senior mobile architect. Design production-ready structure for `[APP NAME]` in `[iOS/Android/Flutter/React Native]`. Include:
> - **Folder structure** (tree view)
> - **Screens** (list with nav route)
> - **Reusable components** (shared widgets)
> - **State management** (approach, store shape, data flow)
> - **API layer** (service classes, interceptors, error mapping)
> - **Auth flow** (login, token refresh, logout, protected routes)
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
- **Store shape:** [JSON structure]
- **Data flow:** [unidirectional]

## API Layer
- **HTTP client:** [Dio/Alamofire/URLSession]
- **Base URL:** [value]
- **Interceptors:** [auth, logging, retry]
- **Error mapping:** [APIException → DomainException]

## Authentication
- **Flow:** login → JWT → secure storage → auto-attach → refresh → logout
- **Protected routes:** [mechanism]
- **Session persistence:** [secure storage + biometric]

## Navigation
- **Main nav:** [bottom tabs / drawer / tab bar]
- **Modals:** [full-screen / bottom sheet]
- **Deep linking:** [scheme + path]

## Storage
| Type | Tool | Data |
|------|------|------|
| Secure | ... | tokens, keys |
| Cache | ... | user data, prefs |
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
> Act as senior mobile UX designer. Create screen-by-screen UX plan for `[APP NAME]` for `[TARGET USERS]` in `[STYLE]` style. Per screen:
> - **Objective** (user goal)
> - **Main action** (primary interaction)
> - **UI elements** (list + layout)
> - **States:** empty, loading, error, success
> - **CTA** (button text, placement, behavior)
> - **Microcopy** (labels, placeholders, error messages)
> - **Retention opportunity** (what brings user back)

**Output template:**
```markdown
# UX Flow: [APP NAME]

## Screen 1: Splash
| Element | Detail |
|---------|--------|
| Objective | Brand intro, check auth |
| Main action | Auto-check → navigate |
| UI | Logo centered, spinner below |
| Loading | Lottie animation (2s max) |
| Error | Offline state + retry button |
| CTA | None (auto-transition) |
| Microcopy | None |
| Retention | - |
```

---

## Phase 4: PRD (Product Requirements)

**Prompt:**
> Act as CTO + PM of startup. Write concise PRD for `[APP NAME]`. Include:
> - **Product overview** (1 paragraph)
> - **User problem** (job to be done)
> - **Goals** (3-5 OKRs)
> - **Non-goals** (excluded scope)
> - **Target audience** (demographics, tech literacy, platform)
> - **Core features** (list + acceptance criteria per feature)
> - **Requirements** (functional + non-functional)
> - **Edge cases** (offline, slow network, empty state, concurrent access, account deletion)
> - **Technical considerations** (platform, 3rd-party deps, compliance)
> - **Success metrics** (DAU/MAU, D1/D7/D30 retention, conversion rate, NPS, crash rate)
> - **Launch scope** (v1.0)
> - **Roadmap** (6-month timeline)

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
| Metric | Target | Tool |
|--------|--------|------|
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
> - **Auth/roles** (user model, roles, OAuth providers, MFA)
> - **APIs** (endpoints by domain, methods, request/response, pagination)
> - **Integrations** (3rd-party, webhooks, web sockets)
> - **Notifications** (push, email, in-app — triggers, delivery)
> - **Storage** (file uploads, CDN, signed URLs)
> - **Payments** (provider, products, webhooks, receipts, refunds)
> - **Admin panel** (dashboard, user mgmt, analytics, moderation)
> - **Rate limits** (tiered, burst handling, throttle strategy)
> - **Security risks** (OWASP top 10, data privacy, GDPR)
>
> Keep **MVP-friendly** — flag deferred items.

**Output template:**
```markdown
# Backend Logic: [APP NAME]

## Database Schema
| Table | Columns | Indexes | Relations |
|-------|---------|---------|-----------|
| users | id, email, name, ... | email UNIQUE | → sessions |

## Auth & Roles
- **Auth method:** [JWT / OAuth / custom]
- **Roles:** [user, admin, moderator]
- **OAuth:** [Google, Apple, email/password]
- **MFA:** [deferred to v1]

## APIs
| Method | Endpoint | Auth | Description |
|--------|----------|------|-------------|
| GET | /api/v1/items | JWT | List (paginated) |
| POST | /api/v1/items | JWT | Create |

## Integrations
| Service | Purpose | Deferred? |
|---------|---------|-----------|
| Stripe | Payments | No |
| SendGrid | Emails | No |
| FCM | Push | No |

## Notifications
- **Triggers:** [new follower, payment, account alert]
- **Delivery:** Push (FCM/APNs) + Email + In-app

## Storage
- **Provider:** [S3 / Cloud Storage / Azure Blob]
- **Policy:** Signed URLs, 15-min expiry, CDN 24h

## Payments
- **Provider:** Stripe
- **Products:** [subscription_monthly, subscription_yearly, consumable]
- **Webhooks:** checkout.session.completed, invoice.paid, subscription.deleted

## Admin Panel
- **Dashboard:** DAU, MRR, crash rate, active users
- **User mgmt:** search, ban, delete, export
- **Moderation:** flag, review, remove

## Rate Limits
| Tier | Req/min | Burst |
|------|---------|-------|
| Free | 60 | 10 |
| Pro | 300 | 50 |
| Admin | 1000 | 200 |

## Security Risks
| Risk | Impact | Mitigation | Deferred |
|------|--------|------------|----------|
| SQL injection | Critical | Parameterized queries | No |
| Rate limit bypass | High | IP + user limits | No |
| GDPR compliance | High | Data deletion API | V1 |
```

---

## Phase 6: UI Design System (Visual Design)

**Prompt:**
> Act as world-class mobile UI designer. Create UI design system for `[APP NAME]` for `[TARGET USERS]` in `[BRAND STYLE]` style. Include:
> - **Colors** (primary, secondary, accent, neutral, semantic — hex + usage)
> - **Typography** (typeface, scale, weights, line heights, per element)
> - **Spacing** (4px grid, all breakpoints)
> - **Buttons** (primary, secondary, ghost, icon, destructive — states: default, pressed, disabled, loading)
> - **Inputs** (text, search, password, textarea, dropdown — states: empty, focused, error, disabled)
> - **Cards** (default, elevated, tappable — padding, radius, shadow)
> - **Nav patterns** (tab bar, navbar, bottom sheet, modal)
> - **Icons** (style: outlined/filled, weight, sizing grid)
> - **Onboarding style** (illustration type, animation direction, skip/paginate)
> - **Premium direction** (animations, micro-interactions, transitions, elevation)

**Output template:**
```markdown
# UI Design System: [APP NAME]

## Colors
| Token | Hex | Usage |
|-------|-----|-------|
| primary | #... | CTAs, active |
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
| Type | H | Radius | Text | States |
|------|---|--------|------|--------|
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
- **Tab bar:** 4-5 icons + labels, active=primary, inactive=neutral-400
- **Bottom sheet:** grabber, 60%/90% snap points
- **Modal:** full-screen + close icon, slide-up (250ms ease-out)

## Icons
- **Style:** outlined, 1.5px stroke
- **Sizes:** 20, 24, 28, 32
- **Weight:** regular (20), medium (24), large (28)

## Onboarding
- **Illustrations:** Isometric 3D, warm palette
- **Animation:** Lottie — fade bottom, stagger 200ms per slide
- **Nav:** Skip top-right, dot indicators, "Next"/"Get Started"
- **Max slides:** 4

## Premium Direction
- **Micro-interactions:** button press scale(0.95), card spring, pull-to-refresh custom icon
- **Transitions:** shared element hero, page curl between tabs
- **Elevation:** custom shadow paths, 3 levels
- **Loading:** shimmer skeleton (not spinners)
- **Empty states:** illustrated + CTA (not plain text)
```

---

## Phase 7: Starter Code (Code Scaffolding)

**Prompt:**
> Act as senior engineer in `[SwiftUI/Kotlin/Flutter/React Native]`. Generate starter codebase for `[APP NAME]` with `[FEATURES]`. Include:
> - **Project setup** (init commands, deps, config)
> - **Navigation** (route defs, tab nav, stack nav)
> - **Auth flow** (login screen, auth provider, token storage, protected routes)
> - **Home screen** (list/grid, pull-to-refresh, skeleton loading)
> - **API layer** (HTTP client, interceptors, endpoints, error handling)
> - **Reusable components** (button, card, input, loading, empty, error)
> - **State management** (store, actions/reducers, selectors)
> - **Mock data** (fixtures, mock responses, dev toggle)
> - **Loading & error handling** (error boundary, retry, offline banner, toast)

**Output template:**
```markdown
# Starter Code: [APP NAME]

## Tech Stack
- **Framework:** [React Native / Flutter / SwiftUI / Jetpack Compose]
- **State mgmt:** [Redux Toolkit / Riverpod / Combine / MutableState]
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
> Act as brutally honest mobile QA lead + growth PM. Audit `[APP NAME]` — `[APP DESCRIPTION FROM PHASE 1]`. Find:
> - **Weak UX** (friction, confusing nav, poor affordance)
> - **Confusing flows** (drop-off, unclear CTAs, dead ends)
> - **Retention risks** (no return reason, boring onboarding, notification fatigue)
> - **Monetization errors** (early paywall, wrong pricing, no perceived value)
> - **App Store risks** (rejected patterns, guideline violations, weak screenshots)
> - **Privacy issues** (unnecessary permissions, data collection, GDPR blind spots)
> - **Tech debt traps** (over-engineering, wrong state mgmt, unscalable schema)
> - **Unnecessary features** (YAGNI violations, feature creep)
>
> Per finding: **rating** (critical/major/minor), **impact** (retention/revenue/trust/performance), **fix**.

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
1. [Fix 1] — before launch
2. [Fix 2] — before launch
3. [Fix 3] — V1
```

---

## Phase 9: Launch Plan (GTM Strategy)

**Prompt:**
> Act as mobile launch strategist. Create GTM plan for `[APP NAME]` for `[TARGET USERS]`. Include:
> - **Pre-launch checklist** (30-day, 14-day, 7-day, 1-day)
> - **Beta plan** (TestFlight/Play Console, cohort size, feedback cadence, NPS target)
> - **Onboarding improvement** (first-run funnel, activation step, time-to-value, aha moment)
> - **App Store strategy** (keywords, category, subtitle, description hook, screenshot copy, rating prompt)
> - **Launch content** (blog, demo video, social carousel, press release)
> - **Influencer/community** (niche creators, subreddits, Discord, Twitter/X threads)
> - **Push plan** (welcome, re-engagement, feature, transactional — cadence per type)
> - **Referral loop** (share mechanism, reward, viral coefficient target)
> - **30-day retention** (D1/D7/D14/D30 targets + action per day)

**Output template:**
```markdown
# Launch Plan: [APP NAME]

## Pre-Launch Checklist
| When | Task | Owner |
|------|------|-------|
| T-30 | Finalize icon + screenshots | Design |
| T-30 | Privacy policy + ToS | Legal |
| T-14 | Submit to App Store + Play Store | Dev |
| T-7 | Press kit + assets | Marketing |
| T-1 | Server scaling test | Backend |
| T-0 | Launch | PM |

## Beta Plan
- **Platform:** TestFlight + Play Console internal
- **Cohort:** 500 users
- **Feedback:** In-app NPS survey + weekly 1:1 calls (top 10)
- **Target NPS:** >40 at exit

## Onboarding
- **Funnel:** Sign up → Permissions → Tutorial (3 steps) → First value action
- **Activation step:** [action predicting retention]
- **Time-to-value:** <90s from install to aha

## App Store Strategy
| Element | Strategy |
|---------|----------|
| Keywords | [top 10] |
| Category | [primary + secondary] |
| Subtitle | [30 chars] |
| Hook | [first 2 lines] |
| Screenshots | [per screenshot plan] |

## Launch Content
1. Blog: "Why we built [APP NAME]" (ProductHunt + Medium)
2. Demo video: 60s, vertical, 3 hook cuts
3. Social carousel: 5-slide Instagram/LinkedIn explainer
4. Press release: [wire service]

## Influencer & Community
- **Creators:** 5 micro-influencers in [niche] — free lifetime Pro for post
- **Subreddits:** r/[niche] — value post (not link drop)
- **Discord:** Launch day AMA in 3 servers
- **Twitter/X:** 10-tip thread → CTA to download

## Push Notification Plan
| Type | Trigger | Cadence | Tone |
|------|---------|---------|------|
| Welcome | Install +60min | 1x | Warm, benefit |
| Re-engagement | 3d inactive | Max 2/week | Curiosity + FOMO |
| Feature | New feature | 1x | Educational |
| Transactional | User action | Real-time | Neutral |

## Referral Loop
- **Mechanism:** Share invite link → both get [reward]
- **Reward:** [1 month Pro / 5 credits / exclusive content]
- **Viral coefficient target:** >0.3

## 30-Day Retention
| Day | Target | Action |
|-----|--------|--------|
| D1 | >40% | Push: "Try [core action]" |
| D7 | >25% | Notification + email: "Weekly summary" |
| D14 | >20% | Feature announcement push |
| D30 | >15% | "30 day milestone — here's what you achieved" |
```

---

## Phase 10: Complete Lead (Program Management)

**Prompt:**
> Act as senior mobile apps leader. Building `[APP NAME]` for `[TARGET USERS]` with `[TECH STACK]`. Divide into phases: strategy, UX, architecture, backend, code, QA, launch. Per phase:
> - **Deliverables** (artifacts)
> - **Key decisions** (choices to lock before proceeding)
> - **Risks** (what goes wrong + contingency)
> - **Next prompts** (questions for team / AI)
>
> Format: **table** per phase, summary timeline.

**Output template:**
```markdown
# Complete Lead: [APP NAME]

## Phase Map
| Phase | Timeline | Deliverables | Gate |
|-------|----------|--------------|------|
| 1. Strategy | Week 1-2 | Blueprint, personas, value prop | Stakeholder approval |
| 2. UX | Week 2-3 | UX flow, wireframes, microcopy | Usability test pass |
| 3. Architecture | Week 3-4 | Structure, DB schema, API design | Tech review sign-off |
| 4. Backend | Week 4-8 | DB deployed, APIs live, admin | API integration pass |
| 5. Design | Week 4-6 | Design system, all screens | Design QA pass |
| 6. Code | Week 5-12 | Working app, tests, CI | Sprint demo acceptance |
| 7. QA | Week 12-14 | Audit, bug fixes, perf | Crash rate <0.1% |
| 8. Launch | Week 14-16 | App Store submission, GTM | Launch checklist done |

## Phase Details

### Phase 1: Strategy
| Area | Detail |
|------|--------|
| Deliverables | Blueprint doc, personas, value prop, feature matrix |
| Key decisions | Platform first (iOS vs Android vs both). Monetization model. MVP boundary. |
| Risks | Unvalidated demand (survey first). Scope creep (hold MVP line). |
| Next prompts | "Rank 3 persona segments by revenue potential." "What assumptions need validation before building?" |

### Phase 2: UX
| Area | Detail |
|------|--------|
| Deliverables | Screen-by-screen plan, onboarding flow, error/empty states, microcopy |
| Key decisions | Nav pattern (tabs vs drawer). Permission timing. First-run flow. |
| Risks | Over-designed v1 (ship simpler). Permission rejection (delay non-critical). |
| Next prompts | "Show onboarding funnel with drop-off estimates." "Which screen has highest cognitive load?" |

### Phase 3: Architecture
| Area | Detail |
|------|--------|
| Deliverables | Folder structure, state mgmt plan, API contracts, DB schema, nav map |
| Key decisions | State mgmt library. Offline-first vs online-first. Local DB. |
| Risks | Wrong abstraction (too generic). Over-engineering (YAGNI). |
| Next prompts | "Draw data flow API → state → UI for home screen." "Estimate API response sizes." |

### Phase 4: Backend
| Area | Detail |
|------|--------|
| Deliverables | DB migrations, REST/GraphQL endpoints, auth system, admin dashboard, CI/CD |
| Key decisions | Serverless vs dedicated. SQL vs NoSQL. REST vs GraphQL. Image processing. |
| Risks | Scaling too early (stay monolithic). Payment integration errors (test webhooks). |
| Next prompts | "Peak concurrent user estimate? Handle 10x?" "Run payment failure flow." |

### Phase 5: Design
| Area | Detail |
|------|--------|
| Deliverables | Design system (colors, fonts, components), final screens, asset exports |
| Key decisions | Animation library. Icon set (custom vs system). Dark mode scope. |
| Risks | Design mismatch with platform conventions. Heavy animations → perf hit. |
| Next prompts | "Show screenshots on iPhone SE + Android small screen." "WCAG AA accessible?" |

### Phase 6: Code
| Area | Detail |
|------|--------|
| Deliverables | Working app with all MVP features, test coverage, CI pipeline |
| Key decisions | Testing framework. Code review process. Branch strategy. |
| Risks | Incomplete error handling (ship global error boundary). Missing analytics (add early). |
| Next prompts | "Generate API client classes for all endpoints." "Test coverage report?" |

### Phase 7: QA
| Area | Detail |
|------|--------|
| Deliverables | Audit report, bug tracker, crash-free rate, perf benchmarks |
| Key decisions | Which bugs block launch. Perf budget per screen. |
| Risks | Launch with known critical bugs. Weak error states found late. |
| Next prompts | "Run brutal audit on current build." "App size on device?" |

### Phase 8: Launch
| Area | Detail |
|------|--------|
| Deliverables | App Store submission, GTM calendar, press kit, beta results |
| Key decisions | Soft vs hard launch. Pricing finalization. Country rollout order. |
| Risks | App Store rejection (budget 2 weeks). Server overload (auto-scale). |
| Next prompts | "Generate App Store description with keywords." "Create 30-day push notification plan." |

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
