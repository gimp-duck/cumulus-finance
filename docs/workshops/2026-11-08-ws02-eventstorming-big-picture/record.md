---
id: WS02
title: Big Picture EventStorming — Cumulus Finance
date: 2026-11-08
playbook: eventstorming-big-picture.md
participants: [owner, Claude]
---

# WS02 — Big Picture EventStorming: Cumulus Finance

> Append-only. Corrections made after the workshop go to a later record or to the living documents, not here.

## Agenda & inputs
- Playbook: [`eventstorming-big-picture`](../../method/playbooks/eventstorming-big-picture.md)
- Inputs: [WS00 record](../2026-11-08-ws00-brief/record.md), [WS01 record](../2026-11-08-ws01-glossary/record.md), [vision](../../domain/vision.md), [actors](../../domain/actors.md), [glossary](../../domain/glossary.md) (16 agreed terms), [open questions](../../planning/open-questions.md) (Q-001…Q-014)
- Scope: the whole domain — the Investor's world, including what happens outside Cumulus (issuers, brokers, tax) — not only the first version.
- Agenda: 1. Chaotic exploration · 2. Enforce the timeline · 3. Pivotal events · 4. People & systems · 5. Hotspots · 6. Opportunities & priorities · 7. Emerging boundaries

## Raw notes

### 1. Chaotic exploration

Owner's first brain-dump (original French → English, raw, unordered):

| # | Original | English (raw) |
|---|---|---|
| 1 | compte ouvert | Account Opened |
| 2 | action achetée | Share Bought |
| 3 | action vendue | Share Sold |
| 4 | etf acheté | ETF Bought |
| 5 | etf vendu | ETF Sold |
| 6 | performance du portefeuille consultée | Portfolio Performance Viewed |
| 7 | performance d'un produit particulier consultée | Single Product Performance Viewed |
| 8 | dividende versé | Dividend Paid |
| 9 | split d'action réalisé | Stock Split Done |
| 10 | cours de l'action consultée | Share Price Viewed |
| 11 | choix de l'achat hebdomadaire effectué | Weekly Purchase Chosen |
| 12 | prix d'achat/vente choisi | Buy/Sell Price Chosen |
| 13 | portée de l'ordre choisie (jour/date limite) | Order Validity Chosen (day / until date) |
| 14 | versement effectué | Cash Deposited |
| 15 | impôt déclaré | Tax Declared |
| 16 | opération hebdomadaire saisie | Weekly Operation Entered |
| 17 | action hebdomadaire sélectionnée | Weekly Share Selected |
| 18 | meilleur compte d'achat sélectionné (CTO/PEA) | Best Purchase Account Selected (CTO / PEA) |
| 19 | actions qualifiées à l'achat classées | Qualified Shares Ranked |
| 20 | position fermée | Position Closed |
| 21 | PEA a atteint 5 ans | PEA Reached 5 Years |
| 22 | action/ETF ajouté ou retiré d'un portefeuille | Share/ETF Added to or Removed from a Portfolio |
| 23 | portefeuille créé | Portfolio Created |
| 24 | versement effectué sur épargne salariale | Employee Savings Deposit Made |
| 25 | épargne salariale débloquée avant la période de blocage (mariage, naissance, achat résidence principale, etc.) | Employee Savings Released Early (marriage, birth, main home purchase, etc.) |
| 26 | action analysée | Share Analyzed |
| 27 | graphiques de performance consultés | Performance Charts Viewed |

Agent observations (to discuss, not yet decided):
- #6, #7, #10, #27 ("… viewed") are information needs rather than facts that change the domain; candidate **read models** feeding decisions.
- #12 and #13 describe an **Order** (price limit, validity) placed before a Trade — "Order Placed" and its outcomes (executed, expired, cancelled, partly executed) are missing; "Order" is not in the glossary yet.
- #2–#5 are probably one event ("Trade Executed", buy/sell, any Instrument).
- #11 vs #17: same event?
- #18 hints at a rule (e.g. PEA eligibility) → candidate policy.
- ⚠ Glossary conflict: in French life insurance, *arbitrage* means switching savings between funds inside a contract — different from the owner's "Arbitrage" (deciding what to buy / sell).

