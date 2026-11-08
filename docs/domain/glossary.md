---
id: DOMAIN-GLOSSARY
title: Glossary (ubiquitous language)
status: draft
updated: 2026-11-08
sources: [WS00]
---

# Glossary — ubiquitous language

Rules and entry format: [playbook](../method/playbooks/ubiquitous-language.md).
Terms are global until bounded contexts exist; then they move to `contexts/<bc>/glossary.md`.

All entries below are **candidate terms** from WS00: raw definitions from the owner's words, or "to define" when the term was only used. A glossary review will settle them.
Owner's rule (WS00 review): prefer **established, recognized financial usage** over invented terms.

| Term | Definition | Example | Not to be confused with | Synonyms to avoid | Original | Context | Status |
|---|---|---|---|---|---|---|---|
| Asset | To define — anything of value the Investor holds, in any form | Shares, cash, Livret A balance | Instrument | — | actif | (global) | draft |
| Portfolio | To define — used by the owner for each broker account (CTO, PEA) | "2 portfolios at Saxo" | Envelope, account ([Q-012](../planning/open-questions.md)) | — | portefeuille | (global) | draft |
| Envelope | ⚠ Agent-proposed term: account type with its own tax rules | CTO, PEA, life insurance, PER, Livret A, LDDS, PEL, CEL | Portfolio ([Q-012](../planning/open-questions.md)) | account type | enveloppe | (global) | draft |
| Instrument | To define — a tradable security held in a Portfolio | Meta share, an ETF | Asset | security | instrument | (global) | draft |
| Position | To define — the holding of one Instrument in a Portfolio | Nvidia, 1 purchase, 627 € invested | Operation | line | position | (global) | draft |
| Operation | To define — owner's view: any event that changes a Portfolio, broader than a transaction (buy, sell, but also a stock split or a dividend payment); to confirm against established usage ([Q-013](../planning/open-questions.md)) | Weekly purchase of Meta; Nvidia stock split | Transaction | — | opération | (global) | draft |
| Operation report | Export of Operations issued by a Broker | `.xlsx` export from Saxo | — | — | rapport d'opérations | (global) | draft |
| Operation cost | Everything an Operation costs besides the price: FX fee, brokerage fee, taxes, social contributions | — | Price | fees | coût d'opération | (global) | draft |
| Reference currency | Currency in which the Investor measures their wealth | EUR for the owner | Instrument currency | — | devise de référence | (global) | draft |
| Instrument currency | Currency in which an Instrument is quoted | CAD for Constellation Software | Reference currency | — | devise de l'instrument | (global) | draft |
| Currency effect | Share of a gain/loss due to the Instrument currency rising/falling against the Reference currency | — | Performance | — | — | (global) | draft |
| Inflation-adjusted | Amount corrected by the inflation of the Investor's country, in Instrument or Reference currency | — | — | constant currency | corrigé de l'inflation | (global) | draft |
| Gross / Net | Net = after Operation costs, including taxes and social contributions paid and virtually due; exact scope to define | — | — | — | brut / net | (global) | draft |
| Virtually-due tax | Taxes and social contributions that would be due if a Position were sold now ([Q-001](../planning/open-questions.md)) | — | Paid tax | latent tax | fiscalité restant à payer | (global) | draft |
| Annualized performance | To define — performance expressed per year; must always state its basis (gross/net, fees, dividends) | +42 %/yr | Total gain | — | performance annualisée | (global) | draft |
| Dividend | To define | — | — | — | dividende | (global) | draft |
| Corporate action | Event on an Instrument that changes Positions without an Investor decision | Stock split, merger, spin-off, stock dividend | Transaction (possibly a kind of Operation, [Q-013](../planning/open-questions.md)) | — | opération sur titres | (global) | draft |
| Arbitrage | To define — a decision about what to buy, sell or reinforce to grow Assets | Choosing the weekly purchase | — | — | arbitrage | (global) | draft |
| Reinforce | To define — buy more of an Instrument already held | "Stock to reinforce: Meta" | — | — | renforcer | (global) | draft |
| Weekly purchase | To define — the Investor's recurring purchase each week | — | — | — | achat hebdomadaire | (global) | draft |
| Overall strategy | To define — the Investor's strategy across all Envelopes | — | — | — | stratégie globale | (global) | draft |
| Monitoring | Observing the past and current state of holdings | — | Arbitrage | — | monitorer | (global) | draft |
| Idea source | Provider of selection criteria or arbitrage ideas | Trident, a Guru | — | — | — | (global) | draft |
| Guru | To define — a recognized investor whose analyses or holdings are followed | Joseph Carlson | Idea source | — | gourou | (global) | draft |
| Index | Market index used as a benchmark for net performance | S&P 500 | — | benchmark | indice | (global) | draft |

Trident-specific terms seen on screenshots (medal, podium, Trident score, discount, estimated return, qualification filter, paused stock, exit) are kept in the [WS00 record](../workshops/2026-11-08-ws00-brief/record.md) only, until Cumulus adopts its own criteria.
