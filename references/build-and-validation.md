# Build Planning, Validation, and Maintenance

## Vertical-slice build plan

Prefer **Foundation → First Vertical Slice → Remaining Core → Quality → Polish**. Each block must produce something observable.

For every block specify objective, what gets built, dependencies, output, and done-when criteria.

## Definition of Ready

Verify problem, user, outcome, approved thesis and P0, non-goals, core journey, important states, resolved blockers, visible assumptions, P0 acceptance criteria, required assets/data, viable first slice, and clear guardrails.

## Definition of Done

As relevant verify requirements and acceptance criteria, normal/edge/failure/recovery states, responsive behavior, accessibility, runtime errors, analytics/observability, documentation, decision log, and alignment between PRD and implementation.

## Validation

Run acceptance, UX, accessibility, technical QA, regression, and the Blank-Slate Test. Do not treat generated code as completion.

## Maintenance

When scope or behavior changes:

1. classify it as fact, assumption, question, or decision;
2. identify affected requirements, states, schemas, architecture, tests, and build blocks;
3. update the PRD and decision log together;
4. route backward if the change invalidates an approved product decision;
5. preserve a short reason and trade-off, not just the new outcome.

