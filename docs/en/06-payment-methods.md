# 06 · Complete Comparison of Payment Methods

English | [中文](../06-payment-methods.md)

---

> Paying for overseas AI subscriptions from China comes down to 7 paths. This guide breaks each one down on cost / risk / speed / reversibility / who it fits, with a summary table at the end.

## Top-level comparison

| Method                | Hidden cost            | Rejection rate | Speed         | Refundable | Best for                     |
| --------------------- | ---------------------- | -------------- | ------------- | ---------- | ---------------------------- |
| Chinese VISA/MC card  | 1-3% FX + spread       | 40-60%         | Instant       | Easy       | Chinese users with foreign-tier cards |
| Foreign domestic card | 0 (native currency)    | <5%            | Instant       | Easy       | Users with overseas family / long-term residents |
| Apple Pay / gift card | 25-30% (Apple cut)     | <10%           | Instant       | Hard       | iOS users, no foreign card   |
| Google Play gift card | 25-30%                 | 10-20%         | Instant       | Hard       | Android users                |
| Virtual cards (Wise / Revolut / Wildcard) | 1-5% issuance | 15-30% | Instant   | Medium     | Users with overseas phone / KYC ability |
| USDT / crypto         | 0-2% (chain fees)      | 0 (direct transfer) | 5-30 min  | No         | Crypto users, anti-KYC users |
| Subscription proxy    | 10-30% (service fee)   | 0 (proxy guarantees) | 5-30 min | Depends on vendor | Users who don't want hassle |

---

## Foreign / Chinese credit cards

### Foreign domestic cards (Chase Sapphire / Amex Gold / HSBC Hong Kong AmEx, etc.)

The most reliable. Requires you or family to live overseas long-term and hold a domestic card.

- **Rejection rate**: < 5%, essentially no risk control issues
- **Extra cost**: 0 (US subscriptions on USD card, EU on EUR card)
- **Watch out for**: billing address must match the card exactly; don't open 5+ AI subscriptions on the same card in a month (bank may flag for fraud)

If this is your path, the rest of this section is optional reading.

### Real approval rates for Chinese credit cards

Whether a Chinese-issued "multi-currency" / "VISA / MC" card works depends on the specifics. Observed data as of 2026-05:

| Card                                  | OpenAI approval | Stripe general approval | Notes                       |
| ------------------------------------- | --------------- | ----------------------- | --------------------------- |
| China Merchants Bank multi-currency VISA / MC | 60-70%   | 70-80%                  | Highest success rate of any Chinese card |
| CITIC Bank i Platinum / Lily / MasterCard    | 50-60%   | 60-70%                  | Long-time popular pick      |
| Huaxia Bank Elite VISA                | 40-50%          | 50-60%                  | Depends on BIN range         |
| SPDB AE White (AmEx)                  | 30-50%          | 50-65%                  | Improving recently           |
| ICBC VISA / MC                        | 20-30%          | 30-40%                  | BIN heavily flagged          |
| CCB / ABC VISA / MC                   | 10-25%          | 20-40%                  | Strict risk control          |
| China UnionPay-only cards             | < 5%            | 0%                      | Most overseas merchants don't accept UnionPay |
| Alipay / WeChat credit cards          | 0%              | 0%                      | Non-cross-border by design   |

**Why Chinese cards get rejected**:

1. The issuing bank's BIN range is flagged as "high-risk cross-border" by OpenAI / Stripe — direct rejection
2. Billing address / ZIP mismatch — Chinese addresses don't exist in OpenAI's ZIP database; faking a US address conflicts with card registration
3. IP anomaly — card is Chinese but IP is US (proxy), triggers "card not present + suspicious IP" double risk
4. Bank-side overseas spending protection — many banks default to blocking "unauthorized / no-OTP cross-border charges"

**Concrete steps to improve approval**:

