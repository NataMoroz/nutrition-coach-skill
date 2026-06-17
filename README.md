# nutrition-coach (Claude Skill)

> Built this after my own postpartum recomp journey — a nutrition coach that actually understands training, breastfeeding, and real life. Works as a Claude Skill or a prompt for any LLM.

A personalized nutrition / body-recomposition coaching skill for Claude. Logs food, breaks down macros, tracks running daily totals, and flags safety issues.

## Install

### Option A — Project skill (recommended)

```bash
# Inside your project directory:
mkdir -p .claude/skills
curl -o .claude/skills/nutrition-coach.md \
  https://raw.githubusercontent.com/NataMoroz/nutrition-coach-skill/main/SKILL.md
```

Then open `.claude/skills/nutrition-coach.md` and fill in every `{{PLACEHOLDER}}`.

### Option B — User-level skill (available in all your projects)

```bash
mkdir -p ~/.claude/skills
curl -o ~/.claude/skills/nutrition-coach.md \
  https://raw.githubusercontent.com/NataMoroz/nutrition-coach-skill/main/SKILL.md
```

Fill in placeholders, then the skill is ready everywhere.

### Option C — Clone and copy manually

```bash
git clone https://github.com/NataMoroz/nutrition-coach-skill.git
cp nutrition-coach-skill/SKILL.md .claude/skills/nutrition-coach.md
# (or ~/.claude/skills/nutrition-coach.md for user-level)
```

> **Verify it loaded:** run `/skills` inside Claude Code — `nutrition-coach` should appear in the list.

## Customize

Open the installed `nutrition-coach.md` and replace every `{{PLACEHOLDER}}` with your data:

| Placeholder | What to put |
|---|---|
| `{{NAME}}` | Person's name |
| `{{GOAL}}` / `{{GOAL_WEIGHT}}` | Main goal and target weight |
| `{{AGE}}` `{{CURRENT_WEIGHT}}` `{{HEIGHT}}` | Basic profile |
| `{{BACKGROUND}}` `{{SESSIONS_PER_WEEK}}` `{{ACTIVITY_BREAKDOWN}}` | Training info |
| `{{HEALTH_NOTES}}` | Allergies, conditions, foods to avoid |
| `{{RESTING_KCAL}}` `{{ACTIVE_KCAL}}` `{{TDEE}}` | From a watch/tracker monthly average |
| `{{TARGET_KCAL}}` `{{DEFICIT}}` `{{FLOOR_KCAL}}` | Calorie targets |
| `{{PROTEIN}}` `{{FAT}}` `{{CARBS}}` `{{FAT_FLOOR}}` | Macro targets in grams |
| `{{DEFICIT_RANGE}}` `{{EXPECTED_LOSS}}` | Deficit range and expected fat loss/month |
| `{{KEY_MICROS}}` | Micronutrients to watch (fiber, omega-3, etc.) |
| `{{EXTRA_RULE}}` | Any condition-specific safety rule (delete line if none) |
| `{{OPTIONAL_TAG}}` | Extra emoji tag for special meals (delete line if none) |
| `{{LANGUAGE}}` | Language for responses (e.g. English, Ukrainian) |

## Quick macro math (recomp, male, moderate activity)

- **Protein:** ~1.8–2.2 g/kg body weight
- **Fat:** 0.6–1.0 g/kg (don't go below ~0.6 g/kg for hormones)
- **Carbs:** fill the remaining calories
- **Deficit:** 300–500 kcal for recomposition (moderate beats aggressive)

Example for an 80 kg male, TDEE ~2 700:
target ~2 300 kcal · protein ~160 g · fat ~70 g · carbs ~260 g.

## How it works

Once installed, the skill activates automatically when you log food or ask nutrition questions — no slash command needed. Just describe what you ate and Claude will break down macros, update running daily totals, and flag any safety issues against your personal targets.

## Files

```
nutrition-coach-skill/
├── SKILL.md   # the skill itself — copy this to your .claude/skills/ folder
└── README.md  # this file
```

## License

MIT
