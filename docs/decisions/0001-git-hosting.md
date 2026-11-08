---
id: ADR-0001
title: Host the repository on GitHub
status: accepted
date: 2026-11-08
deciders: [owner]
---

# ADR-0001 — Host the repository on GitHub

## Context and problem statement
The project needs a remote git host. The owner is the sole contributor at first. The early phases produce documentation (Markdown + Mermaid) worked on with AI agents; code comes later.

## Decision drivers
- Native rendering of Markdown and Mermaid diagrams.
- Breadth of AI-agent integrations (CLI, coding agents, spec-driven tools).
- Free private repository for a single user.
- Lightweight agile tracking is enough for a solo contributor.

## Considered options
1. GitHub
2. Azure DevOps
3. GitLab

## Decision outcome
Chosen option: **GitHub** (private repository), because it renders docs-as-code best and has the widest AI-agent ecosystem (`gh` CLI, coding agents, GitHub Spec Kit), at no cost for a solo user.

### Consequences
- Good: the `gh` CLI lets agents manage issues, projects and pull requests on request.
- Bad / accepted trade-off: Issues + Projects are less rich than Azure Boards for formal agile hierarchies.
- Reversibility: cheap for the git history (change remote); issues and project boards would need a migration.

## Pros and cons of the options
### Azure DevOps
- Good: very complete Boards (Epic / Feature / Story), free up to 5 users.
- Bad: smaller AI-agent ecosystem; Markdown/Mermaid rendering mostly in the Wiki.
### GitLab
- Good: all-in-one, native Mermaid rendering.
- Bad: smaller AI-agent ecosystem; limited free CI minutes.
