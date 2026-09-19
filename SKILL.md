---
name: prd-product-os
description: Guide a product idea or existing project through progressive intake, product framing, scope, experience architecture, an approval gate, requirements, technical architecture, build planning, validation, and PRD maintenance. Use when the user asks to start, continue, write, refine, review, or update a PRD. Works with a local project brief by default and may synchronize with Notion when available and requested.
---

# PRD Product OS

Turn ideas into build-ready PRDs without making the user repeat known context or forcing a long questionnaire.

## Operating contract

- Reconstruct context before asking questions.
- Propose likely answers and label inferences; do not silently turn them into facts.
- Keep **Facts**, **Assumptions**, **Open Questions**, and **Decisions** separate.
- Ask one material question at a time when practical.
- Continue through non-blocking uncertainty; stop on blocking product decisions.
- Do not produce the full build-ready PRD before the Product Architecture Gate is approved unless the user explicitly overrides it.
- Adjust depth to the build budget. Reduce scope instead of compressing incompatible scope into the timebox.
- Treat external systems as optional persistence adapters. The workflow must work from files and conversation context alone.

## Start or resume

1. Inspect available conversation context and referenced project artifacts.
2. If a project brief exists, read it. Otherwise use [assets/project-brief-template.md](assets/project-brief-template.md) as the state shape; create a file only when the user has asked for a persisted artifact or project work authorizes it.
3. If the user requests Notion synchronization and Notion is connected, read [references/notion-adapter.md](references/notion-adapter.md).
4. Reconstruct confirmed facts, assumptions, decisions, gaps, build budget, current stage, and gate status.
5. Use [references/workflow-router.md](references/workflow-router.md) to choose the next mode.

## Load only the reference for the active mode

- Intake or framing: [references/intake-and-framing.md](references/intake-and-framing.md)
- Scope or experience architecture: [references/scope-and-experience.md](references/scope-and-experience.md)
- Gate, requirements, data, or technical architecture: [references/requirements-and-architecture.md](references/requirements-and-architecture.md)
- Build plan, validation, final PRD, or maintenance: [references/build-and-validation.md](references/build-and-validation.md)
- Final document structure: [references/prd-template.md](references/prd-template.md)

Do not load every reference by default.

## Product Architecture Gate

Before detailed requirements, present one compact checkpoint containing target user, problem, outcome, thesis, up to three principles, success signals, P0/P1/P2, non-goals, never-cut core, cut order, primary journey, assumptions, blocking questions, recommended build scope, and only the decisions needing confirmation.

End with **Approve / Revise / Discuss**. Record the response. If approved, continue to detailed requirements. If not, route back to the unresolved stage.

## Final standard

A build-ready PRD must pass this test:

> Could a capable designer, engineer, or coding agent with no conversation history build the intended P0 without inventing material product decisions?

If two reasonable builders could interpret an important P0 behavior differently, clarify it before calling the PRD build-ready.

