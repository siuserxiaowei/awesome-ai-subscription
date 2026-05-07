# 04 · Complete Guide to Grok Subscriptions

English | [中文](../04-grok-complete-guide.md)

---

> Scope: xAI's Grok web / X integration / xAI API.
> Data as of: 2026-05. Grok's tier structure was reworked twice in 2024-2025. This guide is based on the current "Premium / Premium+ / SuperGrok / xAI API" four-tier structure.

## Tier overview

xAI's pricing is unique — Grok is deeply bundled with X (formerly Twitter). Subscribing to Grok almost always also gives you X Premium features.

| Tier         | Price (USD)               | Key features                                                  | Includes X subscription   |
| ------------ | ------------------------- | ------------------------------------------------------------- | ------------------------- |
| Free         | $0                        | Limited Grok 4 (~10-15 messages/day), basic image generation  | No (X account required, but X is free) |
| Premium      | $8 (web annual) / $11/mo  | Full Grok 4 + X Premium features (no ads, long posts, etc.)   | Yes (X Premium)           |
| Premium+     | $40/month                 | Advanced Grok 4 + Reasoning + Voice + X Premium+ (full ad removal, max distribution) | Yes (X Premium+) |
| SuperGrok    | $300/month                | Power users, highest quotas, top-priority access              | Yes                       |
| xAI API      | Pay per token             | Programmatic access to Grok 4                                 | No                        |

> All X / Grok subscriptions on X.com bill through Stripe. Apple App Store works too but takes 30%.

## Real cost of Premium ($8)

X advertises Premium as "$8/month," but read the fine print:

- $8 = annual price divided by 12; you actually pay $84/year upfront
- Monthly is $11/month
- iOS in-app: web $8 → iOS $11 (Apple cut)
- iOS annual: $112/year

Real-world combos:
- Cheapest: $84/year on web — works out to $7/month
- Most common: $11/month web (most people don't want to lock in a year)

## Premium vs Premium+ — what does the extra $32 buy you

| Dimension              | Premium ($8/mo annual)   | Premium+ ($40/mo)              |
| ---------------------- | ------------------------ | ------------------------------ |
| Grok 4 usage           | Medium (~50-80 msg/day)  | High (near-unlimited)          |
| Grok Reasoning (deep think) | Limited             | Near-unlimited                 |
| Grok Voice             | Basic                    | Full, on par with ChatGPT Advanced Voice |
| Grok Imagine (video)   | Basic                    | High quota, 1080p output        |
| X ad removal           | Timeline ads removed     | Fully ad-free (including replies) |
| Content distribution weight | High                | Highest (For You priority)     |
| Grok post analysis / live news | Limited           | Full (analyze any post directly)|
| Verified badge         | Auto                     | Auto + high priority            |

**Premium+ fits**:
- X power users (post and lurk daily)
- People who want Grok 4's voice / video features
- Content creators who care about X distribution

**Premium fits**:
- People who just want Grok 4 for chat / writing
- Casual X users (ad removal is enough)
- Don't care about voice / video

## SuperGrok ($300) — who buys this

xAI's premium tier launched in 2025, positioned similarly to ChatGPT Pro:

- Very high Grok 4 / Grok 4 Heavy quotas
- Multi-model parallel runs (same prompt across multiple models, then voted)
- Top-priority GPU queue, no peak waits
- Early access to new models (next-gen Grok internal beta)

Real-world target users: professional researchers, AI companies running internal benchmarks, xAI superfans. Most people don't need it.

## xAI API

Token-based pricing similar to OpenAI / Anthropic. Current pricing:

| Model            | Input ($/M tokens) | Output ($/M tokens) | Context window |
| ---------------- | ------------------ | ------------------- | -------------- |
| grok-4           | $3                 | $15                 | 256k           |
| grok-4-mini      | $0.30              | $1                  | 256k           |
| grok-4-heavy     | $5                 | $25                 | 256k           |

Notes:
- Pricing is mid-pack, on par with Sonnet 4.5
- 256k context window — longer than Claude or GPT
- Real-time X data access (Grok can query live X content) is an API-exclusive capability
- Good fit for news / live-event analysis applications

## Grok vs ChatGPT / Claude

Grok's core differentiation:

1. **Real-time** — Reads what's happening on X right now. News-style Q&A is hours to days ahead of Plus / Claude.
2. **Tone** — Default style is more "willing to take a position." Less hedged on political / controversial topics than ChatGPT.
3. **Deep X integration** — X post analysis and live news analysis are killer features
4. **Cheap** — Premium at $8 is the cheapest mainstream AI subscription (and includes X Premium)

**When to choose Grok Premium over ChatGPT Plus**:

- X power users (1+ hour/day on X). Premium = X Premium membership + full Grok 4. $8 is a steal.
- News / live-event analysis (journalists, researchers, market analysts)
- Prefer less "politically correct" response style

**When not to**:

- Non-X users (half of Premium's value is X member features)
- Primary coding (Grok 4's coding ability lags Claude / GPT)
- Need stable image / video generation (Grok Imagine improves fast but stability lags DALL·E / Veo)

## Subscribing from China

### Path A: X web + foreign credit card

Simplest path. Requires a foreign card and access to X (X is blocked in mainland China). Stripe-powered, approval rate similar to OpenAI (40-60%).

### Path B: Apple ID in-app

Use a US / HK Apple ID, subscribe in the X iOS app. Premium $11, Premium+ $44 (Apple markup).

### Path C: Subscription proxy service

Most common path from China. Proxy logs into your X account and upgrades the subscription. Cheap (because Grok itself is cheap) — Premium runs ~80-100 RMB/month.

Notes:
- You need your own X account (non-Chinese real-name verified). The proxy only handles the upgrade.
- Some proxies offer "X account + subscription" bundles for 150-200 RMB

### Mainland China region restrictions

X.com is fully blocked in mainland China. You need a stable foreign exit node throughout. Grok web (grok.com) is similarly restricted.

## Grok data training / privacy

xAI's privacy stance is weaker than OpenAI / Anthropic:

- Public X posts are used by default to train Grok (since 2024-09)
- DMs and private content reportedly aren't trained on, but users can't opt out
- Premium / Premium+ users can disable "use my data to train Grok" in settings

If your X account contains commercially sensitive material, unreleased content, or client conversations:
- Turn off the training toggle
- Don't paste sensitive info into Grok
- Use the xAI API instead (API doesn't train by default)

## Price history

| Date    | Event                                                  |
| ------- | ------------------------------------------------------ |
| 2023-12 | Grok 1 available only to X Premium+                    |
| 2024-04 | Grok 1.5 + standalone Grok subscription launched       |
| 2024-12 | Premium dropped to $8 (annual), merged with X subscription |
| 2025-07 | Grok 4 released; SuperGrok $300 tier launched          |
| 2025-12 | Grok Imagine video generation launched                 |

---

**Stuck paying for Grok Premium / Premium+ from China?** [payforgpt.com](https://payforgpt.com) is a Chinese AI subscription proxy serving users without direct overseas payment access. X / Grok subscription delivery, USDT / Alipay / WeChat Pay accepted.

---

📘 [Read in Chinese (中文版)](../04-grok-complete-guide.md)
