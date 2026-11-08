---
id: METHOD-CONVENTIONS
title: Documentation conventions
status: reviewed
updated: 2026-10-17
---

# Documentation conventions

## Language

All artifacts are in **American English** (`organize`, `program`, `apartment`). Proper names of external works keep their original spelling (e.g. *DDD Starter Modelling Process*). Business terms coming from another language keep their original form in the glossary (`original` column).

## File and folder names

- `kebab-case`, lowercase, ASCII only: `event-timeline.md`, `order-management/`.
- Workshop folders: `docs/workshops/<yyyy-mm-dd>-ws<NN>-<slug>/` — e.g. `2026-10-20-ws00-brief/`. `NN` is a sequence number across all workshops.
- Decisions: `docs/decisions/<NNNN>-<slug>.md` — e.g. `0001-git-hosting.md`.

## Front-matter

Every living document (in `domain/`, `planning/`, `method/`) starts with YAML front-matter:

```yaml
---
id: DOMAIN-VISION          # stable identifier, never reused
title: Vision
status: draft              # draft | reviewed | validated | deprecated
updated: 2026-10-20        # last meaningful change (ISO date)
sources: [WS00]            # workshops / decisions that produced the content
---
```

| Status | Meaning | Who sets it |
|---|---|---|
| `draft` | Written by the agent or work in progress; may contain assumptions | agent / owner |
| `reviewed` | Read and corrected by the owner; no known error, but may be incomplete | owner |
| `validated` | Owner confirms it is the current truth; changes need a reason | owner only |
| `deprecated` | Kept for history; points to its replacement | owner |

## Identifiers

IDs are stable: never renumbered, never reused. Deleted items are marked `deprecated`, not removed.

| Prefix | Item | Defined in |
|---|---|---|
| `WS<NN>` | Workshop session | `workshops/` |
| `ACT-<NNN>` | Actor (person, role, organization, external system) | `domain/actors.md` |
| `EVT-<NNN>` | Domain event | `domain/event-timeline.md` (later per context) |
| `CMD-<NNN>` | Command / action | event timeline, domain stories |
| `POL-<NNN>` | Policy / business rule ("whenever X then Y") | event timeline, later per context |
| `DS-<NNN>` | Domain story | `domain/stories/` |
| `Q-<NNN>` | Open question / hotspot | `planning/open-questions.md` |
| `ADR-<NNNN>` | Decision record | `decisions/` |
| `REQ-<BC>-<NNN>` | Requirement (phase 3, EARS syntax) | `domain/contexts/<bc>/specs/` |

## Assumptions and uncertainty

Anything not stated by the owner is marked inline: `⚠ ASSUMPTION:` followed by the statement, and linked to an open question (`Q-NNN`).

## Writing style

- Event names: past tense, business language — `Order Placed`, not `OrderCreatedEvent` or `save order`.
- Commands: imperative — `Place Order`.
- Prefer tables and lists to prose; one idea per line.
- Diagrams in Mermaid; every diagram has a short text explanation next to it.
- Link, don't duplicate: refer to the glossary or another document by relative link.
