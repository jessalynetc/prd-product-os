# PRD Product OS

PRD Product OS is a portable ChatGPT/Codex skill that helps turn an early product idea into a build-ready Product Requirements Document through progressive interviews, explicit decision gates, and validation.

It is designed for product designers, solo builders, and AI-assisted development workflows where product intent needs to survive handoffs between ChatGPT, Claude, Codex, Cursor, designers, and engineers.

The skill does **not** immediately generate a long PRD from a vague idea. It first reconstructs existing context, identifies what is missing, proposes likely answers, and interviews the user only about decisions that materially affect the product.

## What it does

The skill guides a project through:

```text
Context Reconstruction
→ Intake
→ Product Framing
→ Success Definition
→ Scope
→ Experience Architecture
→ Product Architecture Gate
→ Requirements
→ Domain and Data Model
→ Technical Architecture
→ Vertical-Slice Build Plan
→ Validation
→ Final PRD
→ Maintenance
```

Key behaviors include:

- reading available context before asking questions
- separating facts, assumptions, open questions, and decisions
- proposing likely answers instead of presenting a long questionnaire
- adapting scope to 3-hour, 6-hour, 12-hour, or production build budgets
- defining P0, P1, P2, non-goals, never-cut scope, and cut order
- requiring approval at the Product Architecture Gate
- writing testable requirements and observable acceptance criteria
- planning implementation as vertical slices
- validating the result with Definition of Ready, Definition of Done, and the Blank-Slate Test
- resuming an existing PRD from saved state instead of restarting discovery

## The Router

The Router is a decision table inside the skill—not a separate agent or program. It examines the current project state and chooses the earliest unresolved stage that could materially change downstream work.

| Current evidence | Route |
|---|---|
| Only an idea exists | Intake |
| User, problem, or outcome is unclear | Product Framing |
| Direction is clear but P0 is unclear | Scope |
| P0 is clear but journey or states are unclear | Experience Architecture |
| Product architecture is ready but unapproved | Product Architecture Gate |
| Gate is approved but behavior is underspecified | Requirements |
| Requirements are stable but implementation choices are missing | Technical Architecture |
| Architecture is stable but execution order is missing | Build Plan |
| Draft PRD is complete | Validation |
| Development is underway | Maintenance |

The Router prevents repeated interviews and stops the skill from writing detailed requirements before foundational product decisions are stable.

## Product Architecture Gate

Before generating the complete PRD, the skill presents a compact checkpoint containing:

- target user
- core problem and desired outcome
- product thesis
- up to three product principles
- success signals
- P0, P1, and P2
- non-goals
- never-cut core and cut order
- primary journey
- assumptions and blocking questions
- recommended build scope
- decisions requiring approval

The user can respond with **Approve**, **Revise**, or **Discuss**. The skill does not proceed to the complete build-ready PRD until this gate is approved, unless the user explicitly asks to override it.

## Works without Notion

Notion is optional. The core workflow has no connector dependency.

### Local mode

The skill uses `assets/project-brief-template.md` to maintain:

- current PRD stage
- confirmed facts
- assumptions
- decisions
- blocking and non-blocking questions
- current gaps
- next interview question
- build budget
- gate approval status

### Notion-connected mode

When the user requests Notion synchronization and the connector is available, the skill can read and update an existing project record. Workspace-specific IDs and credentials are deliberately excluded from this repository. The adapter discovers the available schema at runtime.

See [`references/notion-adapter.md`](references/notion-adapter.md).

## Repository structure

```text
prd-product-os/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── assets/
│   └── project-brief-template.md
└── references/
    ├── workflow-router.md
    ├── intake-and-framing.md
    ├── scope-and-experience.md
    ├── requirements-and-architecture.md
    ├── build-and-validation.md
    ├── prd-template.md
    └── notion-adapter.md
```

`SKILL.md` contains the shared operating contract and routing entrypoint. Detailed guidance is loaded from `references/` only when the active stage requires it, keeping the skill focused and token-efficient.

## Installation

Clone the repository into your Codex skills directory:

```bash
git clone https://github.com/jessalynetc/PRD-capture-skill.git ~/.codex/skills/prd-product-os
```

Restart the relevant Codex or ChatGPT Work session if the skill is not discovered immediately.

You can also download the repository and place the folder manually in your supported skills directory. The folder containing `SKILL.md` is the installable skill.

## Example prompts

Start a new PRD:

```text
Use $prd-product-os to start a PRD for a portfolio chatbot that answers recruiter questions. I have six hours for the MVP.
```

Resume an existing project:

```text
Use $prd-product-os to continue this project from project-brief.md. Tell me the current stage, what is confirmed, and the next material question.
```

Use the optional Notion workflow:

```text
Use $prd-product-os to continue the Mid-Autumn project. Read its Notion project page first and update the PRD stage and gaps after this interview round.
```

Review a draft:

```text
Use $prd-product-os to validate this PRD using Definition of Ready, Definition of Done, and the Blank-Slate Test.
```

## Final quality standard

The skill treats a PRD as build-ready only when it passes the Blank-Slate Test:

> Could a capable designer, engineer, or coding agent with no previous conversation history build the intended P0 without inventing material product decisions?

If two reasonable builders could interpret an important P0 behavior differently, the PRD still needs clarification.

## Design decisions

- One main skill is used instead of ten independently triggered skills because every stage shares one state model and one approval gate.
- Detailed stage guidance is separated into references for progressive disclosure.
- Notion is an optional persistence adapter rather than a hard dependency.
- The first version uses an instruction-based Router instead of an executable state machine.
- The skill optimizes for clarity and build readiness rather than document length.

## Status

This repository contains the initial portable version of PRD Product OS. It is ready for real-project testing and iterative improvement based on observed interview, routing, and handoff failures.
