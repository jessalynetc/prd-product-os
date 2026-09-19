# Gate, Requirements, and Architecture

## Gate package

Present target user, problem, outcome, thesis, principles, success signals, P0/P1/P2, non-goals, never-cut core, cut order, primary journey, assumptions, blocking questions, recommended build scope, and decisions requiring approval. Wait for **Approve / Revise / Discuss** unless explicitly waived.

## P0 requirement schema

For each important P0 requirement include:

- ID and priority
- requirement and user value
- trigger
- observable behavior
- states
- business rules
- edge cases
- acceptance criteria

Acceptance criteria describe observable normal, empty, error, and recovery behavior when relevant. Avoid subjective phrases such as “works well.”

## Non-functional requirements

Evaluate accessibility, keyboard, screen reader, reduced motion, responsiveness, performance, reliability, security, privacy, permissions, compatibility, maintainability, observability, analytics, and error recovery. Include only relevant items; mark exclusions “Not applicable — reason.”

## Domain and data model

Define entities, relationships, source of truth, state, ownership, read/write behavior, persistence, and concrete schemas when P0 depends on them.

## AI behavioral contract

For AI features define role, allowed actions, context, grounding, uncertainty behavior, user control, confirmation, review, safety boundaries, evaluation, latency, malformed output, and tool failure.

## Technical architecture

Choose frontend, backend, database, state, APIs, auth, integrations, hosting, analytics, libraries, and asset architecture only after product behavior is stable. Explicitly distinguish product requirements from implementation decisions.

## Build guardrails

Document **Must Preserve**, **Must Ask Before**, and **May Decide Autonomously**. The harder a decision is to reverse, the more human review it requires.

