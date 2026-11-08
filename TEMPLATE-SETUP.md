# Template setup

This repository was created from **ddd-discovery-template**. This file is a one-time checklist for the AI agent (or the owner) to turn the template into a real project. **Delete this file at the end of the setup.**

## 1. Ask the owner
- Project name (display name and repository slug).
- A one-sentence description, if they already have one (otherwise leave a placeholder; WS00 will produce it).

## 2. Personalize
| File | Change |
|---|---|
| `README.md` | Replace the title and template description with the project name and description; delete the "Using this template" section; keep "Where to start" and "Principles" |
| `docs/README.md` | Keep as is (next step is WS00) |
| `docs/domain/*.md`, `docs/planning/open-questions.md`, `docs/planning/roadmap.md` | Replace `updated: <yyyy-mm-dd>` with today's date |
| `docs/decisions/0001-*.md`, `0002-*.md` | Replace `date: <yyyy-mm-dd>` with today's date (decisions are inherited from the template) |
| `docs/decisions/README.md` | Same dates |

Do **not** change `docs/method/` — it is the shared method.

## 3. Agent memory (if your agent has one)
Save these owner preferences in the agent's persistent memory for this project:
- Repository artifacts in American English; conversation in French.
- Never add `Co-Authored-By` or AI attribution to commits or pull requests.
- Agent-neutral docs: substantive content goes to `AGENTS.md` / `docs/method/`, never to agent-specific files.
- Stay technology-agnostic until a decision record says otherwise.
- Project state: phase 1, next step WS00 (project brief).

## 4. Finish
1. Delete `TEMPLATE-SETUP.md` and remove the "Not initialized yet?" note from `AGENTS.md`.
2. Check nothing template-specific remains: search for `<yyyy-mm-dd>` outside `docs/method/templates/`, and for `ddd-discovery-template` outside `docs/decisions/0002-*.md`.
3. Show the owner the changes; commit and push **only with their agreement**.
4. Propose to start WS00 — project brief.
