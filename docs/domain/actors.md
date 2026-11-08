---
id: DOMAIN-ACTORS
title: Actors
status: draft
updated: 2026-11-08
sources: [WS00, WS01, WS02]
---

# Actors

People, roles, organizations and external systems that take part in the domain.
Institutions are modeled as **roles**: the named organizations are today's examples only.

| ID | Name | Type | Description | Goals / interests | Status |
|---|---|---|---|---|---|
| ACT-001 | Investor | person role | Person who holds financial assets and uses Cumulus — today only the owner | Monitor their Financial wealth precisely; make independent Investment decisions to grow their Assets | draft |
| ACT-002 | Relative / community member | person role | Possible future user (3-year goal); who pays is undecided ([Q-005](../planning/open-questions.md)) | Same as Investor | draft |
| ACT-003 | Broker | organization | Holds securities accounts (e.g. CTO, PEA) with stocks, ETFs and cash; issues operation reports — e.g. Saxo | — | draft |
| ACT-004 | Bank | organization | Holds regulated savings and savings plans (e.g. Livret A, LDDS, savings account, PEL, CEL) — e.g. La Banque Postale | — | draft |
| ACT-005 | Insurer | organization | Holds life insurance and PER; may be a subsidiary of a bank group, but a separate entity — e.g. La Banque Postale's insurance subsidiary | — | draft |
| ACT-006 | Employee savings provider | organization | Holds employee savings — e.g. Axa, maybe others | — | draft |
| ACT-007 | Idea source | organization / person role | Provides selection criteria and investment ideas — mainly Trident today; also Gurus (e.g. Joseph Carlson's YouTube videos and analyses) | — | draft |
| ACT-008 | AI assistant | candidate role | Owner's idea: analysis, projection, decision support; never decides (N2). Scope open ([Q-004](../planning/open-questions.md)) | — | draft |
| ACT-009 | Market data source | external system | ⚠ ASSUMPTION: provides price, dividend and FX history ([Q-010](../planning/open-questions.md)) | — | draft |
| ACT-010 | Inflation statistics source | external system | ⚠ ASSUMPTION: provides inflation per user country ([Q-002](../planning/open-questions.md)) | — | draft |
| ACT-011 | Tax authority | organization | ⚠ ASSUMPTION: sets tax and social contribution rules per Account type ([Q-001](../planning/open-questions.md)); receives the Annual tax statement from the Broker | — | draft |
| ACT-012 | Issuer | organization | Company or fund manager that issues an Instrument; decides Corporate actions (dividends, splits, mergers…) and publishes financial results | — | draft |

`Type`: person role · organization · external system.
