# Mobile App Architect — Worked Example

## App: MealMate — Meal Planning for Busy Professionals

**Target users:** Busy professionals 25-40, eat healthier, lack meal planning time.
**Problem:** 70% professionals skip meal planning → unhealthy takeout.
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
| Sarah | 29 | PM | Eat healthy without 2h/week planning | Forgets, orders takeout | Notion user |
| Mike | 34 | Engineer | Cook 3x/week, save money | Recipe research too slow | TikTok recipes |
| Priya | 41 | Doctor | Family meals, dietary restrictions | Kids picky, husband GF | Meal preps Sundays |

## Value Proposition
**"MealMate plans dinners in 2 min. Never ask 'what's for dinner?' again."**
1. AI weekly plans from 5 preferences
2. Auto grocery list by store aisle
3. One-tap ingredient delivery (Instacart)

## Features
| Scope | Feature | Description |
|-------|---------|-------------|
| MVP | Onboarding | Diet pref, allergies, prep time, family size |
| MVP | Weekly plan | AI generates 7 dinners |
| MVP | Grocery list | Consolidated by aisle, checkable |
| MVP | Recipe detail | Ingredients, steps, photo, cook time |
| V1 | Delivery | One-tap Instacart / Amazon Fresh |
| V1 | Leftover repurpose | Next-day leftover suggestions |
| V2 | Social share | Share plans, family groups |
| V2 | Barcode scanner | Scan pantry → auto-exclude |

## Monetization
**Model:** Freemium (3 free plans, then $4.99/mo or $39.99/yr)
**Conversion:** After 3rd plan, "Unlock unlimited + delivery"

## Risks
| Risk | Likelihood | Mitigation |
|------|------------|------------|
| Users don't cook with plan | Medium | 15-min meals, no-cook options |
| AI generates bad meals | High | Start curated + manual, AI later |
| Churn after week 1 | High | Push: "Your Saturday plan" + Sunday prep reminder |
```

---

## Phase 3: UX Flow — Sample

```markdown
# UX Flow: MealMate

## Splash
| Element | Detail |
|---------|--------|
| Objective | Brand intro, check cached plan |
| UI | Logo + "Your meals, planned." |
| Loading | Skeleton shimmer |
| Error | "Can't load plan" + retry |
| CTA | Auto-transition to Home or Onboarding |
| Microcopy | "Loading your week..." |

## Home (Weekly Plan)
| Element | Detail |
|---------|--------|
| Objective | See this week's meals |
| Main action | Tap day → recipe detail |
| UI | Horizontal day strip, vertical meal cards |
| Loading | 7 skeleton cards with shimmer |
| Empty | "No plan yet" → "Build first week" CTA |
| Error | Toast + pull-to-retry |
| CTA | "Plan This Week" FAB |
| Retention | Sunday push: "Meal plan ready" |
```

---

## Phase 5: Backend — DB Schema

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
| GET | /plans/{id}/grocery | Consolidated grocery list |
| POST | /plans/{id}/swap/{day} | Swap day's meal |
| GET | /recipes/search | Search recipes |
```

---

## Phase 8: Brutal Audit — Findings

```markdown
| # | Category | Finding | Rating | Fix |
|---|----------|---------|--------|-----|
| 1 | UX | Diet prefs required before seeing value | Critical | Show sample plan first |
| 2 | Retention | No reason to reopen after plan generated | Critical | Add "Today's dinner" widget, timer, prep checklist |
| 3 | Monetization | Paywall on plan 4 — habit not formed | Major | Move to plan 7, email before paywall |
| 4 | App Store | Screenshots show empty states, not food | Major | Add food photography |
| 5 | Privacy | Contact permission without context | Minor | Explain before prompt |
```

---

## Phase 10: Complete Lead — Timeline

```markdown
| Phase | Timeline | Key Decision |
|-------|----------|-------------|
| Strategy | Week 1 | Focus singles/couples, skip family plan |
| UX | Week 2 | Tab bar: Plan | Groceries | Recipes | Profile |
| Architecture | Week 3 | Flutter + Firebase (serverless MVP) |
| Backend | Week 4-7 | Firestore, Cloud Functions for plan gen |
| Design | Week 4-6 | Warm earth tones, rounded cards, food photography |
| Code | Week 5-11 | Riverpod, GoRouter |
| QA | Week 12 | Load test AI gen, 100+ recipe combos |
| Launch | Week 13-14 | Beta 500 → iterate → public launch |
```
