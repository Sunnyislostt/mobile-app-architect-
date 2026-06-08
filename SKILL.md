---
name: mobile-app-architect
description: "End-to-end mobile app creation framework from blueprint to launch. Covers product strategy, UX, architecture, backend, UI design, code scaffolding, QA audit, and GTM planning across 10 phases. Use when creating a new mobile app, rebuilding an existing one, or when user mentions any of the 10 prompts by number or name."
---

# Mobile App Architect — 10-Phase Framework

Generate every artifact needed for a production mobile app: strategy docs, UX flows, architecture, backend schema, design system, starter code, audit, launch plan, and a complete program lead doc.

## Phases (run in order)

| # | Phase | Status | Deliverable |
|---|-------|--------|-------------|
| 1 | **App Blueprint** | Product Strategy | Personas, pain points, value prop, MVP/v1/v2 features, user flow, monetization, risks |
| 2 | **App Structure** | Mobile Architecture | Folders, screens, components, state mgmt, API layer, auth, navigation, storage, error handling, analytics |
| 3 | **UX Flow** | UX Design | Screen-by-screen plan, states, CTAs, microcopy, retention hooks |
| 4 | **PRD** | Product Requirements | Overview, problem, goals, audience, features, edge cases, success metrics, roadmap |
| 5 | **Backend Logic** | Backend Architecture | DB schema, auth/roles, APIs, integrations, notifications, storage, payments, admin, rate limits |
| 6 | **UI Design System** | Visual Design | Colors, typography, spacing, buttons, inputs, cards, nav, icons, onboarding, premium direction |
| 7 | **Starter Code** | Code Scaffolding | Setup, navigation, auth, home, API layer, components, state mgmt, mock data |
| 8 | **Brutal Audit** | QA + Growth | Weak UX, confusing flows, retention risks, monetization errors, App Store risks, privacy, tech debt |
| 9 | **Launch Plan** | GTM Strategy | Pre-launch checklist, beta, onboarding, App Store, content, influencer, push, referral, retention |
| 10 | **Complete Lead** | Program Management | Phases with deliverables, key decisions, risks, next prompts per phase |

## Workflow

1. **Ask:** "What is your app idea? Describe the concept, target users, and problem it solves."
2. **Fill table:** Replace `[APP NAME]`, `[TARGET USERS]`, `[PROBLEM]`, `[TECHNOLOGY STACK]`, `[STYLE]`, `[FEATURES]`, `[BRAND STYLE]`, `[APP IDEA]` with user's inputs.
3. **Run phases sequentially.** Each phase builds on prior outputs. Use the full prompt templates from [REFERENCE.md](REFERENCE.md).
4. **Present each phase output** to the user for approval before moving to the next phase.
5. **Save outputs** to `docs/mobile-app-architect/<app-name>/<phase-number>-<phase-name>.md`.

## Key Principles

- **Phase gates:** Each phase must be approved before starting the next. Do not skip.
- **Replace all placeholders:** Every `[APP NAME]`, `[TARGET USERS]`, etc. must be filled before generating output.
- **YAGNI:** MVP scope only. V2 features are documented but not implemented.
- **Platform-aware:** The prompts adapt to iOS/Android/Flutter/React Native automatically.
- **Risks first:** Surface product, UX, and technology risks at each phase.

## Anti-Patterns

- Do NOT generate code before completing phases 1-6 (strategy → design).
- Do NOT combine multiple phases into one output.
- Do NOT skip the Brutal Audit (phase 8) before the Launch Plan (phase 9).
- Do NOT use generic prompts — always fill brackets with user-specific details.

See [REFERENCE.md](REFERENCE.md) for the full prompt templates and output structure for each phase.
See [EXAMPLES.md](EXAMPLES.md) for a complete worked example.
