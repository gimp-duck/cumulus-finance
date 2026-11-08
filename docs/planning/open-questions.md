---
id: PLANNING-OPEN-QUESTIONS
title: Open questions & hotspots
status: draft
updated: 2026-11-08
sources: [WS00, WS01, WS02]
---

# Open questions & hotspots

Every uncertainty, conflict or hotspot gets an ID and stays here until answered. Answered questions are kept (status `answered`) with a link to where the answer lives.

| ID | Question | Raised in | Priority | Blocks | Status | Answer / link |
|---|---|---|---|---|---|---|
| Q-001 | Virtually-due tax on a PEA / life insurance: use the Account's current age, or project to its holding-period target (> 5 years for PEA)? Which other products are affected? | WS00 | high (WS02 top pain) | net view (P5), opportunity D | open | |
| Q-002 | Which inflation index for a user's country (for France: INSEE CPI, eurozone HICP, other)? | WS00 | low | inflation-adjusted views (P4) | open | |
| Q-003 | What does an "independent" arbitrage system mean? | WS00 | — | — | answered | Own criteria + own data + able to drop Trident, gradually — [vision](../domain/vision.md) |
| Q-004 | What role could an AI assistant play (analysis, projection, decision support), and who stays accountable for a decision? | WS00 | medium | — | open | |
| Q-005 | Who pays and who benefits if Cumulus is opened to relatives or a community? | WS00 | low | 3-year goal | open | "Too early to say" |
| Q-006 | Does decision support offered to people other than the owner fall under investment-advice regulation? | WS00 | low | 3-year goal | open | |
| Q-007 | Are life insurance / PER held by the bank or by an insurer? | WS00 | — | — | answered | Bank group's insurance subsidiary → distinct Insurer role — [actors](../domain/actors.md) |
| Q-008 | While still following Trident, can the owner record their own reading of Trident (e.g. a medal per stock) without breaching N8 or Trident's terms of use? | WS00 | medium | P7 | open | |
| Q-009 | Personal data: where may financial data live, and who may access it — now and once other users join? | WS00 | high (WS02 top pain) | — | open | |
| Q-010 | Market data: can free sources give sufficient quality for price, dividend and FX history, or is a paid service needed? | WS00 | high (WS02 top pain) | first version (current value) | open | |
| Q-011 | How are corporate actions (splits, mergers, spin-offs, stock dividends) known and applied to history? | WS00 | high | first version (correct history) | open | |
| Q-012 | Portfolio vs account vs envelope: is "portfolio" the broker account (CTO, PEA), the envelope type, or a grouping chosen by the Investor? | WS00 (consolidation) | high | WS01 vocabulary | answered | WS01: Account (broad) of an Account type with a Tax regime; Portfolio = grouping of Lots chosen by the Investor; Financial wealth = everything — [glossary](../domain/glossary.md) |
| Q-013 | Operation vs transaction: same thing? Which term is preferred? | WS00 (consolidation) | medium | WS01 vocabulary | answered | WS01: Operation is the umbrella (any event on an Account); Trade = purchase / sale; "transaction" avoided — [glossary](../domain/glossary.md) |
| Q-014 | Employee savings: must they be imported, or is manual entry acceptable as for bank and insurer holdings? | WS00 (consolidation) | low | — | answered | Manual entry acceptable for now (WS00 review) — [vision](../domain/vision.md) |
| Q-015 | Two meanings of *arbitrage* (life insurance switch vs buy / sell decision): which term for which? | WS02 | — | — | answered | Fund switch / Investment decision; "Arbitrage" deprecated — [glossary](../domain/glossary.md) |
| Q-016 | Does a withdrawal before 5 years close a PEA? | WS02 | — | — | answered | Yes, except PACTE-law cases (dismissal, invalidity, early retirement…); after 5 years partial withdrawals are allowed — [WS02 record](../workshops/2026-11-08-ws02-eventstorming-big-picture/record.md) |
| Q-017 | A Position can end through a Corporate action (cash takeover, delisting, merger): how is it closed and valued? | WS02 | medium | correct history (opportunity E) | open | Principle agreed: POL-004 in the [timeline](../domain/event-timeline.md); tax treatment still to verify |
| Q-018 | Does the Broker's report contain enough to rebuild the real cost (FX rate, FX fee, brokerage fee, withholding tax, settlement date)? | WS02 | — | — | answered | Yes, per the owner; ⚠ to confirm on a real export |
| Q-019 | Same Operations imported twice, or overlapping report periods: how are duplicates recognized? | WS02 | medium | import (opportunity B) | open | Owner: each Operation should carry an identifier; plan a safety de-duplication key (issuer + date + amount?) |
| Q-020 | When Cumulus and the Broker disagree, which is the reference? | WS02 | — | — | answered | The Broker; Cumulus only reports the Discrepancy (POL-003) |
| Q-021 | "Amount invested" used for exposure (POL-001): fees included? What happens after a partial sale? | WS02 | high (WS02 top pain) | POL-001 | open | No intuition yet |
| Q-022 | Once independent of Trident, how is an estimated return computed, and from which data? | WS02 | low | P7 | open | Deferred: estimated return entered manually at first |
| Q-023 | Securities transfer between Brokers (e.g. a PEA moved): must it be handled? | WS02 | — | — | answered | Yes; the owner already transferred their PEA; may bring fees → EVT-008, EVT-009 |
| Q-024 | Is the Broker's annual tax statement (IFU) a source for paid taxes and realized gains? | WS02 | — | — | answered | Yes; the Broker sends it to the tax administration, the owner checks the pre-filled values → EVT-073, EVT-074 |

`Priority`: high · medium · low. `Blocks`: what cannot progress without the answer (e.g. "phase 2 decomposition").
