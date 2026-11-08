---
id: DOMAIN-GLOSSARY
title: Glossary (ubiquitous language)
status: draft
updated: 2026-11-08
sources: [WS00, WS01, WS02]
---

# Glossary — ubiquitous language

Rules and entry format: [playbook](../method/playbooks/ubiquitous-language.md).
Terms are global until bounded contexts exist; then they move to `contexts/<bc>/glossary.md`.

Owner's rule (WS00 review): prefer **established, recognized financial usage** over invented terms.
Terms marked *agreed WS01* were decided by the owner in [WS01](../workshops/2026-11-08-ws01-glossary/record.md), with the sources listed there; the others are WS00 candidate terms, still to define.

## Holdings

| Term | Definition | Example | Not to be confused with | Synonyms to avoid | Original | Context | Status |
|---|---|---|---|---|---|---|---|
| Asset | Anything of value held by the Investor, whatever its form — *agreed WS01* | Shares, cash, a Livret A balance | Instrument | — | actif, avoirs | (global) | draft |
| Financial wealth | The Investor's complete set of Assets across all Accounts — not a Portfolio nor a set of Portfolios — *agreed WS01* | Everything at the Broker, Bank, Insurer and Employee savings provider | Portfolio | total portfolio, net worth | patrimoine financier | (global) | draft |
| Account | Arrangement with an Institution under which Assets are held, identified by a number, of one Account type; used in the broad sense (covers contracts and plans) — *agreed WS01* | The owner's PEA at Saxo; a life insurance contract | Account type, Portfolio | contract, envelope | compte | (global) | draft |
| Account type | The product an Account belongs to; carries its legal form (account, contract or plan) and its Tax regime — *agreed WS01* | CTO, PEA, life insurance, PER, Livret A, LDDS, PEL, CEL, employee savings plan | Account | envelope | type de compte, enveloppe | (global) | draft |
| Tax regime | Set of tax and social contribution rules attached to an Account type — *agreed WS01* | PEA: taxed at withdrawal, favorable after 5 years | Account type | envelope | régime fiscal, enveloppe fiscale | (global) | draft |
| Portfolio | Grouping of Lots chosen by the Investor, possibly across Accounts; a Lot can belong to several Portfolios — *agreed WS01* | "Trident" (only Lots bought on Trident's advice), "US Tech" | Account, Financial wealth | — | portefeuille | (global) | draft |
| Instrument | Financial instrument: share, ETF unit, bond…; a savings account balance is not one — *agreed WS01* | Meta share, an ETF unit | Asset | security | instrument financier | (global) | draft |
| Position | Quantity of one Instrument held in one Account; the sum of its Lots — *agreed WS01* | 3 Meta shares in the CTO | Lot, Operation | holding, line | position | (global) | draft |
| Lot | Quantity of an Instrument acquired by one Trade (or received through a Corporate action), with its own acquisition cost — *agreed WS01* | 2 Meta shares bought on March 12 at $580 | Position | — | lot | (global) | draft |
| Weighted average acquisition price | Average cost of a Position across its Lots; basis of French capital gains tax on a CTO — the per-Lot view serves monitoring, this one taxation — *agreed WS01 review* | — | Lot acquisition cost | — | prix moyen pondéré (PMP) | (global) | draft |

## Movements

| Term | Definition | Example | Not to be confused with | Synonyms to avoid | Original | Context | Status |
|---|---|---|---|---|---|---|---|
| Operation | Any event recorded on an Account that changes its Positions or cash: Trade, Cash movement, effect of a Corporate action, fee, tax — *agreed WS01* | Weekly purchase of Meta; dividend credited | Corporate action | transaction | opération | (global) | draft |
| Trade | Purchase or sale of an Instrument, executed on a market, with a trade date and a settlement date — *agreed WS01* | Purchase of 1 Meta share | Operation | transaction | achat / vente | (global) | draft |
| Corporate action | Event **decided by the issuer** that affects all holders of an Instrument (dividend, split, merger, spin-off, capital increase, takeover offer); mandatory, voluntary or with options. Its effect on an Account is an Operation — *agreed WS01* | Nvidia stock split | Operation | — | opération sur titres (OST) | (global) | draft |
| Dividend | Distribution decided by the issuer (a Corporate action); its payment on an Account is an Operation with a gross amount, Withholding tax and a net amount — *agreed WS01* | — | — | — | dividende | (global) | draft |
| Withholding tax | Tax deducted at source on a Dividend, typically by the issuer's country; always shown as an Operation cost — *agreed WS01* | 15 % on a US dividend | — | — | retenue à la source | (global) | draft |
| Cash movement | Deposit or withdrawal of cash on an Account — *agreed WS01* | Monthly deposit on the PEA | Trade | — | versement / retrait | (global) | draft |
| Order | Instruction given by the Investor to a Broker to buy or sell an Instrument, with a limit price and a validity; executed, partly executed, expired or cancelled — *raised WS02* | Buy 1 Meta at ≤ $610, valid today | Trade | — | ordre | (global) | draft |
| Account transfer | Moving an Account and its Lots from one Institution to another, keeping its history and Tax regime — *raised WS02* | The owner's PEA moved to Saxo | Cash withdrawal | — | transfert de compte | (global) | draft |
| Discrepancy | Mismatch found by Cumulus between imported records and expectations (unexplained cost, inconsistent figures); the Broker remains the reference — *raised WS02* | Unexplained FX fee on a purchase | — | error | écart | (global) | draft |
| Annual tax statement | Yearly tax document issued by a Broker, also sent to the tax administration — *raised WS02* | IFU from Saxo | Tax return | — | IFU (imprimé fiscal unique) | (global) | draft |
| Operation report | Export of Operations issued by a Broker | `.xlsx` export from Saxo | — | — | rapport d'opérations | (global) | draft |
| Operation cost | Everything an Operation costs besides the price: FX fee, brokerage fee, Withholding tax, taxes, social contributions | — | Price | fees | coût d'opération | (global) | draft |

## Valuation & performance

| Term | Definition | Example | Not to be confused with | Synonyms to avoid | Original | Context | Status |
|---|---|---|---|---|---|---|---|
| Reference currency | Currency in which the Investor measures their Financial wealth | EUR for the owner | Instrument currency | — | devise de référence | (global) | draft |
| Instrument currency | Currency in which an Instrument is quoted | CAD for Constellation Software | Reference currency | — | devise de l'instrument | (global) | draft |
| Currency effect | Share of a gain/loss due to the Instrument currency rising/falling against the Reference currency | — | Performance | — | — | (global) | draft |
| Inflation-adjusted | Amount corrected by the inflation of the Investor's country, in Instrument or Reference currency | — | — | constant currency | corrigé de l'inflation | (global) | draft |
| Gross / Net | Net = after Operation costs, including taxes and social contributions paid and virtually due; exact scope to define | — | — | — | brut / net | (global) | draft |
| Virtually-due tax | Taxes and social contributions that would be due if a Position were sold now ([Q-001](../planning/open-questions.md)) | — | Paid tax | latent tax | fiscalité restant à payer | (global) | draft |
| Annualized performance | To define — performance expressed per year; must always state its basis (gross/net, fees, dividends) | +42 %/yr | Total gain | — | performance annualisée | (global) | draft |
| Index | Market index used as a benchmark for net performance | S&P 500 | — | benchmark | indice | (global) | draft |

## Decisions & strategy

| Term | Definition | Example | Not to be confused with | Synonyms to avoid | Original | Context | Status |
|---|---|---|---|---|---|---|---|
| Investment decision | The Investor's decision about what to buy, sell or reinforce to grow their Assets — *agreed WS02* | Choosing this week's purchase | Fund switch | arbitrage | décision d'investissement | (global) | draft |
| Investment method | The approach an Investor follows to make Investment decisions (cadence, criteria, rules); can change over time — *raised WS02* | Trident method: weekly purchase, POL-001 | Investment plan | strategy | méthode d'investissement | (global) | draft |
| Investment plan | The Investor's dollar-cost averaging settings: frequency, recurring deposit, capital to deploy and deployment period — *raised WS02* | Monthly, 1,000 € deposit, 50,000 € over 20 months | Investment method | — | investissement programmé | (global) | draft |
| Selection | List of qualified Instruments maintained by an Idea source or the Investor, from which purchases are chosen; not a Portfolio — *agreed WS02* | Trident's gold / silver / bronze shares | Portfolio | portfolio of shares | sélection | (global) | draft |
| Estimated return | Forecast yearly return of an Instrument in the Selection; entered manually at first — *raised WS02* | 14 %/yr for Meta | Annualized performance | — | rendement estimé | (global) | draft |
| Fund switch | Moving savings between funds inside a life insurance contract — *agreed WS02* | Euro fund → unit-linked fund | Investment decision | arbitrage (in English) | arbitrage (assurance vie) | (global) | draft |
| Reinforce | To define — buy more of an Instrument already held | "Stock to reinforce: Meta" | — | — | renforcer | (global) | draft |
| Weekly purchase | To define — the Investor's recurring purchase each week | — | — | — | achat hebdomadaire | (global) | draft |
| Overall strategy | To define — the Investor's strategy across all Accounts | — | — | — | stratégie globale | (global) | draft |
| Monitoring | Observing the past and current state of the Financial wealth | — | Investment decision | — | monitorer | (global) | draft |
| Idea source | Provider of selection criteria or investment ideas | Trident, a Guru | — | — | — | (global) | draft |
| Guru | To define — a recognized investor whose analyses or holdings are followed | Joseph Carlson | Idea source | — | gourou | (global) | draft |

## Deprecated

| Term | Replaced by | Since |
|---|---|---|
| Envelope | Account type + Tax regime | WS01 |
| Arbitrage | Investment decision (buy / sell / reinforce) or Fund switch (life insurance); in English "arbitrage" also means risk-free profit from a price gap | WS02 |

Trident-specific terms seen on screenshots (medal, podium, Trident score, discount, estimated return, qualification filter, paused stock, exit) are kept in the [WS00 record](../workshops/2026-11-08-ws00-brief/record.md) only, until Cumulus adopts its own criteria.
