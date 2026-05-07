# awesome-ai-subscription · A complete guide to AI subscriptions

[English] | [中文](README.md)

---

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![GitHub stars](https://img.shields.io/github/stars/siuserxiaowei/awesome-ai-subscription?style=social)](https://github.com/siuserxiaowei/awesome-ai-subscription/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/siuserxiaowei/awesome-ai-subscription?style=social)](https://github.com/siuserxiaowei/awesome-ai-subscription/network/members)
[![Last commit](https://img.shields.io/github/last-commit/siuserxiaowei/awesome-ai-subscription)](https://github.com/siuserxiaowei/awesome-ai-subscription/commits/main)
[![License](https://img.shields.io/github/license/siuserxiaowei/awesome-ai-subscription)](./LICENSE)

> A continuously maintained guide to AI subscriptions — covering ChatGPT, Claude, Gemini, Grok, Cursor, Codex tiers, payment methods, fraud prevention, card-key activation, and use-case-driven combos. All tables / verified data, no AI fluff.

Originally written in Chinese for users navigating overseas AI subscription payments from inside China; now also available in English. Both versions cover the same material — pricing matrices, payment-route mechanics, risk-control patterns, and reseller economics — with examples kept verbatim where Chinese-context detail matters (Chinese cards, Apple ID flows, etc.) and annotated for English readers.

---

## Why this exists

Paying for overseas AI subscriptions from inside China is uniquely painful. Foreign credit cards get declined for "high-risk merchant", Apple ID gift-card balances get frozen mid-redemption, residential IPs trigger fraud rules at OpenAI/Anthropic, and the gray-market reseller scene mixes legitimate payment proxies with outright scams. There is no clean Western equivalent — Stripe just works in San Francisco, but a Beijing developer trying to pay $20/month for ChatGPT Plus may go through three rejected cards, a Hong Kong virtual card, then a USDT-funded reseller before the subscription activates.

This repo collects what works in 2026. Every number is verified against current official pricing pages, every payment route is tested by someone who actually pushed the charge through, and every "this gets your account banned" warning maps to a real banned account. We update on every price change and every new failure mode that hits our support inbox.

---

## Quick Links · common questions

- [How much is ChatGPT Plus? Is Pro worth $200/month?](./docs/en/01-chatgpt-complete-guide.md#tiers-and-pricing)
- [How do I subscribe to Claude Pro? Max $100 vs $200 — what's the gap?](./docs/en/02-claude-complete-guide.md#tier-comparison)
- [Can a Chinese-issued card pay directly? Why does it usually get declined?](./docs/en/06-payment-methods.md#foreign--chinese-credit-cards)
- [Are payment proxies safe? How do I pick one without getting scammed?](./docs/en/06-payment-methods.md#subscription-proxy-services)
- [On a $20 / $50 / $200 monthly budget, which combos work?](./docs/en/07-pricing-comparison.md#recommended-bundles-by-budget)
- [Payment failed? Gift card frozen? Fixes inside.](./docs/en/08-troubleshooting.md)

---

## Table of contents

### Core subscription guides

| #   | Document                                                                | One-line summary                                                              |
| --- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| 01  | [ChatGPT complete guide](./docs/en/01-chatgpt-complete-guide.md)        | Free / Plus $20 / Pro $200 / Team / Enterprise — every tier + how to pay from China |
| 02  | [Claude complete guide](./docs/en/02-claude-complete-guide.md)          | Free / Pro $20 / Max $100 / Max $200 + Console API — when to pick which       |
| 03  | [Gemini Advanced guide](./docs/en/03-gemini-complete-guide.md)          | Google AI Pro $19.99 / AI Ultra — and how it compares to ChatGPT Plus         |
| 04  | [Grok Premium guide](./docs/en/04-grok-complete-guide.md)               | Premium $8 / Premium+ $40 / xAI API + the X subscription bundling             |
| 05  | [Cursor / Codex coding subscriptions](./docs/en/05-cursor-codex-guide.md) | Cursor Pro $20 / Business $40 / OpenAI Codex — for working programmers       |

### Payment / selection / troubleshooting

| #   | Document                                                                       | One-line summary                                                          |
| --- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| 06  | [Payment methods comparison](./docs/en/06-payment-methods.md)                  | Foreign card / Apple Pay / gift card / virtual card / USDT / proxy — 7 routes |
| 07  | [Pricing matrix + value-for-money](./docs/en/07-pricing-comparison.md)         | One big table comparing all vendors, plus combos for $20/$50/$100/$200 budgets |
| 08  | [Failure / risk-control / card-key troubleshooting](./docs/en/08-troubleshooting.md) | 10+ real scenarios, each with a 2–3 step fix                       |
| 09  | [Pick by use case (programmer / student / writer / researcher / casual)](./docs/en/09-recommendation-by-use-case.md) | Monthly budget + recommended combos for 5 user types |
| 10  | [Tracking policy changes](./docs/en/10-stay-updated.md)                        | Official status / changelog / newsletter / Discord lists for every vendor |

> Each English page links back to its Chinese counterpart at the top.

---

## Subscription landscape at a glance

| Service                  | Monthly (USD) | Highlights                                                       | Best for                            | China-payment difficulty |
| ------------------------ | ------------- | ---------------------------------------------------------------- | ----------------------------------- | ------------------------ |
| ChatGPT Plus             | $20           | GPT-5 / o-series reasoning / advanced voice / DALL·E / Code Interpreter | Casual users, writing, light coding | Medium                   |
| ChatGPT Pro              | $200          | Unlimited GPT-5 Pro / o3-pro heavy reasoning / Sora priority     | Heavy researchers, long-chain reasoning | High                  |
| Claude Pro               | $20           | Claude Sonnet/Opus + Projects + 5x usage                         | Writing, long-document analysis, coding | Medium                |
| Claude Max ($100)        | $100          | 5x Pro usage, priority on new models, Claude Code quota boost    | Heavy long-context, agent dev       | High                     |
| Claude Max ($200)        | $200          | 20x Pro usage, top priority, Claude Code near-unthrottled        | Heavy agent / enterprise coding     | High                     |
| Gemini Advanced (AI Pro) | $19.99        | Gemini 2.5 Pro + 2TB Drive + Workspace + Veo video gen           | Google power users, video creators  | Medium                   |
| Grok Premium             | $8            | Grok 4 + X premium features (no ads, long posts, etc.)           | X power users, real-time news       | Low–medium               |
| Cursor Pro               | $20           | Unlimited Tab completion + 500 advanced requests / month         | Programmers in their daily editor   | Medium                   |

> Prices reference official US pricing as of 2026-05. Vendors re-price often; for live numbers see [07-pricing-comparison](./docs/07-pricing-comparison.md).

---

## How to use this guide

- **First time looking at AI subscriptions** → start at [09-pick by use case](./docs/en/09-recommendation-by-use-case.md) and find your archetype.
- **Already know what to buy, stuck at checkout** → [06-payment methods](./docs/en/06-payment-methods.md) + [08-troubleshooting](./docs/en/08-troubleshooting.md).
- **Tight budget, want max value** → [07-pricing matrix](./docs/en/07-pricing-comparison.md) for budget combos.
- **Tracking long-term policy changes** → [10-stay updated](./docs/en/10-stay-updated.md) for official changelogs and signal sources.

---

## Contributing

Spotted an error, a price change, a new tier, or a new payment route? PRs welcome. Skim [CONTRIBUTING.md](./CONTRIBUTING.md) — 30 seconds and you're in.

Most-wanted contributions:
- Price updates (every vendor re-prices 1–2 times a year)
- Country/region availability changes (e.g., Gemini opening or closing in a region)
- First-hand testing of new payment routes
- New risk-control trigger scenarios

Not accepted: ad-driven posts, unverified second-hand info, AI-spun content.

## License

[MIT](./LICENSE) © 2026 siuserxiaowei

---

## About the maintainers

Maintained by the team behind [payforgpt.com](https://payforgpt.com) — a Chinese-language AI subscription proxy serving users who can't pay overseas directly. We run into every payment edge case daily, so we open-source the playbook. If you'd rather skip the DIY routing of foreign cards / gift cards / virtual cards entirely, we offer Alipay / WeChat Pay / USDT checkout with auto-delivered card keys; ~90% of orders complete within 5 minutes.

No hard sell — read the guide first, decide later.
