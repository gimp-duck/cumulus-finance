---
id: PLAYBOOK-ES-BIG-PICTURE
title: Big Picture EventStorming workshop
status: reviewed
updated: 2026-10-17
---

# Playbook — Big Picture EventStorming (Discover)

**Goal:** explore the *whole* business domain as a timeline of domain events, reveal its hotspots and the first natural boundaries.
**Phase:** 1 — Discover. Method by Alberto Brandolini; vocabulary per the DDD Crew
[EventStorming glossary](https://github.com/ddd-crew/eventstorming-glossary-cheat-sheet).
**Duration:** several sessions; one session per region of the timeline is fine.

## Text notation (replaces sticky notes)

| Sticky | Text form | Example |
|---|---|---|
| 🟧 Domain event | `EVT-NNN` + past-tense name | `EVT-012 Invoice Sent` |
| 🟨 Actor (small yellow) | `ACT-NNN` link | `ACT-003 Accountant` |
| 🩷 External system | `ACT-NNN` (type: external system) | `ACT-007 Bank` |
| 🟥 Hotspot | `Q-NNN` link, short question | `Q-021 What if the invoice is disputed?` |
| ▮ Pivotal event | `★` before the name | `★ EVT-020 Contract Signed` |
| ─ Swimlane | section heading or `lane` column | `Billing` |
| 🟩 Opportunity | `💡` + short idea | `💡 automatic reminder` |

## Steps

### 1. Chaotic exploration
Ask the owner to list **every event they can think of**, in any order, in business language and past tense. Do not structure yet. Push for quantity: "what happens before that? after? what else can happen?"

### 2. Enforce the timeline
Order events chronologically. Where several flows happen in parallel, split into **swimlanes**. Remove duplicates; when two names describe the same fact, keep one and note the synonym (glossary).

### 3. Pivotal events
Identify the few events after which "the world is different" (often handovers of responsibility, money or commitment). Mark them `★`. They delimit **phases** of the timeline and are first hints of boundaries.

### 4. People & systems
For each event or group of events: who/what triggers or reacts? Add actors and external systems.

### 5. Hotspots
Walk the timeline **reverse** (from the end) and forward. At each place where there is a question, conflict, pain, missing knowledge or exception: add a hotspot `Q-NNN`. Challenge with "what if…?", "what goes wrong here?", "who disagrees?".

### 6. Opportunities & priorities
Ask the owner to mark the most painful hotspots and the most valuable opportunities (top 3–5 each).

### 7. Emerging boundaries
Without designing anything, note where language changes, where actors change, where pivotal events split the flow. List them as **candidate boundaries** for phase 2.

## Output format (`domain/event-timeline.md`)

1. A **Mermaid** overview of the timeline (`flowchart LR` with subgraphs per phase/swimlane, pivotal events highlighted).
2. A **table** per swimlane:

| ID | Event | Pivotal | Triggered by | Notes / hotspots |
|---|---|---|---|---|
| EVT-001 | Customer Registered | | ACT-001 Customer | Q-004 |

3. A list of **candidate boundaries** with the evidence for each.

## Outputs
| Output | Location |
|---|---|
| Workshop record (raw list of events, discussion) | `workshops/<date>-ws<NN>-eventstorming-big-picture/record.md` |
| Consolidated timeline | `domain/event-timeline.md` |
| New/updated actors | `domain/actors.md` |
| Terms and synonyms | `domain/glossary.md` |
| Hotspots | `planning/open-questions.md` |

## Done when
- The timeline covers the main flows end-to-end without gaps the owner can name.
- Pivotal events are agreed; top hotspots are prioritized.
