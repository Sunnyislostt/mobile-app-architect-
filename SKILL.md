---
name: mobile-app-architect
description: "End-to-end mobile app creation framework from blueprint to launch. Covers product strategy, UX, architecture, backend, UI design, code scaffolding, QA audit, and GTM planning across 10 phases. Use when creating a new mobile app, rebuilding an existing one, or when user mentions any of the 10 prompts by number or name."
---

# Mobile App Architect — 10-Phase Framework

Generate every artifact for production mobile app: strategy docs, UX flows, architecture, backend schema, design system, starter code, audit, launch plan, complete program lead doc.

## Phases (sequential)

| # | Phase | Deliverable |
|---|-------|-------------|
| 1 | **App Blueprint** | Personas, pain points, value prop, MVP/v1/v2 features, user flow, monetization, risks |
| 2 | **App Structure** | Folders, screens, components, state mgmt, API layer, auth, nav, storage, error handling, analytics |
| 3 | **UX Flow** | Screen-by-screen plan, states, CTAs, microcopy, retention hooks |
| 4 | **PRD** | Overview, problem, goals, audience, features, edge cases, success metrics, roadmap |
| 5 | **Backend Logic** | DB schema, auth/roles, APIs, integrations, notifications, storage, payments, admin, rate limits |
| 6 | **UI Design System** | Colors, typography, spacing, buttons, inputs, cards, nav, icons, onboarding, premium direction |
| 7 | **Starter Code** | Setup, navigation, auth, home, API layer, components, state mgmt, mock data |
| 8 | **Brutal Audit** | Weak UX, confusing flows, retention risks, monetization errors, App Store risks, privacy, tech debt |
| 9 | **Launch Plan** | Pre-launch checklist, beta, onboarding, App Store, content, influencer, push, referral, retention |
| 10 | **Complete Lead** | Phases with deliverables, key decisions, risks, next prompts per phase |

## Workflow

1. **Ask user:** "Describe app idea: concept, target users, problem solved."
2. **Fill placeholders:** Replace `[APP NAME]`, `[TARGET USERS]`, `[PROBLEM]`, `[TECH STACK]`, `[STYLE]`, `[FEATURES]`, `[BRAND STYLE]`, `[APP IDEA]` with user input.
3. **Run phases sequentially.** Each phase builds on prior outputs. Use prompt templates from [REFERENCE.md](REFERENCE.md).
4. **Phase gate:** Present output → user approves → next phase. No skip.
5. **Save outputs** to `docs/mobile-app-architect/<app-name>/<phase-number>-<phase-name>.md`.

## Principles

- **Phase gates:** Must approve each phase. No exceptions.
- **Replace all placeholders:** Fill every bracket before generating.
- **YAGNI:** MVP scope only. V2 documented, not built.
- **Platform-aware:** Prompts adapt to iOS/Android/Flutter/React Native.
- **Risks first:** Surface product, UX, tech risks each phase.

## Anti-Patterns

- No code before phases 1-6 complete (strategy → design).
- No merge multiple phases into one output.
- No skip Brutal Audit (phase 8) before Launch Plan (phase 9).
- No generic prompts — fill brackets with user-specific details.

## Files

- [REFERENCE.md](REFERENCE.md) — Full prompt templates per phase
- [EXAMPLES.md](EXAMPLES.md) — Worked example
