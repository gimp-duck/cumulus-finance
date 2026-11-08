---
id: DOMAIN-VISION
title: Vision
status: draft
updated: 2026-11-08
sources: [WS00, WS01]
---

# Vision

## In one sentence

Cumulus Finance lets an investor **monitor their whole Financial wealth, past and present, in fine detail**, and **supports independent arbitrage decisions** within their overall strategy.

## Context & origin

- **Name:** *Cumulus*, the cloud type — close to "accumulate" (growing portfolios); the meteorological meaning evokes **forecasting**. (The "cloud" connotation is not a technical choice.)
- **Today:** each broker / bank / insurer has its own website or app, with its own limits; brokers export operation reports (e.g. `.xlsx`). The owner follows **Trident**, a paid community method, every week, and re-enters operations manually in it. Investor platforms have good ideas, but not the owner's "sharper vision".
- **Trigger:** the maturity of AI tools for software development assistance.
- **Users:** the owner only for now; possibly relatives, then a wider community circle, if personal use proves convincing.

## Problems

| # | Problem | Who suffers | Frequency / cost | Current workaround | Priority |
|---|---|---|---|---|---|
| P1 | No consolidated view of the Financial wealth spread across several brokers, banks, insurers and employee savings providers | investor | every weekly purchase; lost time | none | 1 |
| P2 | Broker operations are re-entered manually in another tool (no import) | investor | every weekly purchase; lost time | none | 2 |
| P3 | No per-instrument history highlighting the investor's buys/sells; no per-operation view of cost at purchase vs value now or at a chosen date | investor | every weekly purchase; unseen fees | none | 3 |
| P4 | No display in instrument / reference currency, each optionally inflation-adjusted; no split of currency effect vs instrument performance | investor | — | none | 4 |
| P5 | Operation costs (FX fees, brokerage fees, taxes, social contributions — paid and virtually due) are not visible; no gross vs net view | investor | — | none | 5 |
| P6 | The basis of displayed performance figures is unclear (gross or net? fees? dividends?) | investor | — | none | 6 |
| P7 | Arbitrage depends on a community method (Trident); no independent decision support | investor | — | none | 7 |

Frequency / cost was given once for the top problems; "—" means not asked separately.

## Goals & success measures

The investor's goal is to grow their assets. **Cumulus's goal is to monitor (observe the past) and give the means to make the right future choices** — it can succeed in a year when the portfolio falls.

| Horizon | Goal | Observable signal |
|---|---|---|
| 1 year | No manual entry for broker accounts (import only); real cost of every past operation known | number of manual entries; fees discovered that were unknown |
| 3 years | Arbitrage choices made without Trident; other users use the application | net performance vs indexes (e.g. S&P 500) **shown on a clear net basis**, whatever the result |
| 5 years | — (no target) | — |

Manual entry stays acceptable for Accounts at a bank, insurer or employee savings provider for now.

## Non-goals

| # | Non-goal |
|---|---|
| N1 | Placing orders (buy / sell); execution stays with the broker |
| N2 | Deciding on the user's behalf; Cumulus informs, the user decides |
| N3 | Filing tax returns or producing official tax documents |
| N4 | Everyday budgeting (current accounts, spending, categorization) |
| N5 | Physical real estate |
| N6 | Crypto-assets |
| N7 | Several users in the first version |
| N8 | Reproducing Trident's selections (see [Q-008](../planning/open-questions.md)) |

## Smallest useful version

Import the broker's operation report for the **CTO and PEA**, then show the **real cost of every past operation and its current value**.
Covers P2, P3 and part of P5. P1 (consolidated view) is **deliberately left out** despite its priority.

## Constraints

- **Time:** 5–20 h/week, variable. A stable version is hoped for by the end of the year — flexible, not blocking.
- **Budget:** free market data preferred; a paid service is acceptable if free quality is insufficient ([Q-010](../planning/open-questions.md)).
- **Institutions:** stay agnostic — brokers, banks, insurers and providers are roles; today's ones are only examples.
- **Personal data:** requirements unknown ([Q-009](../planning/open-questions.md)).
- **Regulation:** addressed when other users join ([Q-006](../planning/open-questions.md)).

## Risks & unknowns

| # | Risk | Rank |
|---|---|---|
| R1 | Market data: getting price, dividend and FX history reliably, legally and affordably | top 3 |
| R2 | Import formats: each broker exports its own way; formats may change without notice | top 3 |
| R4 | Corporate actions (splits, mergers, spin-offs, stock dividends) distort history if ignored — already seen mishandled on Trident | top 3 |
| R3 | Tax complexity: rules differ per Account type and age, and change with finance laws | — |
| R5 | Ambition: many needs for a solo developer; risk of never shipping the first version | — |
| R6 | Accuracy: a wrong cost or performance shown confidently leads to a bad decision | — |