1. **Stable proxy first**: Use a clean US / JP node, keep it stable for hours before paying (short-term IP flapping triggers risk control)
2. **Use a real US billing address**: Real public addresses work (libraries, companies). The ZIP must match the city / state in the database.
3. **Watch for SMS confirmation**: Many cards send SMS verification for cross-border charges. Click the confirmation link in the SMS (Chinese mobile numbers usually receive these).
4. **Small-amount test first**: Subscribe to a $1-5 service first (a domain, for example). Once it succeeds, the bank whitelists the card and ChatGPT approval rates jump.
5. **Don't retry immediately**: After a rejection, don't retry the same merchant within 24 hours. The bank will hard-lock the card after 2-3 retries.

## Apple Pay / Apple ID gift cards

Best fit: don't want a foreign credit card, mainly use iOS / iPadOS.

**Process**:

1. Register a fresh US-region Apple ID (you can't switch a China-region Apple ID to US — must be new)
2. Buy US App Store gift cards on Taobao / Xianyu (physical card screenshot showing the code)
3. App Store → Gift Cards → Redeem → balance loaded
4. Subscribe via in-app purchase, charged to balance

**Pros**:

- Very high approval rate (< 10% rejected, mostly Apple ID credit issues)
- No foreign credit card / phone number required
- Apple offers Chinese-language support — easier when issues arise

**Cons**:

- Apple takes 30%, so Plus goes from $20 to $25 (extra $5/month, $60/year)
- Maintaining a US Apple ID requires care (short-term IP drift, batch top-ups can lock the account)
- Occasional "already used / frozen" cards (fakes / second-hand) — buy from reputable sellers

**Avoid pitfalls**:

- Buy gift cards sold through Apple official / mainstream retailers (US Costco, Best Buy, Apple.com direct)
- For Taobao gift cards, only use sellers offering 100% redemption guarantee via escrow
- Top up $50-100 at a time (covers 2-4 months) — don't load $500 at once and draw attention

## Google Play gift cards (Android)

Same logic as Apple ID gift cards, but with a Google account:

- Slightly lower approval (10-20% rejected; Google's account risk model is stricter than Apple's)
- Same 30% cut
- Google gift card market is less stable than Apple's — more fakes

## Virtual cards (Wise / Revolut / Wildcard / Cardvcc, etc.)

Virtual cards issue a US / EU / HK card number bound to your Wise / Revolut / Wildcard account, used for paying overseas subscriptions.

### Wise

- Registration requires foreign phone + KYC (passport / overseas ID / overseas address proof)
- Getting Wise from China has gotten harder over the past few years
- Once approved, extremely reliable. 95%+ approval rate.
- Good FX (mid-market + 0.4-0.7%)

### Revolut

- Similar to Wise, mostly UK / EU
- High KYC barrier for Chinese users
- High reliability

### Wildcard / Cardvcc / OneKey, etc. ("virtual card platforms")

Most popular in the Chinese-speaking world due to low KYC bar:

- Often only requires email + passport (some have no KYC)
- Platform issues "US virtual card", top up with USDT
- Approval rate: 60-80% (better than Chinese cards, worse than Wise)
- Risks: platform shutting down / cards failing suddenly / merchants rejecting certain BINs
- Fees: $1-10 issuance, 1-3% top-up fee

**Top virtual card platforms as of 2026-05**:

| Platform     | Notes                              | Risks                              |
| ------------ | ---------------------------------- | ---------------------------------- |
| Wildcard     | Most popular in Chinese-speaking world, USDT top-up | BINs frequently get newly blocked, need to swap cards |
| OneKey Card  | Bundled with OneKey wallet, more stable | Requires installing OneKey wallet |
| Nobepay      | Simple, USDT top-up to issue card  | Some merchants reject the BIN      |
| dcard / vcc.com series | Early players, some still stable | Fragmented market, weak compliance |

**Rule of thumb**: Virtual cards are a "medium cost, medium approval" middle path. If you're already comfortable with subscription proxies or Wise, virtual cards add little value.

## USDT / crypto payment

Some subscription proxies (including [payforgpt.com](https://payforgpt.com)) accept USDT.

**Process**:

1. Already have USDT (exchange / wallet)
2. Send to the TRC20 / ERC20 / Polygon address provided by the proxy
3. After on-chain confirmation (TRC20 ~30 sec, ERC20 a few minutes), proxy starts processing your subscription

**Pros**:

- No domestic banks involved — the channel is fully external, no risk control
- Irreversible: the proxy can't run away after taking your order (large vendors won't disappear over $20)
- Very low transfer cost (TRC20 ~$1/tx)

**Cons**:

- Requires basic crypto / wallet knowledge
- 0-1% on-chain rate fluctuation
- Send to wrong address = unrecoverable

**Best for**: existing crypto users. High barrier for total newcomers.

## Subscription proxy services

The simplest path to paying for subscriptions from China. The proxy handles "create account + top up + subscribe + card-key delivery / account handover" end-to-end.

### Real cost of subscription proxies

| Service              | Official price | Proxy market price (RMB/month) | Markup    |
| -------------------- | -------------- | ------------------------------ | --------- |
| ChatGPT Plus         | $20            | 130-150                        | ~5-15%    |
| ChatGPT Pro          | $200           | 1500-1800                      | ~5-25%    |
| Claude Pro           | $20            | 120-150                        | ~0-15%    |
| Gemini Advanced      | $19.99         | 99-130                         | ~0-5%     |
| Cursor Pro           | $20            | 99-130                         | ~0-5%     |
| Grok Premium         | $8             | 80-100                         | ~30%      |

> Some proxies are cheaper than the official RMB conversion (they bulk-source accounts and use cheap payment rails), but service quality varies wildly.

### Proxy vetting checklist

How to pick a reliable subscription proxy:

1. **Multiple payment options** — vendors that only accept bank transfer / WeChat have low exit cost; pick ones with USDT support
2. **Public pricing** — official website with clear prices. Private DM quotes are usually phishing / scams.
3. **Live Chinese support** — test with 5 common questions. < 5 min response time is a good sign.
4. **Public case studies / reviews** — searchable on Twitter / Xiaohongshu / Tieba. Less likely to disappear.
5. **Clear policy on "account sharing / after-sales"** — runaway shops always say "full after-sales guarantee". Real shops say "free replacement within 7 days if there's an issue".
6. **Don't go suspiciously cheap** — Plus for 60 RMB is either black-market keys (dies in a week) or phishing.

### Common scam patterns to avoid

- Xianyu / second-hand platform "activation codes" under 50 RMB: 85% are recycled keys / black-market cards. Activate, dies in 1-7 days.
- "Insider price" in WeChat groups: no website, pure personal WeChat — exit cost is zero
- "Lifetime" accounts: 99 RMB lifetime ChatGPT — guaranteed to be a black-market shared account, banned by the weekend
- Pinduoduo shops: weakest platform oversight, fastest disappearances

**Rule of thumb**: at the same 100 RMB monthly price, a vendor with public website + multiple payment methods + Chinese support is 10x more reliable than a cheap Xianyu shop.

## Final summary table

| Dimension     | Chinese card | Foreign card | Apple gift card | Virtual card | USDT       | Proxy           |
| ------------- | ------------ | ------------ | --------------- | ------------ | ---------- | --------------- |
| Hidden cost   | 1-3%         | 0            | 25-30%          | 1-5%         | 0-2%       | 5-30%           |
| Approval rate | 40-60%       | 95%+         | 90%+            | 70-90%       | 100%       | 100% (guaranteed) |
| Speed         | Instant      | Instant      | Instant         | Instant      | 5-30 min   | 5-30 min        |
| Reversibility | Refundable   | Refundable   | Apple refund    | Depends      | No         | Vendor-dependent |
| Barrier (China) | Medium     | High         | Low             | Medium       | Medium     | Low             |
| Vendor risk   | 0            | 0            | 0               | Medium       | 0          | Medium (vet vendor) |
| Chinese support | Bank       | None         | Apple Chinese   | None         | None       | Strong          |

---

**No foreign card, no patience for virtual cards / crypto?** [payforgpt.com](https://payforgpt.com) is a Chinese AI subscription proxy serving users without direct overseas payment access. ChatGPT / Claude / Gemini / Grok / Cursor full coverage, Alipay / WeChat / USDT accepted, 7-day after-sales support.

---

📘 [Read in Chinese (中文版)](../06-payment-methods.md)
