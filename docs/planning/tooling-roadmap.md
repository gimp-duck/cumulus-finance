---
id: PLANNING-TOOLING
title: Tooling roadmap
status: reviewed
updated: 2026-11-08
sources: [ADR-0002]
---

# Tooling roadmap

Tools are introduced only when their phase starts. Phase 1 needs nothing beyond git, Markdown, Mermaid and an AI agent following the playbooks.

| Tool | Phase | Trigger to adopt | Use | Install / notes |
|---|---|---|---|---|
| **Context Mapper** (<https://contextmapper.org>, Apache 2.0, no account) + community MCP server `context-mapper-mcp` | 2 | At least two candidate bounded contexts identified | Formal context map in CML, validation, PlantUML diagrams | Requires Node.js. Claude Code: `claude mcp add context-mapper -- npx -y context-mapper-mcp@latest`. Optional VS Code extension (requires Java). Review the MCP repository before installing (third-party). |
| **GitHub Spec Kit** (MIT) | 3 | A bounded context is validated (canvas + scenarios) | Spec-driven delivery: constitution → specify → plan → tasks → implement, per context | Feed `/speckit.specify` from `domain/contexts/<bc>/`; align its folders through an ADR. |
| Stack-specific agent tooling | 3 | First technical decisions (ADR) | Architecture and tactical DDD guidance for the chosen stack | Chosen once the stack is decided — not before. |
| `gh auth refresh -s project` | when needed | We want a GitHub Projects board | Lets agents manage the project board | One-time scope extension of the existing `gh` login. |
