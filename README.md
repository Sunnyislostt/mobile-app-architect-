# Mobile App Architect — 10-Phase Framework

Ship production mobile apps from idea to launch. Covers strategy, UX, architecture, backend, design, code, QA, and GTM.

## What It Is

Structured framework with 10 sequential phases. Each phase produces concrete artifact (blueprint doc, UX flow, PRD, backend schema, design system, starter code, audit report, launch plan). Phase-gate workflow: generate → user approves → next phase.

## 10 Phases

| # | Phase | Output |
|---|-------|--------|
| 1 | App Blueprint | Personas, pain points, value prop, MVP/v1/v2 features, monetization, risks |
| 2 | App Structure | Folder tree, screens, components, state mgmt, API layer, auth, nav, storage, error handling, analytics |
| 3 | UX Flow | Screen-by-screen plan with states, CTAs, microcopy, retention hooks |
| 4 | PRD | Product overview, goals, audience, features, edge cases, success metrics, roadmap |
| 5 | Backend Logic | DB schema, auth/roles, APIs, integrations, notifications, payments, admin, rate limits, security |
| 6 | UI Design System | Colors, typography, spacing, buttons, inputs, cards, nav, icons, onboarding, premium direction |
| 7 | Starter Code | Project setup, navigation, auth, home screen, API layer, components, state mgmt, mock data |
| 8 | Brutal Audit | Weak UX, confusing flows, retention risks, monetization errors, App Store risks, privacy, tech debt |
| 9 | Launch Plan | Pre-launch checklist, beta, App Store strategy, content, influencer, push, referral, 30-day retention |
| 10 | Complete Lead | Phase map with deliverables, key decisions, risks, next prompts, timeline |

## How It Works

1. **User provides app idea** — concept, target users, problem, tech stack
2. **Agent runs phases in order** — uses prompt templates from REFERENCE.md with placeholders filled
3. **Phase gate** — user approves each phase output before next phase starts
4. **Outputs saved** to `docs/mobile-app-architect/<app-name>/<phase-number>-<phase-name>.md`

## Directory Structure

```
mobile-app-architect/
├── SKILL.md       # Agent-facing workflow instructions
├── REFERENCE.md   # Full prompt + output templates for all 10 phases
└── EXAMPLES.md    # MealMate worked example
```

## Usage

Invoke skill: `name: "mobile-app-architect"`

Agent will prompt for app details, then walk through all 10 phases sequentially with approval at each gate.

## Design Principles

- **Phase gates** — no skip. Each phase approved before next.
- **YAGNI** — MVP scope. V2 documented, not built.
- **Platform-aware** — prompts adapt to iOS/Android/Flutter/React Native.
- **Risks first** — product, UX, tech risks surfaced each phase.
- **Caveman** — instructions written full caveman (compressed, no filler). All technical substance preserved.
