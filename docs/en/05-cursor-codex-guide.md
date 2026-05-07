# 05 · Cursor / Codex Coding Subscription Guide

English | [中文](../05-cursor-codex-guide.md)

---

> Scope: All Cursor IDE tiers + OpenAI Codex (2025 relaunch) + Claude Code (briefly; full coverage in 02-claude).
> Data as of: 2026-05. Cursor pricing changed twice in 2025; this guide reflects the latest.

## Coding AI subscription landscape

Major players as of 2026-05:

| Tool          | Form                  | Entry tier    | Key characteristics                     |
| ------------- | --------------------- | ------------- | --------------------------------------- |
| Cursor        | Standalone IDE (VS Code fork) | $20    | Full-IDE AI integration, multi-model    |
| GitHub Copilot| VS Code extension     | $10           | Microsoft / OpenAI ecosystem, deep GitHub integration |
| Claude Code   | CLI + IDE plugin      | Included in Claude Pro / Max | CLI agent, Sonnet / Opus driven |
| OpenAI Codex  | CLI + web             | Included in ChatGPT Plus / Pro | OpenAI's own agent, GPT-5 Pro driven |
| Continue / Cline / Aider | Open-source plugins | Bring your own API key | Fully self-controlled, good for custom workflows |
| Windsurf      | Standalone IDE        | $10           | Cursor's main competitor, "Cascade Flow" model |

This guide focuses on Cursor and Codex — the products with their own subscription fees.

## Cursor tiers

| Tier          | Price (USD)             | Key differences                                            |
| ------------- | ----------------------- | ---------------------------------------------------------- |
| Hobby (Free)  | $0                      | 2-week Pro trial, limited Tab completions, ~50 Slow requests/month |
| Pro           | $20/mo / $16/mo annual  | Unlimited Tab + unlimited Slow Pro Agent + 500 Fast premium requests |
| Pro+          | $40/mo                  | Pro + 1500 Fast requests + priority speed                  |
| Ultra         | $200/mo                 | Near-unlimited Fast, top-priority model access, no Agent cap |
| Business      | $40/seat/mo             | Pro + team admin + SSO + privacy guarantee (no training on data) |
| Enterprise    | Contact sales           | SSO / SCIM / audit / custom quotas                          |

**Fast vs Slow requests**: Cursor uses a credit system. Fast requests hit models directly with instant response. Slow requests queue and may wait tens of seconds at peak. Pro gives you 500 Fast/month, then unlimited Slow.

**How long does Pro last?**:
- Heavy daily coding (4-6 hours/day): 500 Fast burns out in ~2 weeks; second half on Slow with occasional friction
- Medium (1-2 hours/day): Fast lasts the full month
- Occasional (a few times a week): never runs out of Fast

## Cursor Pro vs Pro+ vs Ultra

Quick decision:

- **Pro $20**: Enough for most. Heavy users wait a few seconds on Slow in the second half — usually acceptable.
- **Pro+ $40**: 6+ coding hours per day, won't tolerate Slow queues, frequent Claude Opus or GPT-5 Pro use
- **Ultra $200**: Professional agent developers running many long tasks per day (Composer Agent / multi-step execution)

Pragmatic recommendation: **start on Pro, upgrade only when you hit the cap**. Most people never need to.

## Cursor vs GitHub Copilot

Copilot is now $10/month — half the price. But the feature gap is widening:

