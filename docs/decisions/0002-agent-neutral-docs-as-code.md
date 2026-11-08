---
id: ADR-0002
title: Agent-neutral docs-as-code documentation
status: accepted
date: <yyyy-mm-dd>
deciders: [owner]
---

# ADR-0002 — Agent-neutral docs-as-code documentation

## Context and problem statement
Requirements will be discovered progressively with AI assistance and must stay readable by humans and by any AI agent. The project should not depend on a single agent vendor, nor on a technology stack before the domain is understood.

## Decision drivers
- Readable by humans and machines; versioned with the code.
- No lock-in to one AI agent; no loss of efficiency for the agent currently used.
- A structure that scales as the documentation grows and is partitioned by bounded context.
- American English for all artifacts.

## Considered options
1. Agent-specific setup (e.g. everything in `CLAUDE.md` and `.claude/skills/`).
2. **Agent-neutral content with thin agent adapters.**
3. External wiki / document tool.

## Decision outcome
Chosen option: **2**, as packaged in the `ddd-discovery-template` repository.
- `AGENTS.md` (open convention) is the single source of rules for agents; `CLAUDE.md` only imports it.
- Methods and templates live in `docs/method/` as plain Markdown; agent skills (e.g. `.claude/skills/*/SKILL.md`, Agent Skills format) are thin adapters pointing to them.
- Documentation is split into `method/` (how), `workshops/` (dated journal), `domain/` (living model), `decisions/` (why) and `planning/` (next / unknown).
- All artifacts are written in American English; conversations may be in another language.

### Consequences
- Good: any agent, or the owner alone, can run a workshop from the playbooks; switching agent means adding an adapter only.
- Bad / accepted trade-off: adapters must be kept in sync with playbook names (small, mechanical).
- Reversibility: cheap.
