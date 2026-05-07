# 03 · Complete Guide to Gemini Subscriptions

English | [中文](../03-gemini-complete-guide.md)

---

> Scope: Google Gemini web / app / Workspace integration / Google AI Studio.
> Data as of: 2026-05. Gemini has restructured tier names more than any other product covered here — twice in 2024 alone. This guide reflects the current "Google One AI Premium / AI Pro / AI Ultra" three-tier structure.

## Tier overview

Google bundles AI subscriptions into the Google One ecosystem, so a single subscription gives you both cloud storage and AI features. Current main tiers:

| Tier                          | Price (USD)   | Main features                                                       | Suited for                            |
| ----------------------------- | ------------- | ------------------------------------------------------------------- | ------------------------------------- |
| Gemini (Free)                 | $0            | Gemini 2.5 Flash + limited 2.5 Pro + basic image generation          | Trial / light Q&A                     |
| Google AI Pro                 | $19.99/mo     | Full Gemini 2.5 Pro + Deep Research + 2TB Drive + NotebookLM advanced | Heavy individuals, Workspace users   |
| Google AI Ultra               | $249.99/mo    | Veo 3 video generation + Gemini 2.5 Deep Think + 30TB Drive + Whisk | Video creators, heavy content output |
| Workspace + Gemini (Business) | $30/seat/mo   | Enterprise Gemini + deep Docs / Gmail / Sheets integration          | Companies / SMBs                      |

> Naming gotcha: "Gemini" is the product name (model + app). "Google AI Pro" is the subscription tier name. "Gemini Advanced" is the old name for Google AI Pro. The three names are used interchangeably in the wild.

## Free vs AI Pro — what does $19.99 buy you

| Dimension                           | Free                     | AI Pro ($19.99)                              |
| ----------------------------------- | ------------------------ | -------------------------------------------- |
| Default model                       | Gemini 2.5 Flash         | Gemini 2.5 Pro                               |
| Pro model usage                     | ~10-15 messages per day  | Near-unlimited (queues at peak)              |
| Deep Research                       | 5-10 runs/month          | 100+ runs/month                              |
| Gemini in Docs / Gmail / Sheets     | Partial                  | Full (writing, summarization, translation, table generation) |
| Image generation (Imagen)           | Limited                  | High quota                                   |
| Video generation (Veo 2)            | Not available            | ~50 720p videos/month                        |
| NotebookLM                          | Basic                    | Advanced (longer context, more sources, audio overviews) |
| Google Drive                        | 15 GB (shared with family) | 2 TB                                       |
| Gemini in Android Studio / Code Assist | Not available         | Available with quota                          |

**The real value of AI Pro isn't the model — it's Workspace integration.** If you write in Docs, send mail in Gmail, and crunch numbers in Sheets, having Gemini embedded in the sidebar beats tabbing back and forth to ChatGPT.

## AI Pro vs AI Ultra — where does the 12x premium go

Ultra launched in early 2025. Four core differences vs AI Pro:

1. **Veo 3 video generation** — 1080p / 8-second clips with audio. Currently the highest-quality consumer-grade model.
2. **Deep Think mode** — Multi-step reasoning similar to ChatGPT Pro. More reliable on complex math / scientific problems.
3. **Whisk** — Image-as-prompt mixed-input generation.
4. **30 TB Drive** + advanced Workspace features.

**Worth it?**

Yes for:
- AI short-video creators (YouTube Shorts, TikTok, Douyin). Veo 3 still leads on quality.
- Google Workspace power teams that actually use 30TB shared.

No for:
- Non-video users — the extra $230 is pure premium for capabilities you won't touch
- Reasoning-first users — ChatGPT Pro at $200 is stronger on pure reasoning

Pattern: Ultra retention is much lower than Pro. Many subscribe for one month to ship a few video projects, then downgrade back to Pro.

## Workspace integration in practice

Gemini's coverage across the Google suite (as of 2026-05) is dramatically better than a year ago:

