---
id: BC-<slug>
title: <Bounded context name>
status: draft
updated: <yyyy-mm-dd>
sources: [WS<NN>]
---

# Bounded Context Canvas — <name>

Adapted from the DDD Crew [Bounded Context Canvas](https://github.com/ddd-crew/bounded-context-canvas) (CC BY-SA 4.0). Used from phase 2.

## Purpose
<What this context is responsible for, in business terms, 2–3 sentences.>

## Strategic classification
| Domain | Business model | Evolution |
|---|---|---|
| core / supporting / generic | revenue / engagement / compliance / cost reduction | genesis / custom built / product / commodity |

## Domain roles
<e.g. Specification model, Execution model, Analysis context, Gateway, Draft context…>

## Inbound communication
| Collaborator | Message (command / event / query) | Relationship |
|---|---|---|

## Outbound communication
| Collaborator | Message (command / event / query) | Relationship |
|---|---|---|

## Ubiquitous language
See [`glossary.md`](glossary.md). Key terms: <…>

## Business decisions
- POL-NNN <rule / policy>

## Assumptions
- ⚠ ASSUMPTION: <…> (Q-NNN)

## Verification metrics
- <how we know the boundary is right: e.g. few cross-context changes>

## Open questions
- Q-NNN <…>
