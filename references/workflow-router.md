# Workflow Router

The router is a decision table, not a separate agent. It selects the next mode from saved evidence.

| Evidence | Route |
|---|---|
| No usable brief; idea only | Intake |
| Target user, problem, or outcome unclear | Product framing |
| Thesis clear; success undefined | Success framing |
| Direction clear; P0 or non-goals unclear | Scope |
| P0 clear; journey, states, or navigation unclear | Experience architecture |
| Architecture complete; gate not approved | Product Architecture Gate |
| Gate approved; P0 behavior incomplete | Requirements |
| Requirements stable; entities/state/source of truth unclear | Domain and data model |
| Product behavior stable; implementation choices missing | Technical architecture |
| Architecture stable; execution sequence missing | Build plan |
| Draft complete; quality unverified | Validation |
| Build is underway or product intent changed | Maintenance |

## Routing rules

- Choose the earliest unresolved stage that could materially change downstream work.
- Never reopen an approved decision without new evidence, a contradiction, or a user request.
- A later-stage question can route backward when it exposes a product-level ambiguity.
- Never skip the gate merely because a technical solution seems obvious.
- Report: current stage, what is confirmed, current gaps, and the single best next action.

