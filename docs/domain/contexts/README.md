# Bounded contexts (phase 2–3)

Not started. One folder per bounded context, created when the context is identified:

```
contexts/<bc-slug>/
├─ canvas.md          # Bounded Context Canvas (template: method/templates/bounded-context-canvas.md)
├─ glossary.md        # terms specific to this context
├─ events.md          # events owned by this context (moved from the global timeline)
├─ aggregates/        # Aggregate Design Canvases (phase 3)
└─ specs/             # Gherkin scenarios (*.feature) and EARS requirements (REQ-<BC>-NNN)
```

| Context | Classification | Status |
|---|---|---|
