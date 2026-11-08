---
id: WS01
title: Ubiquitous language — core holding and operation terms
date: 2026-11-08
playbook: ubiquitous-language.md
participants: [owner, Claude]
---

# WS01 — Ubiquitous language: core holding and operation terms

> Append-only. Corrections made after the workshop go to a later record or to the living documents, not here.

## Agenda & inputs
- Playbook: [`ubiquitous-language`](../../method/playbooks/ubiquitous-language.md)
- Inputs: [WS00 record](../2026-11-08-ws00-brief/record.md), [glossary](../../domain/glossary.md) (25 `draft` terms), [Q-012](../../planning/open-questions.md), [Q-013](../../planning/open-questions.md)
- Owner's rule (WS00 review): adopt **established, recognized financial usage**; the agent brings sourced definitions, the owner decides.
- Agenda:
  1. Cluster A — holdings: account, portfolio, envelope, position, instrument, asset (Q-012)
  2. Cluster B — movements: operation, transaction, corporate action, dividend (Q-013)
  3. Remaining `draft` terms, if time allows
- Out of scope: Trident-specific terms.

## Raw notes

### Research (agent, before the session)

No official AMF lexicon entry was found online for "compte-titres", "portefeuille" or "opération sur titres"; the findings below come from regulatory texts, standards bodies and established broker / bank usage.

