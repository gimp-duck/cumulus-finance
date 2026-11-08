---
id: PLAYBOOK-BRIEF
title: Project brief workshop
status: reviewed
updated: 2026-10-17
---

# Playbook — Project brief (Align)

**Goal:** capture *why* the project exists, *for whom*, and *what success looks like*, before exploring *how* the business works.
**Phase:** 1 — Align. Usually the first workshop (WS00); re-run partially whenever the vision drifts.
**Duration:** 1–3 sessions. It is fine to stop after any section and resume later.

## Inputs
- Anything the owner already has: notes, emails, existing tools, screenshots, competitor names, previous attempts.
- Existing `domain/vision.md` and `planning/open-questions.md` if this is a re-run.

## Facilitation rules
- Ask **one theme at a time**; let the owner brain-dump first, then ask follow-ups.
- Ask for **concrete examples** ("tell me about the last time this happened").
- Separate **problem** from **solution**: when the owner describes a feature, ask "what problem does this solve, for whom?".
- Capture vocabulary as it appears (candidate glossary terms) without defining it yet.
- Record uncertainty as open questions, not as facts.

## Steps

### 1. Context & origin
- What is this project in one sentence? Where does the name come from?
- What exists today (tools, processes, a previous system)? What is wrong with it?
- What triggered the project now?

### 2. Problem
- Which problems are we solving? For each: who suffers, how often, what is the cost, what workaround exists today?
- Rank the problems by importance.

### 3. Actors & stakeholders
- Who uses the system, directly and indirectly? Who pays? Who benefits? Who could block it?
- Which organizations and external systems are involved?

### 4. Goals & success
- What must be true in 1 year / 3 years / 5 years for the project to be a success?
- How would we measure it (observable signals, not features)?

### 5. Scope boundaries
- **Non-goals:** what the project explicitly will *not* do (at least for now).
- What is the smallest version that would already be useful?

### 6. Constraints & risks
- Business, legal/regulatory, budget, time, data, organizational constraints. *(Not technical choices — those come later.)*
- Biggest risks and unknowns.

### 7. Wrap-up
- Read back a 5-line summary; ask the owner to correct it.
- List candidate terms and open questions.
- Propose the next workshop (usually Big Picture EventStorming).

## Outputs
| Output | Location |
|---|---|
| Workshop record | `workshops/<date>-ws<NN>-brief/record.md` |
| Vision (problem, goals, non-goals, constraints, success measures) | `domain/vision.md` |
| Actors | `domain/actors.md` |
| Candidate terms (name + raw definition, status `draft`) | `domain/glossary.md` |
| Open questions | `planning/open-questions.md` |

## Done when
- Every section has at least a first answer or an explicit open question.
- The owner agrees with the 5-line summary.
