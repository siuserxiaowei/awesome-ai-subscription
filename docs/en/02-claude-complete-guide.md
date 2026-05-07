# 02 · Complete Guide to Claude Subscriptions

English | [中文](../02-claude-complete-guide.md)

---

> Scope: Anthropic's Claude.ai web + iOS / Android + Console / API.
> Data as of: 2026-05. Claude Pro / Max tiers were restructured in April 2025; this guide reflects the current structure.

## Tier overview

Anthropic has two billing lines — Claude.ai consumer subscriptions and Console / API. They work very differently.

**Consumer subscriptions (Claude.ai)**

| Tier             | Price          | Target audience          | Key differences                                |
| ---------------- | -------------- | ------------------------ | ---------------------------------------------- |
| Free             | $0             | Trial                    | Limited Sonnet 4.x, no Opus, no Projects        |
| Pro              | $20/mo         | Individual paid          | Sonnet + Opus + Projects + 5x Free quota        |
| Max ($100)       | $100/mo        | Heavy individual / dev   | 5x Pro quota, priority access, more Claude Code |
| Max ($200)       | $200/mo        | Live in Claude all day   | 20x Pro quota, near-unlimited Opus, top priority|
| Team             | $30/seat (annual) | 5+ person teams       | All Pro features + shared Projects + admin     |
| Enterprise       | Contact sales  | Companies                | SSO, SCIM, SLA, custom quotas                   |

**API / Console**

Token-based pricing (input / output priced separately). No monthly subscription concept. Console provides org management, key rotation, and usage dashboards, but it's not a subscription product.

## Tier comparison

### Free vs Pro

| Dimension     | Free                    | Pro ($20)                            |
| ------------- | ----------------------- | ------------------------------------ |
| Main model    | Claude Sonnet 4.5       | Sonnet 4.5 + Opus 4.5 (limited)      |
| 5-hour window quota | ~10-25 short messages | ~45-100 messages + Opus sampling    |
| Projects      | Not available           | Available, up to 200k tokens of context per project |
| File uploads  | 5 per conversation      | 30 per conversation                  |
| Artifacts     | Limited                 | Full                                 |
| Computer Use (experimental) | Not available | Available                            |
| Claude Code   | Not available           | Available with usage cap             |

The core of Pro is **Projects** and **Opus access**. Projects let you attach a set of documents (a codebase, contracts, research material) as long-term memory for Claude. Multiple conversations within a project share that context. This is Claude's biggest single advantage over ChatGPT for long-document workflows.

### Max $100 vs Max $200 — which one

The split here gets asked a lot. Short answer: **only people running Claude Code (the CLI / IDE coding agent) hit the $100 ceiling.**

| Dimension                 | Max $100                | Max $200              |
| ------------------------- | ----------------------- | --------------------- |
| 5-hour window quota       | 5x Pro                  | 20x Pro               |
| Opus usage                | Priority, still capped  | Near-unlimited        |
| Claude Code coding quota  | High; daily coders may hit it | Near-unlimited  |
| Priority queue            | High                    | Highest (no peak queues) |
| Suited for                | Heavy writers + occasional Code | Full-day Claude Code users / agent developers |

Observed data:
- A user who treats Claude.ai as their primary writing tool can't burn through $100 in a month
- A developer using Claude Code as a daily IDE will hit the $100 cap in 8-15 days. $200 carries them through the month.
- Both tiers prioritize Opus, but $200 cuts queue time during Opus peak (Asia evenings) noticeably.

**Decision rule**: If you ran more than 200 Claude Code commands in the past 30 days, go straight to $200. Below 100, $100 is fine. Zero, just stay on Pro.

### Team / Enterprise

- **Team**: minimum 5 seats, $30/month or $25/month annual. Adds shared Projects, central billing, admin, stronger data isolation.
- **Enterprise**: contact sales. Typical floor 50-100 seats. Includes SSO, SCIM, audit logs, dedicated SLA, regional data residency.

## Console / API pricing

Not a subscription. Prepaid usage by token.

**Current pricing (2026-05)**:

| Model             | Input ($/M tokens) | Output ($/M tokens) | Context window |
| ----------------- | ------------------ | ------------------- | -------------- |
| Claude Haiku 4.5  | $1                 | $5                  | 200k           |
| Claude Sonnet 4.5 | $3                 | $15                 | 200k (1M beta for Pro users) |
| Claude Opus 4.5   | $15                | $75                 | 200k           |

