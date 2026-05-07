# 01 · Complete Guide to ChatGPT Subscriptions

English | [中文](../01-chatgpt-complete-guide.md)

---

> Scope: All paid tiers of OpenAI's ChatGPT — web, iOS, Android, and desktop. This guide does not cover OpenAI Platform / API (token-based billing, separate from subscriptions).
> Data as of: 2026-05. OpenAI restructures tiers roughly every 6-9 months. File an issue if anything goes stale.

## Tiers and pricing

OpenAI currently has 5 tiers, from free to enterprise:

| Tier        | Price (USD)     | Target audience           | Key differences                                                          |
| ----------- | --------------- | ------------------------- | ------------------------------------------------------------------------ |
| Free        | $0              | Trial / light use         | GPT-5 mini + limited GPT-5, no image gen, no voice/vision                |
| Plus        | $20/mo          | Individual paid users     | Full GPT-5, o-series reasoning models, DALL·E, Advanced Voice, Code Interpreter |
| Pro         | $200/mo         | Heavy research / pros     | GPT-5 Pro reasoning, near-unlimited usage, Sora priority, Operator agent |
| Team        | $25/seat (annual) | 5+ person teams         | All Plus features + shared GPTs + team workspace + no training on data   |
| Enterprise  | Contact sales   | 100+ person companies     | SSO, SCIM, audit logs, SLA, dedicated CSM, custom quotas                 |

> Monthly vs annual: Plus and Pro are monthly only — no annual discount. Team is $30/seat monthly or $25/seat annual ($60/year savings).
> Apple App Store: iOS Plus is $25/month (Apple takes 30%). Subscribe via web instead.

## Free vs Plus — what does $20 buy you

If you're on the fence, here's the real Free vs Plus delta as of 2026-05:

| Dimension      | Free                     | Plus ($20)                                          |
| -------------- | ------------------------ | --------------------------------------------------- |
| Default model  | GPT-5 mini               | GPT-5 (smart) + o4 reasoning                        |
| Usage limits   | ~10 GPT-5 messages per 5 hours | 80 GPT-5 messages per 3 hours; ~50 o-series per week |
| Advanced Voice | Limited / short sessions | Near-unlimited                                      |
| DALL·E images  | 2-3 per day              | ~50 per 3 hours                                     |
| Code Interpreter / data analysis | Limited        | Full access                                         |
| Custom GPTs    | Use only, no creation    | Create + use                                        |
| File uploads   | Restricted               | Up to 10 files per turn, 512 MB each                |
| Deep Research  | 5 lite runs/month        | 25 full + 25 lite per month                         |
| Sora video     | Not available            | 50 720p videos/month (standard tier)                |

**$20 buys you usage headroom and model access.** If you talk to ChatGPT more than an hour a week, you'll hit the Free cap. Plus is the right answer.

## Plus vs Pro — where does the 10x premium go

Pro launched in December 2025 at $200/month. Five core differences vs Plus:

1. **GPT-5 Pro mode (exclusive)**: Pro mode runs think-and-reflect multi-pass reasoning before answering. Built for heavy math, scientific reasoning, and code-level analysis. Plus users can't access it.
2. **o3-pro / latest o-series unlimited**: Plus gives you ~50 o4/o3 messages per week. Pro removes the cap.
3. **Operator (browser agent) higher quota**: Lets ChatGPT drive a browser to book tickets, order food, fill forms. Plus is rate-limited; Pro is essentially open.
4. **Deep Research nearly unlimited**: Plus gets 25/month, Pro gets 250+/month. Heavy users run 10+ deep research jobs per day.
5. **Sora priority + watermark-free**: Pro generates 1080p / 20-second videos. Plus is capped at 720p / 10s.

**Who is Pro worth it for?**

- 3+ Deep Research runs per day (each takes 5-15 min — a Plus monthly quota burns out in days)
- Heavy math / scientific / compiler analysis where GPT-5 Pro mode matters
- Production workflows depending on Operator browser automation
- AI video creators where Sora is core to output

**Who shouldn't bother?**

- Daily writing, coding, casual chat — Plus is enough; the extra $180/month is wasted
- "Expensive must be better" — observed: 90% of Plus users who upgrade to Pro cancel within a month

## Team tier — who needs it

Team targets 2-150 person organizations at $25/seat/month (annual). Three highlights:

1. **Data not used for training by default** — Plus also doesn't train, but the toggle is on the user. Team enforces it at org level.
2. **Shared GPT library** — Custom GPTs built by anyone in the team auto-sync to all members
3. **Admin console** — Invite seats, view usage, central billing

Note: Team minimum is 2 people. A single user can't subscribe. If you're solo, just get Plus — Team's premium pays for management, not better models.

## Enterprise — most readers can skip

