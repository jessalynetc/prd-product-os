# Scope and Experience Architecture

## Scope

- **P0:** minimum viable core needed to deliver or test the primary value.
- **P1:** meaningful MVP enhancement that does not determine core validity.
- **P2:** progressive enhancement or future work.
- **Non-goals:** deliberate exclusions.
- **Never Cut:** smallest capabilities that must survive scope reduction.
- **Cut Order:** first items removed under time pressure.

Protect P0. Challenge features that do not support the outcome, duplicate capability, introduce disproportionate complexity, harm accessibility, or threaten the build budget.

## Build-budget defaults

- **3 hours:** foundation, one critical vertical slice, basic validation.
- **6 hours:** foundation, core vertical slice, remaining P0, responsive/accessibility basics, QA.
- **12 hours:** robust P0, selected P1, edge cases, testing, polish, documentation.
- **Production:** security, privacy, observability, migrations, rollout/rollback, performance, operations, maintainability as relevant.

## Experience architecture

Define: **Entry → Primary Job → Core Interaction/Loop → Key States → Success/Exit**.

Also cover relevant navigation, permissions, loading, empty, failure, and recovery states. Use a small diagram only when it removes ambiguity.

Do not choose a technical stack at this stage. Present the Product Architecture Gate after scope and experience architecture are coherent.

