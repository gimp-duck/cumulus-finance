---
id: PLAYBOOK-UBIQUITOUS-LANGUAGE
title: Ubiquitous language maintenance
status: reviewed
updated: 2026-10-17
---

# Playbook — Ubiquitous language (all phases)

**Goal:** build and maintain a precise, shared vocabulary of the domain. The glossary is the backbone of every other document and, later, of the code.
**When:** continuously during every workshop, plus a dedicated review session whenever the glossary has many `draft` entries or conflicts.

## Rules
- One term = one meaning **within a context**. The same word with two meanings is a signal of two bounded contexts (or of confusion) → open question.
- Two words for the same thing → choose one **preferred term**, list the other as a synonym to avoid.
- Definitions use other glossary terms where possible, and say what the term is **not**.
- Business words only; no technical terms (table, API, DTO…).
- Terms coming from another language: keep the `original` form, agree on the English term.

## Steps (dedicated review session)
1. List `draft` terms and terms used in the timeline/stories but missing from the glossary.
2. For each term: ask for a definition **in the owner's words**, then a concrete example and a counter-example.
3. Check conflicts: same term with different meanings in different parts of the timeline? Record where (candidate boundary).
4. Agree on preferred terms and synonyms.
5. Owner marks agreed terms `reviewed`.

## Glossary entry format (`domain/glossary.md`)

| Term | Definition | Example | Not to be confused with | Synonyms to avoid | Original | Context | Status |
|---|---|---|---|---|---|---|---|
| Subscription | Agreement by which a Customer receives … for a period | Annual plan started on 2026-01-01 | Order | Contract, Plan | abonnement | (global) | draft |

`Context` stays `(global)` until bounded contexts exist; then the entry moves to `domain/contexts/<bc>/glossary.md` and the global glossary keeps only shared terms with a link.

## Done when
No term used in a `reviewed` document is missing from, or conflicting with, the glossary.
