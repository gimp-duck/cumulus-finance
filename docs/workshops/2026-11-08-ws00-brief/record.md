---
id: WS00
title: Project brief — Cumulus Finance
date: 2026-11-08
playbook: brief.md
participants: [owner, Claude]
---

# WS00 — Project brief: Cumulus Finance

> Append-only. Corrections made after the workshop go to a later record or to the living documents, not here.

## Agenda & inputs
- Playbook: [`brief`](../../method/playbooks/brief.md)
- Inputs: none yet (first workshop; `domain/vision.md` and `planning/open-questions.md` are empty)
- Agenda: 1. Context & origin · 2. Problem · 3. Actors & stakeholders · 4. Goals & success · 5. Scope boundaries · 6. Constraints & risks · 7. Wrap-up

## Raw notes

### 1. Context & origin

Owner's answers (translated from French):

- **One sentence:** "A way to manage my financial portfolios (stocks or other): know the current and past state of my portfolios in fine detail, and help me make arbitrage decisions in order to grow my assets."
- **Name:** *Cumulus* is the cloud type; semantically close to "accumulate" (the app's purpose is to make portfolios grow). The meteorological meaning evokes **forecasting**. Less important: a cloud also hints the app lives "in the cloud".
- **What exists today:**
  - Each brokerage / investment platform has its own website or app, with its own differences and limits.
  - Platforms can export operation reports (e.g. `.xlsx`).
  - Investor-oriented platforms exist to manage portfolios and guide arbitrage thinking; they have good ideas worth reusing (to be discussed).
  - Problem: the owner has "a sharper vision than what is offered" for managing a portfolio.
- **Trigger:** the maturity of AI tools for software development assistance.

Reference shared by the owner: 4 screenshots of **Trident**, a paid community subscription site for investors. Features the owner finds very useful:

| Screen | What it shows (as observed on the screenshots) |
|---|---|
| *Achat* (Purchase) | Picks which stock to buy in the weekly purchase ("stock to reinforce", amount to buy). Per stock: Trident rank (medal), price, 7-day change, estimated return (%/yr), amount already bought, metric (EPS / FCF), growth, two multiples ("Mult. V", "Mult. A"). Half-donut of amount bought per stock. "Reinforce without adding capital" option. Simple / Advanced mode. |
| *Portefeuille* (Portfolio) | Gain/loss per position (amount, %, %/yr, vs S&P 500). Positions table: amount invested, current value, dividends, total gains (amount, %), holding duration (days), annualized performance. Positions / Transactions tabs. Portfolio selector ("Manuel"). |
| *Podium Trident* | Community-selected stocks ranked by medal (gold / silver / bronze) and by discount; also "paused", "recent exits", "unranked" stocks; next three deep analyses. |
| *Filtres Trident* | Qualification filters vs S&P 500 average: sales growth ≥ 7%/yr, EPS growth ≥ 12%/yr, Trident score ≥ 12/20, held by ≥ 2 "Gurus" (56 qualified out of 4,184). |

Candidate terms heard (not defined yet): portfolio (*portefeuille*), arbitrage, asset (*actif*), brokerage platform (*plateforme de courtage*), operation report, position, transaction, weekly purchase, reinforce (*renforcer*), estimated return, discount (*décote*), medal, podium, Trident score, Guru, qualification filter, paused stock, exit (*sortie*), annualized performance, dividend.

Follow-ups (agent questions → owner answers):

- **Portfolio scope today:**
  - Saxo: 2 portfolios — *CTO* (ordinary securities account) and *PEA* — holding stocks, ETFs and cash.
  - La Banque Postale: *assurance vie* (life insurance), *LDDS*, *Livret A*, *compte sur livret*, *PEL*, *CEL*, *PER*.
  - Employee savings (*épargne salariale*).
- **Current practice:** follows the Trident method every week. No other tool besides the Saxo app. Enters operations **manually** in Trident, because Trident's import does not support the Saxo format.
- **"A sharper vision" — what is missing:**
  - Per **instrument**: clearly see its evolution, with the owner's buys/sells highlighted.
  - Display in constant currency, in EUR, or in inflation-adjusted currency.
  - Highlight **operation costs**: FX fees, brokerage fees, taxes and social contributions; gross vs net view.
  - The same at **portfolio** level.
  - Correct annualization of performance (gross / net).
  - From a **reference currency** (EUR for the owner): see the share of gain/loss due to the instrument's currency rising/falling against the reference currency.
- **For whom:** exclusively the owner for now. If personal use proves convincing, possibly opened to relatives later, and maybe to a wider community circle.

Step 1 closed: first answers to every question.

Candidate terms added: instrument, ETF, cash (*liquidités*), envelope / account type (CTO, PEA, life insurance, LDDS, Livret A, savings account, PEL, CEL, PER), employee savings, operation, reference currency, constant currency, inflation-adjusted, operation cost, FX fee, brokerage fee, tax, social contributions, gross / net, currency effect.

### 2. Problem

Draft problem list proposed by the agent from the step 1 answers (to be corrected and ranked by the owner):

| # | Draft problem | Source |
|---|---|---|
| P1 | Holdings are spread across Saxo, La Banque Postale and employee savings, with no consolidated view | ⚠ ASSUMPTION: inferred from the asset list, not stated as a problem |
| P2 | Operations are entered twice (Saxo, then manually in Trident) because Trident cannot import the Saxo format | stated |
| P3 | No per-instrument history showing the owner's buys/sells | stated |
| P4 | No currency views (instrument currency / EUR / inflation-adjusted) and no split of gain/loss between currency effect and instrument performance | stated |
| P5 | Operation costs (FX, brokerage, taxes, social contributions) are not visible; no gross vs net view | stated |
| P6 | Annualized performance is not computed correctly (gross / net) | stated |
| P7 | Arbitrage decision support is insufficient | ⚠ ASSUMPTION: from the one-sentence goal; nothing missing was named yet |

Owner's answers:

- **P1 and P7 confirmed.** P7: arbitrage is currently done as a community with Trident; the owner wants an **independent** system.
- **Ranking:** the order P1 → P7 above is correct.
- **Frequency / cost / workaround** (given once for the top problems): at every weekly purchase; cost = lost time and unseen fees; no workaround today.
- **P6 reframed:** "it is not necessarily wrong, but I don't know what I am looking at": net? gross? management fees deducted? dividends included? → the problem is the **unclear basis** of displayed performance figures, not (proven) wrong figures.
- **P5:** covers taxes and social contributions already paid **and** those still virtually due (if sold). For a PEA: use its current age, or project to the > 5-year target? Not thought through yet; probably also applies to life insurance and other products.
- **P4:** four display currencies: instrument currency; instrument currency adjusted for inflation; reference currency (EUR for the owner); reference currency adjusted for inflation. Inflation depends on the user (France for the owner).
- **New need (operation level):** when looking at a past operation, see what it cost at purchase (price, the various fees, etc.) and its value now or at a chosen date (dividends included, other possible fees, taxes / social contributions, etc.), in any of the P4 display currencies.

Updated problem list:

| # | Problem | Priority |
|---|---|---|
| P1 | No consolidated view of holdings spread across Saxo, La Banque Postale and employee savings | 1 |
| P2 | Saxo operations are re-entered manually in Trident (no import) | 2 |
| P3 | No per-instrument history highlighting the owner's buys/sells; no per-operation view of cost at purchase vs value now or at a date | 3 |
| P4 | No display in instrument / reference currency, each optionally inflation-adjusted; no split of currency effect vs instrument performance | 4 |
| P5 | Operation costs (FX, brokerage, taxes, social contributions — paid and virtually due) not visible; no gross vs net view | 5 |
| P6 | Basis of displayed performance figures is unclear (gross/net, fees, dividends) | 6 |
| P7 | Arbitrage depends on the Trident community; no independent decision support | 7 |

Step 2 closed, except the meaning of "independent" (P7), asked again at the start of step 3.

### 3. Actors & stakeholders

Draft actor list proposed by the agent (to be corrected by the owner):

| Actor | Kind | Role (draft) |
|---|---|---|
| Owner (investor) | person | Sole user today |
| Relatives | person | Possible future users |
| Community circle | group | Possible future users |
| Saxo | organization / external system | Broker holding CTO and PEA; source of operations and reports |
| La Banque Postale | organization / external system | Bank holding life insurance, regulated savings, PEL/CEL, PER |
| Employee savings provider | organization / external system | ⚠ ASSUMPTION: unknown provider name |
| Trident | organization / external system | Paid community method; current source of stock selection and arbitrage ideas |
| Market data source | external system | ⚠ ASSUMPTION: prices, dividends, FX rates are needed for P3–P6 |
| Inflation statistics source | external system | ⚠ ASSUMPTION: needed for inflation-adjusted views (P4) |
| Tax authority (French tax rules) | organization | ⚠ ASSUMPTION: rules for taxes and social contributions (P5) |

Owner's answers:

- **P7 "independent"** = a mix of the three: own selection criteria, own data, being able to stop the Trident subscription one day. At first the owner will keep taking Trident criteria into account, "until the day I can break free from it".
- **Employee savings provider:** Axa, maybe others.
- **Trident** is not the only source of arbitrage ideas, but the main one. Others are useful, e.g. YouTube videos or analyses by **Gurus** such as Joseph Carlson.
- **Institutions must stay agnostic:** Saxo, La Banque Postale and Axa are only today's examples → model them as roles (broker, bank, insurer, employee savings provider), not as named organizations.
- **Who pays / who benefits** if opened to others: too early to say.
- **Possible blockers:** Trident's terms of use — blocking only if Trident were kept as the reference. The owner sees no other blocker.
- **Owner's idea:** "maybe an AI model could be an actor? I don't know to what extent AI can be integrated into decision-making, projection into the future, analysis, etc."

Agent notes:
- The AI idea is recorded as a candidate actor role (analysis / projection / decision support), not as a technical choice; its responsibilities and limits are an open question.
- ⚠ Possible blocker not raised by the owner: regulation of investment advice if decision support is offered to people other than the owner. To be discussed in step 6.

Updated actor list (draft):

| Actor | Kind | Role |
|---|---|---|
| Investor (owner) | person | Sole user today |
| Relatives, then community circle | persons / group | Possible future users; who pays is not decided |
| Broker | external organization (role) | Holds securities accounts (e.g. CTO, PEA); source of operations and reports — today Saxo |
| Bank | external organization (role) | Holds regulated savings, PEL/CEL, etc. — today La Banque Postale |
| Insurer | external organization (role) | ⚠ ASSUMPTION: holds life insurance and PER — today through La Banque Postale |
| Employee savings provider | external organization (role) | Holds employee savings — today Axa, maybe others |
| Idea source | external organization / person (role) | Source of selection criteria and arbitrage ideas — today mainly Trident; also Gurus (e.g. Joseph Carlson) |
| AI assistant | candidate role | Owner's idea: analysis, projection, decision support — scope unknown |
| Market data source | external system | ⚠ ASSUMPTION: prices, dividends, FX rates |
| Inflation statistics source | external system | ⚠ ASSUMPTION |
| Tax authority | organization | ⚠ ASSUMPTION: tax and social contribution rules |

Step 3 closed.

Late answer (asked during step 4): life insurance and PER are held by the **bank's insurance subsidiary** — separate entities within the same group → the insurer is a distinct role from the bank.

### 4. Goals & success

Owner's answers:

- **Investor vs tool:** the investor's goal is to grow their assets. The tool is there to **monitor** (observe the past) and to give the user the means to make the right future choices within their **overall strategy**.
- **1 year:** no manual entry any more (import only); the owner knows the real cost of every past operation.
- **3–5 years** (horizon not split): the owner makes arbitrage choices without Trident; other users use the application.
- **Success signals:** number of manual entries; fees discovered that the owner did not know about; the owner's **net** performance vs indexes (e.g. S&P 500).

Agent challenges, asked at the start of step 5:
- Which of the two 3–5 year goals is 3 years and which is 5?
- The "net performance vs indexes" signal measures investment success: is it a success criterion for Cumulus (beat the index), or for its ability to show the comparison on a clear net basis?
- "Import only" for every holding, including regulated savings and employee savings: do these providers export operations?

Candidate terms added: monitoring, overall strategy, index (benchmark).

Step 4 closed (pending the three challenges above).

### 5. Scope boundaries

Answers to the step 4 challenges:
- Both goals ("arbitrage without Trident", "other users") are **3-year** goals. No 5-year target.
- The net-performance-vs-index signal: Cumulus succeeds by **showing the comparison on a clear net basis**, whatever the result.
- "Import only" does not apply to the bank and the insurer for now: **manual entry stays acceptable** there.

Candidate non-goals proposed by the agent — owner: **all excluded**, nothing to add.

| # | Non-goal |
|---|---|
| N1 | Placing orders (buy / sell) from Cumulus; execution stays with the broker |
| N2 | Deciding on the user's behalf; Cumulus informs, the user decides |
| N3 | Filing tax returns or producing official tax documents |
| N4 | Everyday budgeting (current accounts, spending, categorization) |
| N5 | Physical real estate |
| N6 | Crypto-assets |
| N7 | Several users in the first version |
| N8 | Reproducing Trident's selections |

**Smallest useful version** (agent proposal, accepted by the owner): import the broker's operation report for the CTO and the PEA, then see the real cost of every past operation and its current value. Covers P2, P3 and part of P5; P1 (consolidated view, priority 1) is **deliberately not** in it.

Agent notes:
- ⚠ Tension: N8 (no reproduction of Trident's selections) vs "at first I keep taking Trident criteria into account". Can the owner record their own reading of Trident (e.g. a medal per stock) as their own data? → open question.
- N2 is consistent with the AI assistant idea: an AI may analyze or project, never decide.

Step 5 closed.

### 6. Constraints & risks

Owner's answers — constraints:
- **Time:** no allocated time; between 0 and 20 h/week (corrected to 5–20 in step 7), very variable. Hopes for a **stable version before the end of the year**.
- **Budget:** paying for market data was not considered; doing without would be better, but it depends on the quality of free information. A paid subscription can be considered if needed.
- **Personal data:** "a real reflection to be had, I don't know."
- **Regulation:** to be addressed when needed.

Candidate risks proposed by the agent (R1–R6). The owner ranked the 3 most serious; the others were neither removed nor ranked:

| # | Risk | Rank |
|---|---|---|
| R1 | Market data: getting price, dividend and FX history reliably, legally and affordably | top 3 |
| R2 | Import formats: each broker exports its own way, and formats may change without notice | top 3 |
| R4 | Corporate actions (splits, mergers, spin-offs, stock dividends) distort history if ignored | top 3 |
| R3 | Tax complexity: rules differ per envelope and age, and change with finance laws | — |
| R5 | Ambition: many needs for a solo developer; risk of never shipping the first version | — |
| R6 | Accuracy: a wrong cost or performance shown confidently leads to a bad decision | — |

Evidence: the owner has already seen a stock split mishandled on Trident (not on Saxo).

Agent challenge: "before the end of the year" — 2026 (about 7 weeks from today, at 0–20 h/week) or 2027? This bears directly on R5.

Step 6 closed (pending the deadline challenge).

### 7. Wrap-up

5-line summary read back to the owner (draft):
1. Cumulus Finance is a personal tool to monitor all of one's financial holdings, past and present, in fine detail, and to support independent arbitrage decisions within an overall strategy.
2. It addresses: no consolidated view; manual re-entry of broker operations; no per-instrument / per-operation real cost and value; no currency / inflation views nor currency-effect split; hidden costs and no gross / net view; unclear basis of performance figures; dependence on Trident.
3. Today the owner is the only user; relatives then a community may follow within 3 years. Institutions are roles (broker, bank, insurer, employee savings provider, idea source); an AI assistant is a candidate role.
4. Success in 1 year: no manual entry for broker accounts, real cost of every past operation known; in 3 years: arbitrage without Trident, other users. Signals: manual entries, fees discovered, net performance vs indexes shown on a clear basis.
5. First version: import broker reports for the CTO and PEA, then show the real cost and current value of each operation. Non-goals N1–N8. Top risks: market data, import formats, corporate actions. 0–20 h/week, stable version hoped for by year-end, free data preferred.

Owner's corrections to the summary:
- Time: **5 to 20 h/week** (not 0–20).
- "End of the year" is **not a blocking deadline**; the owner is very flexible.

The rest of the summary was not corrected → agreed.

## Decisions taken
- Institutions (broker, bank, insurer, employee savings provider, idea source) are modeled as **roles**; today's organizations are examples only — owner wants Cumulus to stay agnostic.
- Non-goals N1–N8 excluded — owner's choice.
- Smallest useful version = broker import for CTO and PEA + real cost and current value of each operation; P1 deliberately left out — smallest scope that removes the weekly re-entry.
- Manual entry stays acceptable for bank and insurer holdings for now.
- The AI assistant is a candidate role, never a decision maker (N2).

No ADR: these are domain scope decisions, recorded in [`domain/vision.md`](../../domain/vision.md).

## Open questions raised

| ID | Question | Status |
|---|---|---|
| Q-001 | Virtually-due tax horizon for PEA / life insurance | open |
| Q-002 | Inflation index per user country | open |
| Q-003 | Meaning of an "independent" arbitrage system | answered during WS00 |
| Q-004 | AI assistant role and accountability | open |
| Q-005 | Who pays / benefits if opened to others | open |
| Q-006 | Investment-advice regulation for other users | open |
| Q-007 | Life insurance / PER held by bank or insurer | answered during WS00 |
| Q-008 | Recording own reading of Trident vs N8 / terms of use | open |
| Q-009 | Personal data location and access | open |
| Q-010 | Free vs paid market data | open |
| Q-011 | Knowing and applying corporate actions | open |
| Q-012 | Portfolio vs account vs envelope | open (raised at consolidation) |
| Q-013 | Operation vs transaction | open (raised at consolidation) |
| Q-014 | Employee savings: import or manual entry | open (raised at consolidation) |

Details: [`planning/open-questions.md`](../../planning/open-questions.md).

## Living documents updated
| Document | Change |
|---|---|
| `domain/vision.md` | Filled: one sentence, context, problems P1–P7, goals, non-goals N1–N8, smallest useful version, constraints, risks R1–R6 |
| `domain/actors.md` | ACT-001 to ACT-011 added (roles, not named institutions) |
| `domain/glossary.md` | 25 candidate terms added (status `draft`) |
| `planning/open-questions.md` | Q-001 to Q-014 added (Q-003, Q-007 answered) |
| `planning/roadmap.md` | WS00 done; WS01 next |
| `docs/README.md` | Next step and status table updated |
| `workshops/README.md` | WS00 added to the index |

## Next step
WS01 — Big Picture EventStorming: the end-to-end timeline from "operation executed at the broker" to "arbitrage decided". Answer Q-012 and Q-013 first, since they name the core work objects of the timeline.