Cost-reduction strategies:
- **Prompt Caching**: cache repeated prompt prefixes. Cache hits drop input cost to 1/10. Long system prompts and long-document workflows save 50-90%.
- **Batch API**: async batch processing, 50% off, returns within 24 hours.
- **Message Batches + Caching combined**: writing / summarization workloads can run at 1/4 the original cost.

**When to choose API over subscription?**

- Developers integrating Claude into their own apps
- Teams sharing one key across multiple users (subscriptions are bound to accounts)
- Highly variable monthly usage (1 hour one month, 100 hours the next — pay-as-you-go wins)
- Need 200k+ context (Sonnet 4.5's 1M beta is API-only)

**When is subscription better?**

- Personal daily use, no integration
- Steady 1-3 hours per day
- Want Projects, Artifacts, Computer Use — these only ship in Claude.ai
- Don't want to manage API keys or read token billing tables

Observed data: light users (30-90 min/day of conversation) save 3-10x on Pro vs API. Users below 30 min/day or 1-2 sessions/week save more on API.

## Subscribing from China

### Path A: Direct foreign credit card

Same logic as ChatGPT. Claude uses Stripe for payments. Stripe's risk model is slightly more permissive than OpenAI's — observed 50-70% approval for Chinese cards (vs 40-60% for OpenAI).

Watch out for:
- Claude account registration requires a non-China phone number for verification (Anthropic doesn't accept +86)
- Mainland China is outside Anthropic's supported regions. Even after a successful payment, Claude.ai rejects connections from a mainland IP.

### Path B: Apple App Store in-app purchase

Same as ChatGPT. iOS price is $25 (Apple's 30% cut). No foreign credit card needed, but 25% more expensive.

### Path C: Subscription proxy service

The most reliable path from China. A proxy provider logs in on your behalf and upgrades the account. Markup is typically 10-30 RMB/month over the official price.

Checklist for vetting a proxy: see [06 - Payment methods](./06-payment-methods.md#代充服务).

### Mainland China region restrictions

Anthropic explicitly does not support mainland China IPs accessing Claude.ai. Even with a paid account:
- A direct mainland connection returns 403
- You need a stable foreign exit node (US, Japan, Singapore all work)
- The exit IP can't flap (multiple countries in a short window triggers account-level risk controls)

## Claude vs ChatGPT — which to pick

Simplified decision:

- **Long-form writing (papers, reports, contract analysis)** → Claude Pro wins. 200k context + Projects is something ChatGPT Plus can't match.
- **Chat / daily / short code** → toss-up; comes down to taste. Claude is "smart and restrained." ChatGPT is "encyclopedic."
- **Image / video generation** → ChatGPT (DALL·E + Sora). Claude doesn't generate images.
- **Voice conversation** → ChatGPT (Advanced Voice is mature). Claude has no voice mode.
- **Heavy coding agent / CLI** → Claude. Claude Code is the industry benchmark, and Cursor uses Claude under the hood.
- **Enterprise / legal / long compliance documents** → Claude (more reliable on long-document comprehension).

Many heavy users subscribe to both: Plus + Claude Pro for $40/month covers nearly every use case.

## Refunds / cancellation

- Cancel: Settings → Account → Manage Plan → Cancel
- Refund: Anthropic offers a 14-day full refund as long as usage isn't "heavy." Email support@anthropic.com to request; 2-5 day response.
- Apple in-app refunds: reportaproblem.apple.com — handled by Apple, not Anthropic.

## Price history

| Date    | Event                                              |
| ------- | -------------------------------------------------- |
| 2023-09 | Claude Pro launches at $20                         |
| 2024-09 | Claude.ai introduces Projects                       |
| 2025-04 | Max $100 / $200 dual tier launched                 |
| 2025-08 | Claude 4 series released; Pro / Max prices held    |
| 2025-12 | Computer Use enters public beta; Claude Code added to Pro |
| 2026-02 | Sonnet 4.5 released with 1M token context (beta)   |

---

**Can't subscribe to Claude Pro / Max from China?** [payforgpt.com](https://payforgpt.com) is a Chinese AI subscription proxy serving users without direct overseas payment access. We've fulfilled thousands of Claude orders. Chinese-language support, card-key delivery, USDT / Alipay accepted. New accounts also welcome.

---

📘 [Read in Chinese (中文版)](../02-claude-complete-guide.md)