Second wave: the agent proposed missing events (order lifecycle, currency conversion, fees, settlement, dividend lifecycle, other corporate actions, price / FX / inflation updates, custody fees, interest, social contributions, withdrawals, closures, realized gains / losses, tax paid, employee savings release at maturity, life insurance contract and surrender, selection states, Guru publications, operation report export / import, discrepancy found). Owner: **"add all your proposals"**.

Owner's answers:
- **PEA closure:** a PEA can be closed at any time; closing it after 5 years gives tax exemptions.
- **What triggers the week:** a post published on the community forum.
- ⚠ **Method caveat:** the current weekly routine is specific to the Trident method; "nothing says I will always follow the same method" → the timeline must not hard-code the weekly Trident cycle.
- Remark 1 (… viewed = information needs / read models, not events): **agreed**.
- Remark 2 (#11 and #17 are the same event): **yes, duplicate**.
- Remark 3 (two meanings of *arbitrage*): **yes, the terms must be distinguished** to avoid confusion.

Agent note: in current French rules, a withdrawal before 5 years generally closes the PEA (with exceptions), while after 5 years partial withdrawals are allowed → ⚠ to verify, raised as a hotspot.

### 2. Enforce the timeline

Draft ordered timeline proposed by the agent (provisional IDs, kept stable once consolidated). Duplicates merged; Trident-specific names made method-neutral; "… viewed" items moved to read models.

**Lane A — Account life** (Investor, Institutions)

| ID | Event | Merged from / note |
|---|---|---|
| EVT-001 | Account Opened | #1; includes a life insurance contract and an employee savings plan (Account in the broad sense) |
| EVT-002 | Cash Deposited | #14, #24 (employee savings deposit) |
| EVT-003 | PEA Reached 5 Years | #21 |
| EVT-004 | Cash Withdrawn | includes life insurance surrender (*rachat*) |
| EVT-005 | Employee Savings Released at Maturity | |
| EVT-006 | Employee Savings Released Early | #25 (marriage, birth, main home purchase…) |
| EVT-007 | Account Closed | PEA: any time; tax exemptions after 5 years |

**Lane B — Investment decision** (Investor, Idea sources)

| ID | Event | Merged from / note |
|---|---|---|
| EVT-010 | Community Post Published | triggers the week under the Trident method |
| EVT-011 | Guru Analysis Published | |
| EVT-012 | Guru Position Disclosed | |
| EVT-013 | Instrument Spotted | |
| EVT-014 | Instrument Analyzed | #26 |
| EVT-015 | Instrument Qualified | criteria met |
| EVT-016 | Qualified Instruments Ranked | #19 |
| EVT-017 | Instrument Paused | |
| EVT-018 | Instrument Removed from Selection | Trident "exit" |
| EVT-019 | Instrument Selected for Purchase | #11 = #17; weekly cadence is Trident-specific |
| EVT-020 | Purchase Account Selected | #18 (CTO or PEA) → candidate policy (PEA eligibility) |
| EVT-021 | Portfolio Created | #23 |
| EVT-022 | Lot Added to Portfolio / Lot Removed from Portfolio | #22, reworded with WS01 terms |

**Lane C — Order & trade** (Investor, Broker)

| ID | Event | Merged from / note |
|---|---|---|
| EVT-030 | Order Placed | #12 (limit price) and #13 (validity) are attributes of the Order |
| EVT-031 | Order Partially Executed | |
| EVT-032 | Trade Executed | #2–#5 (buy / sell, share or ETF) |
| EVT-033 | Order Expired | |
| EVT-034 | Order Cancelled | |
| EVT-035 | Currency Converted | |
| EVT-036 | Brokerage Fee Charged | |
| EVT-037 | FX Fee Charged | |
| EVT-038 | Trade Settled | |
| EVT-039 | Position Closed | #20 |

**Lane D — Issuer & market** (issuers, market data, statistics)

| ID | Event | Merged from / note |
|---|---|---|
| EVT-040 | Price Updated | |
| EVT-041 | FX Rate Updated | |
| EVT-042 | Inflation Published | |
| EVT-043 | Dividend Announced | |
| EVT-044 | Ex-Dividend Date Passed | |
| EVT-045 | Dividend Paid | #8 |
| EVT-046 | Withholding Tax Deducted | |
| EVT-047 | Stock Split Done | #9 |
| EVT-048 | Merger Done | |
| EVT-049 | Spin-off Done | |
| EVT-050 | Capital Increase Offered | |
| EVT-051 | Takeover Offer Launched | |

**Lane E — Account charges & income** (Institutions)

| ID | Event | Merged from / note |
|---|---|---|
| EVT-060 | Custody Fee Charged | |
| EVT-061 | Interest Paid | Livret A, euro fund |
| EVT-062 | Social Contributions Charged | |

**Lane F — Tax** (Investor, Tax authority)

| ID | Event | Merged from / note |
|---|---|---|
| EVT-070 | Capital Gain Realized / Capital Loss Realized | |
| EVT-071 | Tax Declared | #15 |
| EVT-072 | Tax Paid | |

**Lane G — Record keeping** (Investor, Broker, Cumulus)

| ID | Event | Merged from / note |
|---|---|---|
| EVT-080 | Operation Report Exported | by the Broker |
| EVT-081 | Operation Report Imported | into Cumulus |
| EVT-082 | Operation Entered Manually | #16, generalized (not only weekly) |
| EVT-083 | Discrepancy Found | e.g. unknown fee, Broker vs Cumulus mismatch |

**Read models** (information needs, not events): Financial wealth / Portfolio performance (#6), Instrument performance (#7), Instrument price (#10), Performance charts (#27).

Candidate terms raised: Order (*ordre*), Investment method (*méthode d'investissement*), Selection (*sélection*).

Agent challenges on the draft: (1) is the purchase amount decided with the instrument, or separately? (2) can a Position close without a sale (cash takeover, delisting, merger)? (3) missing or misplaced lanes?

Owner's answers:
1. **How the purchase is chosen under Trident:**
   - Trident maintains a set of shares (decisions can add / remove / pause shares) — the owner calls it a "portfolio of shares".
   - Trident then forecasts an **estimated return per year** for each of these shares.
   - The app then proposes to buy **the share with an estimated return ≥ 10 %/yr on which the owner is the least exposed**.
   - The amount invested is up to the owner, but Trident **proposes an amount** based on the strategy the owner gave it. Example: the owner chooses a weekly or monthly purchase, makes a monthly savings deposit of 1,000 €, and has 50,000 € of existing capital to invest → Trident adds the monthly deposit and 1/20 of the existing capital, so as to invest progressively over the first 20 months.
2. "Closing a position" meant **selling everything**.
3. Lanes: "a priori it's fine".

Agent notes:
- ⚠ Term clash: Trident's "portfolio of shares" is not a Portfolio in the WS01 sense (a grouping of the Investor's Lots); it is a list of qualified Instruments → candidate term **Selection**.
- The "strategy given to Trident" matches the established practice of **dollar-cost averaging** (*investissement programmé*): a recurring amount plus a capital deployed over a period → candidate term **Investment plan**.
- Two candidate policies (both specific to the current Investment method):
  - POL-001 — Whenever a purchase is due, propose the Instrument with an estimated return ≥ 10 %/yr on which the Investor is the least exposed.
  - POL-002 — Proposed purchase amount = recurring deposit + existing capital ÷ deployment period (e.g. 1,000 € + 50,000 € ÷ 20).
- "Least exposed": measured by amount bought, current value, or share of Financial wealth? → hotspot.
- A Position can still end through a Corporate action (cash takeover, delisting, merger) even if the owner meant "sell everything" → hotspot.

Events added to lane B:

| ID | Event | Note |
|---|---|---|
| EVT-023 | Investment Plan Defined / Investment Plan Changed | frequency, recurring deposit, capital to deploy, deployment period |
| EVT-024 | Estimated Return Updated | by the Idea source, per Instrument in the Selection |
| EVT-025 | Purchase Amount Proposed | POL-002 |
| EVT-026 | Purchase Amount Decided | by the Investor |

Lane B order becomes: Investment Plan Defined → … → Instrument Qualified → Estimated Return Updated → Instrument Selected for Purchase (POL-001) → Purchase Amount Proposed (POL-002) → Purchase Amount Decided → Purchase Account Selected → (lane C) Order Placed.

Step 2 closed: lanes accepted by the owner.

Owner's answers to the step 2 notes:
- **Selection** adopted for Trident's "portfolio of shares" (list of qualified Instruments).
- **"Least exposed"**: the owner enters the amount invested in each share, and the app proposes the one with the **smallest amount invested** → exposure = amount invested, not current value.
- Position ended by a Corporate action: "true, I hadn't thought of it" → hotspot.

### 3. Pivotal events

Agent proposal, **accepted by the owner** ("OK"):

| Pivotal event | Why "the world is different" after it |
|---|---|
| ★ EVT-023 Investment Plan Defined | frames every following purchase decision |
| ★ EVT-019 Instrument Selected for Purchase | the decision is made |
| ★ EVT-032 Trade Executed | money is committed; the Lot exists |
| ★ EVT-081 Operation Report Imported | the Broker's facts enter Cumulus |
| ★ EVT-039 Position Closed | the gain or loss becomes real |
| ★ EVT-007 Account Closed | end of a Tax regime |

### 4. People & systems

Draft proposed by the agent (to be confirmed):

| Lane | Events | Triggered by |
|---|---|---|
| A. Account life | Account Opened, Cash Deposited, Cash Withdrawn, Account Closed | ACT-001 Investor, with the Institution (ACT-003…006) |
| A. Account life | PEA Reached 5 Years | time |
| A. Account life | Employee Savings Released at Maturity / Early | time / ACT-001 Investor (early release case) with ACT-006 |
| B. Decision | Community Post Published, Guru Analysis Published, Guru Position Disclosed | ACT-007 Idea source |
| B. Decision | Instrument Qualified / Paused / Removed from Selection, Qualified Instruments Ranked, Estimated Return Updated | ACT-007 Idea source **today**; ACT-001 Investor (maybe ACT-008 AI assistant) once independent (P7) |
| B. Decision | Instrument Spotted, Instrument Analyzed | ACT-001 Investor or ACT-007 Idea source |
| B. Decision | Investment Plan Defined, Purchase Amount Decided, Purchase Account Selected, Portfolio Created, Lot Added / Removed | ACT-001 Investor |
| B. Decision | Instrument Selected for Purchase, Purchase Amount Proposed | policies POL-001, POL-002 (today run by the Idea source's app) |
| C. Order & trade | Order Placed, Order Cancelled | ACT-001 Investor |
| C. Order & trade | Order Executed / Partially Executed / Expired, Currency Converted, fees, Trade Settled | ACT-003 Broker |
| C. Order & trade | Position Closed | follows a sale of all Lots (or a Corporate action) |
| D. Issuer & market | Dividend Announced, Ex-Dividend Date Passed, Stock Split / Merger / Spin-off Done, Capital Increase Offered, Takeover Offer Launched | **Issuer** — new actor |
| D. Issuer & market | Dividend Paid, Withholding Tax Deducted | Issuer, via ACT-003 Broker |
| D. Issuer & market | Price Updated, FX Rate Updated | ACT-009 Market data source |
| D. Issuer & market | Inflation Published | ACT-010 Inflation statistics source |
| E. Charges & income | Custody Fee Charged, Interest Paid, Social Contributions Charged | the Institution (ACT-003…006) |
| F. Tax | Capital Gain / Loss Realized | follows Trade Executed (sale) |
| F. Tax | Tax Declared, Tax Paid | ACT-001 Investor, ACT-011 Tax authority |
| G. Record keeping | Operation Report Exported | ACT-003 Broker (on the Investor's request?) |
| G. Record keeping | Operation Report Imported, Operation Entered Manually | ACT-001 Investor |
| G. Record keeping | Discrepancy Found | ACT-001 Investor or Cumulus? |

Agent questions: new actor **Issuer**; who triggers "Discrepancy Found"; who requests the Operation report export.

Owner's answers:
- Observation: the **Issuer can publish its financial results**, which may matter for the weekly choice of share → new event EVT-052 Financial Results Published (lane D, Issuer), feeding lane B (Instrument Analyzed, Estimated Return Updated).
- 1. Issuer added as an actor: **agreed**.
- 2. Discrepancy Found: **Cumulus reports it** → candidate policy POL-003: whenever Operations are imported, check that every cost is explained and that records match; report any Discrepancy.
- 3. Operation report export: **the Investor downloads it on demand**.

Step 4 closed.

### 5. Hotspots

Agent walked the timeline backwards (from Account Closed) then forwards. Hotspots already open elsewhere: Q-001 (virtually-due tax), Q-008 (own reading of Trident), Q-010 (market data), Q-011 (corporate actions). New hotspots proposed (provisional IDs):

| ID | Where | Hotspot |
|---|---|---|
| Q-015 | B — Decision | Two meanings of *arbitrage* (life insurance switch vs buy/sell decision): which term for which? |
| Q-016 | A — Account Closed | Does a withdrawal before 5 years close a PEA (current rule, exceptions)? To verify |
| Q-017 | C — Position Closed | A Position can end through a Corporate action (cash takeover, delisting, merger): how is it closed and valued? |
| Q-018 | G — Operation Report Imported | Does the Broker's report contain enough to rebuild the real cost (FX rate, FX fee, brokerage fee, withholding tax, settlement date)? |
| Q-019 | G — Operation Report Imported | The same Operations imported twice, or overlapping report periods: how are duplicates recognized? |
| Q-020 | G — Discrepancy Found | When Cumulus and the Broker disagree, which is the reference? |
| Q-021 | B — Purchase Amount Proposed | "Amount invested" for exposure: fees included? What happens after a partial sale? |
| Q-022 | B — Estimated Return Updated | Once independent of Trident, how is an estimated return computed, and from which data (results, multiples, growth)? |
| Q-023 | A — Account life | Missing event? A securities transfer between Brokers (e.g. moving a PEA) keeps the Lots and their history |
| Q-024 | F — Tax | Missing event? The Broker's annual tax statement (*IFU*): a source for paid taxes and realized gains? |

Candidate opportunities (💡) proposed by the agent:
- 💡 Explain every cost of every Operation automatically (POL-003).
- 💡 Import any Broker's report (role-agnostic).
- 💡 Run the Selection, estimated return and purchase proposal with the Investor's own criteria (P7).
- 💡 Show "what if I sold today" with virtually-due tax per Account type.
- 💡 Rebuild the history of a Position across a Corporate action or a transfer.

Owner's answers on the hotspots:

| ID | Owner's answer |
|---|---|
| Q-015 | "Help me decide": *arbitrage* fits the life insurance meaning better — which term for the buy/sell decision? |
| Q-016 | "Check it, but I think so" |
| Q-017 | "I don't know, help me" |
| Q-018 | Yes — the Broker's report contains enough to rebuild the real cost |
| Q-019 | There should always be an identifier per Operation; but as a safety net, plan a de-duplication mechanism (maybe issuer + date + amount? not decided) |
| Q-020 | The Broker is supposed to be right; Cumulus only reports the problem |
| Q-021 | Good question, needs thinking; no intuition yet |
| Q-022 | Not on the agenda; at first, the estimated return will be **entered manually** |
| Q-023 | Had not thought of it, but must be handled; for a PEA a transfer can bring extra fees. The owner **has already transferred their PEA** |
| Q-024 | The IFU is provided by the Broker and is useful for the tax return. Saxo already sends everything to the tax administration; the owner only **checks the pre-filled values** |

Owner asked: prioritize among all hotspots (Q-001 to Q-024) or only the new ones?

Agent research and proposals:
- **Q-016 verified** (sources: [Crédit Agricole](https://www.credit-agricole.fr/particulier/conseils/magazine/tout-un-mag/avant-et-apres-la-loi-pacte-ce-qui-change-pour-votre-pea.html), [INC](https://www.inc-conso.fr/content/loi-pacte-et-pea-plan-depargne-en-actions), [Ramify](https://www.ramify.fr/pea/retrait), [Neofa](https://neofa.com/fr/pea/retrait-pea)): before 5 years, any withdrawal, even partial, closes the PEA, except PACTE-law cases (dismissal, invalidity, early retirement of the holder or spouse / partner; business creation cited by some sources). After 5 years, partial withdrawals no longer close it and deposits remain possible. Gains after 5 years are exempt from income tax but bear social contributions. ⚠ Sources disagree on the current social contribution rate (17.2 % vs 18.6 %): rates change, which confirms R3.
- **Q-015 proposal:** English "arbitrage" has a third meaning in finance (risk-free profit from a price gap) → avoid the word in English artifacts. Adopt **Fund switch** (original: *arbitrage*, life insurance meaning) and **Investment decision** (original: *décision d'investissement*) for the owner's buy / sell / reinforce decision. "Arbitrage" deprecated.
- **Q-017 proposal** (⚠ tax treatment to verify): a Position ended by a Corporate action is closed by Operations derived from that action:
  - cash takeover → Lots removed, cash credited at the offer price, treated like a sale (gain / loss realized);
  - share-for-share merger / exchange → Lots replaced by Lots of the new Instrument, acquisition cost carried over (in France, exchanges generally benefit from a tax deferral);
  - delisting / bankruptcy → value falls to zero; when the loss becomes realized is a tax question.
- New events from Q-023 / Q-024: EVT-008 Account Transferred (Lots and history kept), EVT-009 Transfer Fee Charged, EVT-073 Annual Tax Statement Issued (IFU, by the Broker), EVT-074 Pre-filled Tax Return Checked (by the Investor).

The owner found the request unclear; the agent restated it as three short questions.

Owner's answers:
- Q-015 proposal (**Fund switch** / **Investment decision**, "arbitrage" deprecated): **yes**.
- Q-017 proposal (the Corporate action generates the Operations that end the Position): **yes** (tax treatment still to verify).

### 6. Opportunities & priorities

Owner's choices:

| Most painful hotspots | Most valuable opportunities |
|---|---|
| Q-001 Virtually-due tax: current age or target horizon? | 💡 A — Explain every cost of every Operation automatically |
| Q-009 Personal data: where, and who accesses it? | 💡 B — Import any Broker's report |
| Q-010 Market data: free or paid sources? | 💡 D — "What would I get if I sold today", taxes included |
| Q-021 "Amount invested": fees included? After a partial sale? | 💡 E — Keep a Position's history across a split, merger or Account transfer |

Not chosen: opportunity C (own selection criteria) — consistent with P7 being priority 7 and Q-022 being deferred.

### 7. Emerging boundaries

Candidate boundaries noted by the agent (not designed, input for phase 2):

| Candidate | Evidence |
|---|---|
| Operation records (lanes G, C results, E, A) | Own language (operation report, import, Operation, Lot, discrepancy); pivotal ★ Operation Report Imported; facts come from the Broker, who is the reference (Q-020) |
| Instrument & market reference (lane D) | Language of the Issuer and markets (corporate action, price, FX rate, inflation); actors Issuer, Market data source, Inflation source; issuer-side vs account-side split agreed in WS01 |
| Valuation & performance (read models) | Language of currency effect, inflation-adjusted, gross / net, annualized performance; consumes records + reference data; no events of its own |
| Taxation (lane F) | Language of Tax regime, PMP, realized gain, social contributions, IFU; actor Tax authority; pivotal ★ Position Closed, ★ Account Closed; rules change often (R3) |
| Investment decision (lane B) | Language of Selection, estimated return, Investment plan; **actor changes over time** (Idea source today → Investor / AI assistant tomorrow); policies POL-001, POL-002 are method-specific; pivotal ★ Investment Plan Defined, ★ Instrument Selected for Purchase |
| Outside Cumulus: Order execution (lane C orders) | Happens at the Broker (non-goal N1); Cumulus only sees its results through the Operation report |

## Decisions taken
- Timeline organized in 7 lanes (A–G); 6 pivotal events agreed by the owner.
- "… viewed" items are read models, not events (owner agreed).
- The current Investment method (Trident) is not hard-coded: its rules are policies (POL-001, POL-002) — owner's caveat.
- Terms: Selection, Investment decision, Fund switch adopted; "Arbitrage" deprecated (Q-015).
- Issuer added as an actor; Cumulus reports Discrepancies, the Broker remains the reference (POL-003).
- A Corporate action that ends a Position generates the Operations that close it (POL-004; tax treatment to verify).
- Priorities: hotspots Q-001, Q-009, Q-010, Q-021; opportunities A, B, D, E.
- Agent addition, not discussed: EVT-027 Fund Switched placed in lane A (⚠ ASSUMPTION).

## Open questions raised
| ID | Status |
|---|---|
| Q-015 Two meanings of *arbitrage* | answered |
| Q-016 PEA withdrawal before 5 years | answered (verified) |
| Q-017 Position ended by a Corporate action | open (principle agreed) |
| Q-018 Broker report sufficient for real cost | answered (to confirm on a real export) |
| Q-019 De-duplication of imported Operations | open |
| Q-020 Reference when Cumulus and Broker disagree | answered |
| Q-021 "Amount invested" for exposure | open — top pain |
| Q-022 Computing an estimated return | open — deferred |
| Q-023 Securities transfer between Brokers | answered |
| Q-024 Annual tax statement (IFU) | answered |

Priorities raised: Q-001, Q-009 (now high), Q-010, Q-021. Details: [`planning/open-questions.md`](../../planning/open-questions.md).

## Living documents updated
| Document | Change |
|---|---|
| `domain/event-timeline.md` | Filled: Mermaid overview, 62 events in 7 lanes, 6 pivotal, policies POL-001…004, read models, 6 candidate boundaries |
| `domain/actors.md` | ACT-012 Issuer added; wording "Investment decision" |
| `domain/glossary.md` | Added Investment decision, Investment method, Investment plan, Selection, Estimated return, Fund switch, Order, Account transfer, Discrepancy, Annual tax statement; Arbitrage deprecated |
| `domain/vision.md` | Wording "Investment decision" instead of "arbitrage" |
| `planning/open-questions.md` | Q-015 to Q-024 added; Q-001, Q-009 raised to high |
| `planning/roadmap.md` | WS02 done; WS03 domain story next |
| `docs/README.md`, `workshops/README.md` | Status and index updated |

## Next step
WS03 — Domain story on the first version's flow: "Operation report imported → real cost and current value of each Operation". It turns the top opportunities A and B into one concrete scenario and will surface Q-018, Q-019 and Q-021 on real data. Phase 1 exit criteria still missing after that: owner validation of the vision, and answers to the hotspots that block decomposition.
