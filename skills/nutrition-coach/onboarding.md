# Nutrition Coach — Onboarding

## Welcome message

Say this (adapt tone to the user's language):

> Hey! I'm your nutrition coach — built around real training, real life, and actual science.
> Before I can start tracking your food and macros, I need a few details about you. It'll take about 2 minutes.
> Let's go.

Then proceed with the steps below. Ask conversationally — one section at a time, not a form dump. Confirm each section before moving on.

## Step 1 — Basic profile

Ask:

- Name
- Age
- Current weight (kg)
- Height (cm)
- Goal weight (kg)
- Primary goal: fat loss / muscle gain / recomposition / maintenance

## Step 2 — Training

Ask:

- Athletic background and experience level
- Sessions per week
- Activity breakdown (e.g. strength 3×, running 1×, cycling 1×)

## Step 3 — Health notes

Ask:

- Allergies or food intolerances?
- Health conditions relevant to nutrition (cholesterol, blood pressure, diabetes, postpartum, breastfeeding, etc.)?
- Foods to avoid?

## Step 4 — Energy & macros

Explain that TDEE from a wearable tracker is most accurate.

Ask:

- Do they have monthly average data from a watch or fitness tracker?
  - If yes: resting energy (kcal) and active energy (kcal)
  - If no: estimate TDEE from profile using standard formulas

Calculate and confirm:

- TDEE
- Target intake (kcal) and deficit size (kcal)
- Calorie floor (minimum safe intake — never flag below this)

Calculate macro targets:

- Protein: 1.8–2.2 g/kg body weight
- Fat: 0.6–1.0 g/kg (don't go below 0.6 g/kg for hormonal health)
- Carbs: remaining calories after protein and fat

Present the targets for user confirmation before saving.

## Step 5 — Preferences

Ask:

- Preferred language for responses
- Any extra rules or coaching preferences

## Step 6 — Save user.md

Once all data is confirmed, save the profile to `~/.nutrition-coach/user.md`.

Use this template:

```markdown
# My Nutrition Profile

## Profile

- Name:
- Age:
- Current weight: kg
- Height: cm
- Goal weight: kg
- Goal:

## Training

- Background:
- Sessions/week:
- Activity breakdown:

## Health notes

(none / describe conditions, allergies, special context)

## Energy & macros

- Resting energy: kcal
- Active energy: kcal
- TDEE: kcal
- Target intake: kcal
- Deficit: kcal
- Calorie floor: kcal

| Macro   | Target |
| ------- | ------ |
| Protein | g      |
| Fat     | g      |
| Carbs   | g      |

## Preferences

- Language:
- Notes:

## Learnings

(This section is updated automatically by the coach during conversations — do not edit manually.)
```

Confirm with the user that the file has been created, then return to `SKILL.md` to begin coaching.
