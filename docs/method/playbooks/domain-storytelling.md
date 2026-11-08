---
id: PLAYBOOK-DOMAIN-STORYTELLING
title: Domain Storytelling workshop
status: reviewed
updated: 2026-10-17
---

# Playbook — Domain Storytelling (Discover)

**Goal:** describe **one concrete scenario** precisely, as a numbered sequence of *actors* doing *activities* on *work objects*. Complements EventStorming: EventStorming gives breadth, Domain Storytelling gives depth on a single flow.
**Phase:** 1 — Discover (also useful in phase 2 to check a boundary).
Method by Stefan Hofer & Henning Schwentner (<https://domainstorytelling.org>).
**Duration:** 30–60 min per story.

## Choosing the story
Pick a flow from the event timeline: a happy path first, then important variants or a painful hotspot.
Fix the **scope** of the story along three axes and note them in the story header:

| Axis | Options |
|---|---|
| Granularity | coarse-grained (whole process) / fine-grained (one step in detail) |
| Point in time | as-is (today) / to-be (with the future system) |
| Domain purity | pure (business only, no software) / digitalised (systems appear) |

In phase 1, prefer **coarse-grained, as-is, pure**.

## Steps
1. Ask the owner to tell the story using a **real, specific example** ("Last Tuesday, Marie from …").
2. Write each sentence as: `<n>. <Actor> <activity> <work object> [to/with <actor>]`.
3. Challenge every sentence: who exactly? what exactly is exchanged? what is it called? where does it come from?
4. Note variants and exceptions as separate stories or open questions — do not branch inside a story.
5. Read the story back; let the owner correct it.

## Output format (`domain/stories/ds-NNN-<slug>.md`)

```markdown
# DS-001 — <title>
Scope: coarse-grained · as-is · pure
Related events: EVT-010, EVT-011

| # | Actor | Activity | Work object | With / to |
|---|---|---|---|---|
| 1 | ACT-002 Customer | sends | Purchase request | ACT-003 Sales rep |
```

Followed by a Mermaid `sequenceDiagram` of the same steps, and a list of open questions.

## Outputs
| Output | Location |
|---|---|
| Workshop record | `workshops/<date>-ws<NN>-domain-story-<slug>/record.md` |
| Story | `domain/stories/ds-NNN-<slug>.md` (template: [`templates/domain-story.md`](../templates/domain-story.md)) |
| Work objects and activities as terms | `domain/glossary.md` |
| New events discovered | `domain/event-timeline.md` |
| Questions | `planning/open-questions.md` |

## Done when
The owner can read the story aloud and agrees it is what really happens.
