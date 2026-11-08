# ddd-discovery-template

> Template repository — **Phase 1 — Align & Discover** (domain discovery, no code yet)

A ready-to-use workspace to discover and specify a new product with **Domain-Driven Design (DDD)**, through structured workshops run with an AI agent. Everything is plain Markdown / Mermaid, readable by humans and by any AI agent.

## Using this template

1. Create a repository from it:
   `gh repo create <name> --private --template gimp-duck/ddd-discovery-template --clone`
   (or **Use this template** on GitHub).
2. Open an AI agent session in the new folder and ask it to initialize the project — it will follow [`TEMPLATE-SETUP.md`](TEMPLATE-SETUP.md).
3. Start with the WS00 project brief.

## Where to start

| You are… | Read |
|---|---|
| A human joining the project | [`docs/README.md`](docs/README.md) — map of the documentation and current status |
| An AI agent | [`AGENTS.md`](AGENTS.md) — rules of engagement, then `docs/README.md` |
| Looking for the "why" | [`docs/domain/vision.md`](docs/domain/vision.md) |
| Looking for a term | [`docs/domain/glossary.md`](docs/domain/glossary.md) |
| Looking for a past decision | [`docs/decisions/`](docs/decisions/) |

## Principles

- **Domain first, technology later.** No technical choice is made before the domain is understood and a decision record (ADR) justifies it.
- **Docs as code.** Everything is plain Markdown / Mermaid, versioned in git, readable by humans and by any AI agent.
- **Iterate and partition.** The scope is too large to be specified upfront; it is split into sub-domains and bounded contexts as they emerge.
