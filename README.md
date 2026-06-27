# Nutrition Coach — AI nutrition & macro tracking skill

A personalized AI nutrition coach built as a skill. Works for both men and women — with proper sex-based coaching built in, not bolted on. Logs food, tracks macros, learns your patterns, and remembers your data across conversations.

> Built after my own postpartum recomposition journey — a nutrition coach that actually understands training, breastfeeding, and real life.

## The story behind this

I've been athletic most of my life. Before getting pregnant I completed an Olympic-distance triathlon, ate clean, trained consistently. No meat for years. Never counted calories — just ate intuitively and it worked.

During pregnancy I kept moving. After giving birth I was back training by month two or three — swimming, running, cycling, gym, yoga. About five sessions a week.

Everyone told me breastfeeding would melt the weight off. It didn't. I was constantly hungry, the scale barely moved, and at some point I was actually gaining. Sleep got better. Body composition didn't.

A friend suggested something I'd never done before: count calories and create a small deficit. So I did what I always do — I went deep. I read through the research, looked at what actually applies to postpartum women (not just the generic fitness advice extrapolated from male studies), factored in breastfeeding, training load, and hormonal context. Then I built a set of instructions for Claude that reflected my specific situation.

It worked. Two months in, I'd lost 6 kg — slowly, sustainably, without starving or sacrificing milk supply. Energy came back. I started taking strength training seriously alongside the cardio, and for the first time postpartum I felt like myself again — not just surviving, actually building.

Friends started noticing. They asked what I was doing. I shared the Claude project, then decided to clean it up and make it available to anyone who needs it.

## What this is

A skill that turns your AI agent into a personal nutrition coach that:

- Runs onboarding to build your profile (goals, training, health context, macro targets)
- Remembers your patterns and preferences across conversations via `user.md`
- Logs every meal to `meals.jsonl` — a running food diary
- Flags safety issues: protein gaps, too-aggressive deficits, calorie floor
- Understands sex-based differences — men and women respond differently to training, nutrition, and deficits, and this coach accounts for that
- Goes deep on female physiology — not just "shrink it and pink it": cycle phases, postpartum, breastfeeding

It's not a generic macro calculator. It's a coach that learns you.

## Installation

Pick whichever fits your setup:

### Option 1: Claude Code

1. Open Claude Code in the terminal
2. Add marketplace:

```
/plugin marketplace add NataMoroz/nutrition-coach
```

3. Install the plugin:

```
/plugin install nutrition-coach@nutrition-coach
```

4. Select `Install for you (user scope)`

### Option 2: Claude Chat / Claude Cowork

Customize → Personal plugins → **+** → Create plugin → Add Marketplace → Add from a repository → enter `NataMoroz/nutrition-coach` → **Sync** → Nutrition Coach → Install

> **Note:** Claude Chat on mobile doesn't support skills yet. To use the skill on mobile, set it up in Claude Code on desktop, then run it from a remote session in Claude Code mobile.

### Option 3: Other coding agents

Run the following command in the terminal to install into any other coding agent. You will be able to choose your agent during setup.

```
npx skills add NataMoroz/nutrition-coach
```

## Usage

Once installed, just ask your agent to log a meal or check your day. The skill activates whenever you mention food.

```
I had oatmeal with banana and a coffee for breakfast
```

```
How am I doing on protein today?
```

You can also invoke the skill directly:

```
/nutrition-coach
```

You don't need to weigh anything or spell out exact grams — the coach estimates portions from your profile and usual habits, which is typically very close to the real numbers.

## Memory

The skill keeps memory in one global folder on your machine: `~/.nutrition-coach/`. It is separate from the skill and shared across all your conversations and across agents. The skill developer doesn't have access to it.

```
~/.nutrition-coach/
├── user.md         — your profile, targets, and learnings
└── meals.jsonl     — your food diary, structured for analysis (trends, averages, patterns)
```

## License

MIT
