# Mobile App Architect — Worked Example

## App: MealMate — Meal Planning for Busy Professionals

**Target users:** Busy professionals age 25-40 who want to eat healthier but lack time to plan meals.
**Problem:** 70% of professionals skip meal planning due to time constraints, leading to unhealthy takeout.
**Tech stack:** Flutter + Firebase + Stripe
**Style:** Minimalist, warm, editorial
**Brand style:** Earthy tones, sans-serif, approachable premium

---

## Phase 1: App Blueprint — Output

```markdown
# App Blueprint: MealMate

## Personas
| Name | Age | Role | Goals | Frustrations | Behavior |
|------|-----|------|-------|--------------|----------|
| Sarah | 29 | Product manager | Eat healthy without spending 2h/week planning | Forgets to plan, ends up ordering | Uses Notion for everything |
| Mike | 34 | Engineer | Cook 3x/week, save money | Recipe research takes too long | Scrolls TikTok for recipes |
| Priya | 41 | Doctor | Family meals, dietary restrictions | Kids are picky, husband is gluten-free | Meal preps Sundays |

## Value Proposition
**"MealMate plans your dinners in 2 minutes so you never have to ask 'what's for dinner?' again."**
1. AI-generated weekly plans from 5 preferences
2. Auto-generated grocery list by store aisle
3. One-tap ingredient delivery (Instacart integration)

## Features
| Scope | Feature | Description |
|-------|---------|-------------|
| MVP | Onboarding | Diet pref, allergies, prep time, family size |
| MVP | Weekly plan | AI generates 7 dinners from preferences |
| MVP | Grocery list | Consolidated by aisle, checkable |
| MVP | Recipe detail | Ingredients, steps, photo, cook time |
| V1 | Delivery integration | One-tap Instacart / Amazon Fresh order |
| V1 | Leftover repurpose | Suggests next-day use of leftovers |
| V2 | Social meal share | Share plans with friends, family groups |
| V2 | Barcode scanner | Scan pantry items → auto-exclude from plan |

## Monetization
**Model:** Freemium (3 free plans, then $4.99/mo or $39.99/yr)
**Conversion triggers:** After 3rd plan, "Unlock unlimited + delivery integration"

## Risks
| Risk | Likelihood | Mitigation |
|------|------------|------------|
| Users don't cook even with a plan | Medium | Add 15-min meals, no-cook options |
| AI generates bad meals | High | Start with curated + manual, add AI later |
| Churn after first week | High | Push notification: "Your Saturday plan" + Sunday prep reminder |
```

---

## Phase 3: UX Flow — Sample Screens

```markdown
# UX Flow: MealMate

## Splash
| Element | Detail |
|---------|--------|
| Objective | Brand intro, check cached plan |
| UI | Logo + "Your meals, planned." tagline |
| Loading | Skeleton shimmer for logo area |
| Error | "Can't load your plan" + retry button |
| CTA | Auto-transition to Home or Onboarding |
| Microcopy | "Loading your week..." |
| Retention | - |

## Home (Weekly Plan)
| Element | Detail |
|---------|--------|
| Objective | See this week's meals at a glance |
| Main action | Tap a day → recipe detail |
| UI | Horizontal day strip, vertical meal cards |
| Loading | 7 skeleton cards with shimmer |
| Empty | "No plan yet" → "Build your first week" CTA |
| Error | Toast: "Couldn't refresh plan" + pull-to-retry |
| CTA | "Plan This Week" floating button |
| Microcopy | "This week's dinners" / "Swipe to see all days" |
| Retention | Sunday push: "Your meal plan is ready" |
```

---

## Phase 5: Backend — DB Schema Sample

```markdown
# Backend: MealMate

## Tables
| Table | Key Columns |
|-------|-------------|
| users | id, email, name, diet_prefs[], allergies[], family_size, plan_id |
| weekly_plans | id, user_id, week_start, status (draft/active/completed) |
| meals | id, plan_id, day_of_week, recipe_id, is_custom |
| recipes | id, title, cook_time, ingredients[], steps[], photo_url |
| grocery_items | id, plan_id, ingredient, quantity, aisle, checked |

## Key APIs
| Method | Endpoint | Purpose |
|--------|----------|---------|
| POST | /plans/generate | AI generate weekly plan |
| GET | /plans/{id}/grocery | Get consolidated grocery list |
| POST | /plans/{id}/swap/{day} | Swap a day's meal |
| GET | /recipes/search | Search recipe database |
```

---

## Phase 8: Brutal Audit — Findings

```markdown
| # | Category | Finding | Rating | Fix |
|---|----------|---------|--------|-----|
| 1 | UX | Users must give diet prefs before seeing value | Critical | Let them see a sample plan first |
| 2 | Retention | No reason to open app after plan is generated | Critical | Add "Today's dinner" widget, cooking timer, prep checklist |
| 3 | Monetization | Paywall on plan 4 — users haven't built habit yet | Major | Move paywall to plan 7, add email reminder before paywall |
| 4 | App Store | Screenshots show empty states not meal photos | Major | Add food photography, remove empty mockups |
| 5 | Privacy | Requesting contacts for "share plan" without context | Minor | Explain why before permission prompt |
```

---

## Phase 10: Complete Lead — Timeline

```markdown
| Phase | Timeline | Key Decision |
|-------|----------|-------------|
| Strategy | Week 1 | Focus on singles/couples, skip family plan initially |
| UX | Week 2 | Tab bar: Plan | Groceries | Recipes | Profile |
| Architecture | Week 3 | Flutter + Firebase (serverless MVP) |
| Backend | Week 4-7 | Firestore schemas, Cloud Functions for plan generation |
| Design | Week 4-6 | Warm earth tones, rounded cards, food photography |
| Code | Week 5-11 | Riverpod state mgmt, GoRouter navigation |
| QA | Week 12 | Load test AI generation, test 100+ recipe combinations |
| Launch | Week 13-14 | Beta 500 users → iterate on plan quality → public launch |
```
```