| Dimension           | Cursor Pro $20                   | Copilot Pro $10                        |
| ------------------- | -------------------------------- | -------------------------------------- |
| Model selection     | Claude Sonnet/Opus, GPT-5, Gemini 2.5 Pro, etc. | Mostly GPT-5 / Claude Sonnet, fewer switches |
| Agent capability    | Composer multi-step execution / large refactors | Workspace agent, medium               |
| Tab completion speed| Extremely fast (Cursor's own model) | Fast                                  |
| Editor experience   | Full IDE, 100% VS Code compatible | VS Code extension, slightly weaker    |
| Large refactors / cross-file | Strong                  | Weaker                                  |
| GitHub deep integration | Basic                       | Strong (PR review, issue linking)      |
| Price               | $20                              | $10                                    |

**Copilot fits**:
- Heavy GitHub users (enterprise integration is unbeatable)
- Tight budget + completion-focused needs
- Microsoft / Azure ecosystem

**Cursor fits**:
- Want the best agent coding experience
- Like switching between models
- Don't care about GitHub integration

## OpenAI Codex (2025 version)

Not the 2021 Codex. The current Codex is OpenAI's CLI agent + web version, relaunched in May 2025. The model is functionally similar to Claude Code.

Tiers:

- **Codex CLI Free**: Limited GPT-5 mini, runs simple tasks
- **Included in ChatGPT Plus** ($20): GPT-5 / o-series, with quotas (hundreds of small tasks/day, large tasks limited)
- **Included in ChatGPT Pro** ($200): GPT-5 Pro, near-unlimited
- **Enterprise**: Bundled with OpenAI Enterprise

**Codex vs Claude Code**:

| Dimension          | Claude Code                      | OpenAI Codex (2025)                    |
| ------------------ | -------------------------------- | -------------------------------------- |
| Primary model      | Sonnet / Opus                    | GPT-5 / o3-pro                         |
| CLI maturity       | Mature, large ecosystem          | Newer, catching up since 2025-05       |
| Multi-file editing | Strong                           | Strong                                 |
| MCP protocol support | Built-in + large marketplace   | In progress                            |
| Long agent tasks   | Excellent (Anthropic prioritizes agents) | Excellent (OpenAI pushing Agent SDK) |
| Bundled with       | Claude Pro / Max                 | ChatGPT Plus / Pro                     |

**How to choose**:

- Already on ChatGPT Plus / Pro → use Codex, don't add Claude
- Already on Claude Pro / Max → use Claude Code, don't switch
- Fresh choice → depends on what you write. Frontend / full-stack: Claude Code slightly ahead. Backend / data / heavy reasoning: Codex slightly ahead. Gap is narrowing.

## How to combine coding subscriptions

### Scenario A: Solo independent developer

Budget $20: **Cursor Pro alone**. Skip ChatGPT / Claude — Cursor's built-in models cover it.

Budget $40: **Cursor Pro $20 + Claude Pro $20**. Cursor for coding, Claude.ai for long documents / writing / occasional chat.

Budget $60: Skip the half-Max math — go **Cursor Pro $20 + ChatGPT Plus $20 + Claude Pro $20** for better coverage.

### Scenario B: Heavy agent developer

Budget $100-150: **Cursor Pro $20 + Claude Max $100**. Cursor for daily completion, Claude Max for large Claude Code agent quotas.

Budget $200+: **Cursor Pro+ $40 + Claude Max $200** OR **Cursor Ultra $200 + Claude Pro $20**. The first leans agent / CLI; the second leans IDE-centric.

### Scenario C: Enterprise / team

5-50 people: **Cursor Business $40/seat + Claude Team $30/seat**. Both teams subscribe; SSO / data isolation / admin all in place.

100+ people: Negotiate Enterprise on both, volume discounts apply.

## Subscribing from China

Same logic as ChatGPT / Claude — they all use Stripe under the hood. Cursor's approval rate for Chinese cards is similar to OpenAI (40-60%). Subscription proxy is the most reliable option.

Notable difference: **Cursor's account ban rate is lower than OpenAI / Anthropic.** Account sharing and IP drift rarely trigger bans, so the proxy market price is also cheaper.

## Price history

| Date    | Event                                              |
| ------- | -------------------------------------------------- |
| 2023-03 | Cursor launches, free                              |
| 2024-01 | Cursor Pro $20 launches                            |
| 2024-12 | Cursor Pro+ $40 / Business $40 launched            |
| 2025-05 | OpenAI Codex relaunched                            |
| 2025-08 | Cursor Ultra $200 launched                         |
| 2026-02 | Cursor integrates GPT-5 Pro / Claude Opus 4.5      |

---

**Stuck paying for Cursor Pro / Business from China?** [payforgpt.com](https://payforgpt.com) is a Chinese AI subscription proxy serving users without direct overseas payment access. Full Cursor tier coverage, Chinese-language support, Alipay / USDT accepted, Pro from 99 RMB/month.

---

📘 [Read in Chinese (中文版)](../05-cursor-codex-guide.md)
