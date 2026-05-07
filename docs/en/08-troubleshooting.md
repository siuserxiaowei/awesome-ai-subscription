# 08 · Troubleshooting Payment Failures, Risk Controls, and Card Keys

English | [中文](../08-troubleshooting.md)

---

> 12 real scenarios, 2-3 step fixes for each. Sorted from most to least common — covers about 90% of payment / activation issues.

## Scenario 1: Payment page hangs, then "Your card has been declined"

**Most common causes**: card BIN flagged, billing address mismatch, IP anomaly.

**Fix**:

1. Switch to a clean, stable US / JP node, keep it stable for 1-2 hours before retrying
2. Try a different card (China Merchants Bank multi-currency VISA has the highest approval rate)
3. Use a real US billing address with a real ZIP (zip-state-city must match — don't use 90210 with Texas)
4. Still failing: switch to Apple ID gift card or subscription proxy

> Note: a card rejected twice within 24 hours by the same merchant gets auto-locked for cross-border charges. You'll need to call the bank to unlock. Don't retry compulsively after a failure.

## Scenario 2: Just subscribed, canceled hours/days later with "Your subscription has been cancelled"

**Most common causes**: OpenAI / Anthropic detected the payment card as stolen / shared / black-market.

**Fix**:

1. Check email for the official cancellation message and the stated reason
2. If it's "card issue": the money may already be refunded — no loss
3. If it's "account violation": appeal at help.openai.com → Billing, but success rate is low
4. After this, switch to a legitimate card / proxy and re-subscribe

> Black-market card charges are usually refunded, but the account may be blacklisted. You may need a fresh email to re-register.

## Scenario 3: Subscribed successfully, but the model picker doesn't show Plus / Pro badge

**Most common cause**: OpenAI status sync delay.

**Fix**:

1. Wait 5-30 minutes, refresh the page
2. Log out + log back in
3. Clear browser cookies / use incognito
4. Still stuck: check https://chat.openai.com/api/auth/session for the `isPaid` field

If `isPaid = true` but the UI is still locked, it's a pure cache issue. Just wait.

## Scenario 4: Apple ID gift card shows "This card has already been redeemed"

**Most common causes**: code already used / fake card / second-hand card.

**Fix**:

1. Immediately screenshot the code + the redemption error, contact the seller
2. Sellers using escrow (Taobao 7-day no-questions-asked / Xianyu escrow) — refund is recoverable
3. Xianyu / WeChat private deals — 90% unrecoverable, eat the loss
4. Going forward: only buy gift cards via "auto-delivery + platform escrow" channels

> Fake card market grew in late 2025 because black-market scripts brute-force gift card inventory. Bad money is driving out good.

## Scenario 5: Apple ID locked with "Your Apple ID has been locked for security"

**Most common causes**: multiple-country logins in a short window, batch top-ups, multi-device activations.

**Fix**:

1. Use https://iforgot.apple.com password reset flow — typically resolves in 1-3 days
2. After unlock, immediately bind 2FA to a correct phone number (lock-outs often happen because of unbound phone numbers)
3. Switch to a stable IP, only use 1-2 fixed-region IPs going forward
4. If it's "economic lockdown" from batch top-ups: contact Apple support (Chinese works), explain — about 50% chance of resolution

## Scenario 6: Payment confirmed but Claude.ai / ChatGPT shows "Subscription not found"

**Most common causes**: email casing mismatch / wrong account binding.

**Fix**:

1. Log out, log back in using the exact lowercase email used for payment
2. Check Settings → Subscription, verify it's actually linked to the current account
3. If not: contact official support (billing@anthropic.com / help.openai.com) with payment details
4. Usually resolves in 1-3 days

## Scenario 7: Card key activates, fails after a few days

**Most common cause**: black-market card (shared / stolen) caught and banned by the platform.

**Fix**:

1. Screenshot payment + activation records, contact the proxy vendor for warranty service
2. Reputable shops: free replacement within 7-30 day warranty period
3. Runaway shops / Xianyu shops: essentially unrecoverable, eat the loss
4. Going forward: vet your proxy following [06 - Payment methods](./06-payment-methods.md#代充服务)

## Scenario 8: Claude.ai shows "Anthropic does not offer service in your country"

**Most common cause**: IP is in an Anthropic-unsupported country (mainland China, Russia, Iran, etc.).

**Fix**:

1. Use a stable US / JP / HK exit node, ensure IP is clean
2. Test if the node is truly clean: visit https://www.cloudflare.com/cdn-cgi/trace and check the `loc` field
3. If it's a CDN-accelerated node (IP shared with many users), it may be flagged by Anthropic. Switch to dedicated IP / different node
4. Open browser in incognito, clear all Anthropic-domain cookies, re-login

## Scenario 9: Payment page shows "3D Secure verification failed"

**Most common cause**: 3DS (OTP / SMS verification) didn't go through.

**Fix**:

1. Check bank app SMS — cross-border payment triggers SMS OTP, click the confirmation link within 5 minutes
2. Chinese phone numbers sometimes don't receive OTP. Contact bank support to enable cross-border SMS
3. China Merchants Bank / CITIC: enable "cross-border consumption verification SMS" manually in the app
4. Still failing: use an Apple Pay-supported card. Apple Pay uses Touch ID / Face ID, doesn't depend on SMS

## Scenario 10: Subscribed, but switching IP back to China gets immediate restrictions / kicked

**Most common cause**: OpenAI / Anthropic detects large IP drift, triggers account-level risk control.

**Fix**:

1. Don't connect from a Chinese IP directly. Use a stable foreign exit node throughout
2. Don't flap regions on your node (US → JP → HK → US = high risk)
3. iOS / Android apps sometimes leak real IP (even with double-layer proxy). Use the web version first
4. For heavy users: route AI domains through a foreign exit, leave other traffic on the China network

## Scenario 11: Cursor subscribed but Fast requests still queue

**Most common cause**: Cursor's Pro Fast quota is a soft limit. Peak hours may temporarily downgrade.

**Fix**:

1. Log out + log back in, refresh subscription state
2. Check Settings → Account, verify it really shows Pro
3. Peak hours (US 9-11 PM / China 9-11 AM) — queueing is unavoidable, wait a few hours
4. Persistent queueing: upgrade to Pro+ ($40), Fast quota triples

## Scenario 12: ChatGPT subscribed on web but iOS app shows Free

**Most common cause**: iOS app and web may be on different accounts / cached states.

**Fix**:

1. Sign out + sign back in on iOS app
2. iOS Settings → ChatGPT → clear app cache / reinstall
3. Check email casing — sometimes you logged into a different account
4. Still stuck: restart phone (iOS Apple Receipt sync is occasionally slow)

## Refund flows at a glance

| Scenario                              | Recommended channel                          | Success rate |
| ------------------------------------- | -------------------------------------------- | ------------ |
| Card charged but service not granted  | Bank dispute                                 | 70-90%       |
| Subscribed, want immediate refund     | Email OpenAI / Anthropic support, within 7 days | 30-60%    |
| Apple in-app refund                   | reportaproblem.apple.com — easiest of all    | 70-90%       |
| Google Play in-app refund             | Play Store refund page, similar to Apple     | 60-80%       |
| Card key / service from proxy vendor  | Contact proxy support                        | Vendor-dependent |

## Anti-scam summary

1. **Small-amount test first**: for an unfamiliar service, pay small ($1-10) first, then go full month
2. **Stable node**: same IP throughout the payment flow, don't flip mid-way
3. **Don't share accounts**: even cheap, shared accounts get banned in days, data may be lost
4. **Screenshot everything**: document each step. Useful for disputes / refunds / appeals.
5. **Vet proxy by payment options**: vendors with USDT support tend to be more legit (more payment options = more compliant)

---

**Hit an issue not covered here?** [payforgpt.com](https://payforgpt.com) is a Chinese AI subscription proxy serving users without direct overseas payment access. Chinese-language support 16 hours/day. Common ChatGPT / Claude / Gemini issues get a fix within 5 minutes. You can also file a [GitHub issue](https://github.com/siuserxiaowei/awesome-ai-subscription/issues) and we'll update the docs.

---

📘 [Read in Chinese (中文版)](../08-troubleshooting.md)