| Term | Established usage found | Sources |
|---|---|---|
| Securities account (*compte-titres*) | Account on which financial securities are registered in the holder's name, kept by an account keeper (*teneur de compte-conservateur*); usually paired with a cash account. The PEA is a securities account + a cash account under a specific tax regime. | [Banque de France](https://www.banque-france.fr/fr/statistiques/credit/conservation-de-titres-2025-q2), [AMF nomenclature of securities accounts](https://www.amf-france.org/sites/institutionnel/files/doctrine/Instruction/Nomenclature%20des%20comptes%20de%20titres%20financiers%20et%20leurs%20regles%20de%20fonctionnement.pdf), [Invesse](https://invesse.fr/lexique/enveloppe-fiscale/) |
| Tax envelope (*enveloppe fiscale*) | Retail-finance term (not regulatory): a legal and tax framework that hosts investments and sets their tax, inheritance and availability rules; it yields nothing by itself. Usually lists CTO, PEA, life insurance, PER. | [Invesse](https://invesse.fr/lexique/enveloppe-fiscale/), [Goodvest](https://www.goodvest.fr/lexique/enveloppe-fiscale), [Auguste Patrimoine](https://www.auguste-patrimoine.fr/blog/difference-enveloppe-fiscale-produit-financier) |
| Portfolio | Collection of an investor's investments; not tied to one account — one broker allows several portfolios under one account. | [UniCredit](https://support.unicredit.pl/en/support/solutions/articles/80001196819-what-is-the-difference-between-investment-account-and-portfolio-), [La langue française](https://www.lalanguefrancaise.com/dictionnaire/definition/gestion-de-portefeuille) |
| Holding / position | Holding = what is owned in an account; position = sometimes the same, sometimes a trade not yet settled (varies by broker). | [Zerodha](https://support.zerodha.com/category/trading-and-markets/corporate-actions/general/articles/difference-between-holdings-and-positions), [UniCredit](https://support.unicredit.pl/en/support/solutions/articles/80001196819-what-is-the-difference-between-investment-account-and-portfolio-) |
| Corporate action (*opération sur titres*, OST) | Event initiated by the issuer that affects its securities and their holders: dividend payment, capital increase, takeover / exchange offer, split… Classified as mandatory, voluntary, or mandatory with options (ISO 15022 / 20022). | [Crédit Agricole](https://www.credit-agricole.fr/particulier/conseils/magazine/tout-un-mag/qu-est-ce-qu-une-operation-sur-titres-ost.html), [Fortuneo](https://www.fortuneo.fr/faq/bourse/informations-generales/qu-est-ce-qu-une-operation-sur-titres-ost-et-comment-puis-je-etre-au-courant-de-ces-operations), [La finance pour tous](https://www.lafinancepourtous.com/pratique/placements/actions-3/les-operations-sur-titres), [ISO 20022 MT567 field](https://iso20022.org/15022/uhb/mt567-2-field-20c.htm), [Interactive Brokers glossary](https://ibkb.interactivebrokers.com/fr/glossary/1450) |

### Cluster A — holdings (proposed to the owner)

| # | Term proposed | Proposed definition | Decision asked |
|---|---|---|---|
| A1 | Account | Contract with an Institution under which Assets are held, identified by a number, of one Account type | Does it also cover a life insurance contract and an employee savings plan? |
| A2 | Account type (+ Tax regime) | The product an Account belongs to (CTO, PEA, life insurance, PER, Livret A…); its Tax regime is the set of rules attached to it | Adopt Account type + Tax regime, with *enveloppe fiscale* as the original form, instead of "Envelope"? |
| A3 | Portfolio | (a) one Account, (b) all the Investor's holdings, or (c) a grouping of Positions chosen by the Investor, possibly across Accounts | Which meaning? |
| A4 | Position | Quantity of one Instrument held in one Account, with its acquisition cost | Adopt; avoid "holding" and "line" (*ligne*)? |
| A5 | Instrument | Financial instrument (shares, ETF units, bonds…); a savings account balance is not one | Adopt? |
| A6 | Asset | Anything of value held by the Investor (*avoirs*), whatever its form | Keep as the umbrella term? |

Owner's answers:

| # | Answer |
|---|---|
| A1 | Distinguish account and contract; maybe find an **umbrella term** |
| A2 | Yes — Account type + Tax regime; *enveloppe fiscale* kept as the original form |
| A3 | OK for (c): a grouping of Positions chosen by the Investor, possibly across Accounts |
| A4 | OK — Position; avoid "holding" and "line" |
| A5 | OK — Instrument |
| A6 | OK — Asset as the umbrella term |
| A3 challenge | **A Position can belong to several Portfolios at once** (e.g. "Trident" and "US Tech") |

Agent follow-ups (asked with cluster B):
- A1 umbrella term options: (1) **Account** in the broad sense used by aggregators and ISO 20022, with the legal form (account / contract / plan) carried by the Account type; (2) **Contract** — legally accurate (every account rests on an account agreement) but unusual for a Livret A; (3) owner's own term. Agent recommends (1).
- A3: can a Portfolio hold only **part** of a Position (e.g. only the Meta shares bought on Trident's advice)?
- A3: is "all of the Investor's holdings" a special Portfolio, or a separate term (e.g. *Financial wealth*, from *patrimoine financier*, the term used by Banque de France / INSEE)?

### Cluster B — movements (proposed to the owner)

| # | Term proposed | Proposed definition | Decision asked |
|---|---|---|---|
| B1 | Operation | Any event recorded on an Account that changes its Positions or cash: trade, cash movement, effect of a corporate action, fee, tax — matches French banking usage and the owner's intuition | Adopt as the umbrella term? |
| B2 | Trade | Purchase or sale of an Instrument, executed on a market (trade date, settlement date); "transaction" avoided as ambiguous (broker apps use it for everything) | Adopt "Trade"; avoid "transaction"? |
| B3 | Corporate action | Event **decided by the issuer** that affects all holders of an Instrument (dividend, split, merger, spin-off, capital increase, takeover offer); mandatory, voluntary or with options. Its effect on the Investor's Account is an Operation | Adopt the issuer-side / account-side split? |
| B4 | Dividend | Distribution decided by the issuer (a corporate action); its payment on the Account is an Operation: gross amount, withholding tax, net amount | Adopt? |
| B5 | Cash movement | Deposit or withdrawal of cash on an Account (*versement* / *retrait*) | Adopt? |

Agent challenge on B4: should foreign **withholding tax** on dividends (e.g. 15 % on a US dividend) count as an Operation cost (P5)?

Owner's answers:

| # | Answer |
|---|---|
| A1 umbrella | OK — **Account** in the broad sense; the legal form (account / contract / plan) is a property of the Account type |
| A3 partial | **Yes** — a Portfolio can hold only part of a Position (e.g. only the Meta shares bought on Trident's advice) |
| A3 whole | Not just a Portfolio or a set of Portfolios: it is the user's **complete financial wealth** → separate term |
| B1–B5 | OK on all proposed definitions |
| B4 challenge | Yes — withholding taxes must appear, "to always offer a very transparent view of the products" |

Agent follow-up (consequence of A3 partial): if a Portfolio can hold part of a Position, it groups something finer than a Position. Established term proposed: **Lot** (*tax lot*): the quantity of an Instrument acquired by one Trade (or received through a corporate action), with its own acquisition cost; a Position is the sum of its Lots. Caveat: French tax rules compute capital gains on a CTO / PEA with the **weighted average acquisition price** (*prix moyen pondéré*, PMP), not per lot — the per-lot view would serve monitoring, not tax.

Owner's answer: **Lot adopted** as described.

Agenda item 3 (remaining `draft` terms) postponed: they will be defined as they appear in the Big Picture EventStorming.

## Decisions taken
- Adopted terms (owner's choices, based on the sourced established usage above): Asset, Financial wealth, Account (broad sense), Account type, Tax regime, Portfolio, Instrument, Position, Lot, Operation, Trade, Corporate action, Dividend, Withholding tax, Cash movement.
- "Envelope" deprecated → Account type + Tax regime; *enveloppe fiscale* kept as the original form.
- Avoided terms: "transaction" (ambiguous), "holding" and "line" (use Position).
- A Position belongs to one Account; a Portfolio groups Lots, possibly across Accounts; a Lot can belong to several Portfolios.
- A Corporate action is decided by the issuer; its effect on an Account is an Operation.
- Withholding tax is always shown as an Operation cost (transparency).
- Agent-added term, not discussed: Weighted average acquisition price (French CTO capital gains basis), kept as a candidate.

## Open questions raised
- None new. Answered: [Q-012](../../planning/open-questions.md) (portfolio vs account vs envelope), [Q-013](../../planning/open-questions.md) (operation vs transaction).

## Living documents updated
| Document | Change |
|---|---|
| `domain/glossary.md` | Reorganized in 4 sections; 15 terms agreed (marked *agreed WS01*, status still `draft` until owner review); new terms Financial wealth, Account, Account type, Tax regime, Lot, Weighted average acquisition price, Trade, Withholding tax, Cash movement; Envelope deprecated |
| `planning/open-questions.md` | Q-012 and Q-013 answered; Q-001 wording uses Account |
| `domain/vision.md` | Wording aligned: Financial wealth, Account type |
| `domain/actors.md` | Wording aligned: Financial wealth, Account type |
| `planning/roadmap.md` | WS01 done; WS02 Big Picture EventStorming next |
| `docs/README.md`, `workshops/README.md` | Status and index updated |

## Next step
WS02 — Big Picture EventStorming, using the agreed vocabulary: the timeline from "Trade executed" to "Arbitrage decided".