100+ employee companies. SSO, SCIM, audit logs, SLA, custom quotas. No public pricing (observed: 100-seat minimum, $60-80/seat/month range). Process: apply → sales → MSA → deployment → go-live. 4-6 weeks average. Not relevant for individual users.

## How to subscribe (by location and payment access)

### Path A: Overseas, with a foreign credit card

The straightforward way. Log in to ChatGPT → Upgrade → enter card (Visa / MasterCard / AmEx) → done.

Watch out for:
- Billing address must match the card's issuing country (US card needs a US address with a real ZIP that resolves to the right city/state)
- IP must not be in an OpenAI-blocked region (mainland China, Russia, etc). A mainland IP + foreign card still gets rejected.

### Path B: China, with an international-tier Chinese credit card

This covers cards like the China Merchants Bank Visa Infinite, CITIC Bank platinum, Huaxia Bank Mastercard, etc.

Observed approval rate: 40-60%. Common rejection reasons:
- Card BIN range registered to China — OpenAI's risk engine blocks outright
- Wrong billing ZIP (many users don't realize the billing ZIP for these cards is the address registered with the bank, not their ID address)
- Mainland dynamic IP triggers risk controls

Cards that work: China Merchants Bank multi-currency Visa, CITIC i Platinum, Huaxia Elite (some), SPDB AE White (occasional).
Cards that mostly fail: ICBC Mastercard, CCB Long Card, ABC cards, any China UnionPay-only card (essentially 0% approval).

Tactics to improve approval:
1. Use a clean residential US/JP proxy for the entire flow (avoid shared IP pools)
2. Use a real US address with a real ZIP code (fakeaddress.info works, but OpenAI now validates ZIP-state-city consistency)
3. Card balance: at least $25 ($1 auth + $20 monthly + buffer)

### Path C: Apple ID in-app purchase

Use a US / HK / JP Apple ID, top up with App Store gift cards, subscribe in-app.

Pros: No foreign credit card required.
Cons: 25% more expensive (Apple's 30% cut bumps Plus to $25/month). You also need to create a fresh non-China Apple ID — China region Apple IDs cannot subscribe to ChatGPT.

## Common issues for users in China

### Issue 1: Payment page hangs, then "Your card has been declined"

90% of the time it's the card BIN range being blocked. Switch to an international-tier multi-currency card. Or switch path entirely (Apple ID / proxy service).

### Issue 2: Subscribed successfully but the model picker doesn't show GPT-5 / Plus badge

Clear browser cookies + restart the app. OpenAI's status sync occasionally lags 5-30 minutes. If still stuck, log out and back in.

### Issue 3: Subscribed for a few days, then suddenly canceled with "ToS violation"

Most common causes:
1. **Account is being shared** — OpenAI scans for IP drift. Five+ countries on one account in a week means automatic subscription cancellation.
2. **Card is stolen** — Black-market cross-border card. OpenAI's risk team works with Stripe to flag both card and account.
3. **Account reported for abuse** — Heavy API-style request patterns, automation, banned content.

Prevention: one account, one card, one stable IP. Don't share.

### Issue 4: Risk-flagged or card-rejected — is there self-service appeal?

Yes, but success rate is low. Process:
1. Submit ticket at https://help.openai.com, category "Billing"
2. Write in English, include transaction date + last 4 digits (never full card number)
3. Average response time: 2-7 days

Observed: Card-risk-flagged appeals succeed ~10% of the time. Account suspensions: ~40% restoration rate.

## Refunds / cancellation

- **Cancel**: Settings → Subscription → Manage → Cancel. Active until end of paid period; no charge next month.
- **Refund**: Plus has no official refund policy (subscription product). Email support saying "just subscribed, want to cancel" — about 30% chance of full refund. Within 7 days has highest success rate.
- **Apple in-app refunds**: Use reportaproblem.apple.com. iOS refunds are far easier than web refunds.

## Price history

| Date        | Event                                                       |
| ----------- | ----------------------------------------------------------- |
| 2023-02     | Plus launches at $20                                        |
| 2024-01     | Team launches at $25/seat                                   |
| 2024-12     | Pro launches at $200 (initially with GPT-4o Pro mode)       |
| 2025-08     | GPT-5 fully replaces GPT-4o; Plus / Pro pricing unchanged   |
| 2025-12     | Operator built into Pro tier; Plus gets limited Operator    |
| 2026-03     | Plus rises to $22 in EU, Japan, Brazil; US unchanged        |

OpenAI has never raised the headline US price for Plus or Pro, but regional pricing is diverging.

---

**Can't pay for ChatGPT from China?** [payforgpt.com](https://payforgpt.com) is a Chinese AI subscription proxy serving users without direct overseas payment access. Chinese-language support, Alipay / WeChat Pay / USDT accepted, card-key delivery. Plus, Pro, and Team all available.

---

📘 [Read in Chinese (中文版)](../01-chatgpt-complete-guide.md)