| Product       | What Gemini does                                    | Real-world quality                |
| ------------- | --------------------------------------------------- | --------------------------------- |
| Docs          | Rewrites, continuations, outlines, translation, table generation | Excellent — feels native        |
| Gmail         | Draft emails, smart replies, long-thread summaries  | Good — English better than Chinese |
| Sheets        | Formula writing, data explanation, chart generation | Formulas are accurate; data analysis still needs review |
| Slides        | Outline + image generation                          | Mediocre — layout quality below human |
| Meet          | Auto-transcription + meeting summary                | Excellent, including Chinese      |
| Drive         | Semantic search, cross-file summaries               | Rarely used in China (Drive is blocked); a killer feature for overseas PMs |
| NotebookLM    | Multi-source documents into a Q&A research assistant + audio overviews | Killer feature. Mandatory for content creators / researchers |

Drive integration adds little for users in mainland China (Drive is blocked). NotebookLM alone is worth the $19.99.

## Gemini vs ChatGPT Plus — which is better value

If you're picking one:

**Pick Gemini Advanced (AI Pro $19.99) if you**:
- Work primarily in the Google ecosystem (Docs / Gmail / Workspace)
- Are a researcher / academic / content creator (NotebookLM is a killer feature)
- Need 2TB cloud storage (storage alone is worth ~$10/month)
- Care about video generation (Veo beats Sora on certain styles)

**Pick ChatGPT Plus ($20) if you**:
- Mostly do programming / data analysis (Code Interpreter still leads)
- Need DALL·E for high-quality image generation
- Use voice conversation heavily (Advanced Voice + Standard Voice are ChatGPT strengths)
- Build with custom GPTs (the GPT ecosystem on ChatGPT is the most mature)

**Get both**: Many users subscribe to both at $40/month — Gemini for Workspace work, ChatGPT for general chat + coding.

## Subscribing from China

### Path A: Foreign credit card + Google Pay

Google uses Google Pay for billing, not Stripe. Approval rate for Chinese cards is actually higher than OpenAI — observed 60-75%.

Watch out for:
- Google account must be set to a non-China region (US is most common; Eurozone works but AI Pro is priced differently)
- IP must be in a Google-supported country (mainland China not on the list)
- Some Chinese multi-currency cards work, but you need to bind Google Pay successfully once

### Path B: Google Play in-app (Android users)

Bind a US-region Google Play account, top up with Play gift cards, subscribe in the app.
Same as Apple — Google takes 30%, so price jumps to $25-26/month.

### Path C: Subscription proxy service

Most common path from China. The proxy creates a US Google account and pays the subscription. Typical price: 99-120 RMB/month.

Notes:
- Google's account risk model is less aggressive than OpenAI's — proxy accounts last longer
- But some proxies bulk-create accounts using gift cards. Google occasionally catches the batch pattern, accounts die a few months later.

### Mainland China region restrictions

- Gemini.google.com loads, but sign-in requires a non-China IP
- NotebookLM and Veo video are unavailable in mainland China
- Workspace integrations require a non-China exit node

## Refunds / cancellation

- **Cancel**: Cancel directly in Google One settings. Active until end of period.
- **Refund**: Google offers full refund within 14 days if usage is light. Submit at support.google.com/googleone.
- **iOS / Android in-app refunds**: Use the platform's standard refund flow.

## Price history

| Date    | Event                                                |
| ------- | ---------------------------------------------------- |
| 2024-02 | Gemini Advanced launches at $19.99                   |
| 2024-08 | Renamed to Google One AI Premium                     |
| 2025-03 | Renamed to Google AI Pro; AI Ultra launches at $249.99 |
| 2025-09 | Veo 3 integrated into Ultra; model upgrade to Gemini 2.5 |
| 2026-01 | Workspace integration enters Pro tier (previously required Workspace separately) |

---

**Can't subscribe to Gemini Advanced from China?** [payforgpt.com](https://payforgpt.com) is a Chinese AI subscription proxy serving users without direct overseas payment access. Bundled US Google account + subscription delivery, Chinese-language support, USDT / Alipay accepted.

---

📘 [Read in Chinese (中文版)](../03-gemini-complete-guide.md)
