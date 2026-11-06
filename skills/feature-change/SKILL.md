---
name: feature-change
description: Use when building a feature or making a non-trivial change to a codebase. Creates and maintains a change document that tracks the work from Draft to Ready to Done.
---

# Feature Building and Changes

## When a change document is needed

- Create one for any change that alters behaviour, touches several components, changes interfaces or data, or carries deployment risk.
- Skip it for trivial changes, such as single-file fixes, typos, formatting, or refactors with no behaviour change. If you're unsure, ask.
- Keep the document proportional to the size and complexity of the change.

## The change document

- It is a **working artefact**, not a one-off planning exercise. Keep it updated throughout implementation as decisions, requirements or findings change.
- Store it in the project, following established conventions. If there are none, use `docs/changes/<feature-name>.md`.
- It should give a lasting record of what changed, why it changed, how it was verified, and any decisions that affect future maintenance.

## Status

Every change document has exactly one status:

- **Draft:** requirements, scope or approach are still being established.
- **Ready:** the change is defined, agreed and testable enough to start implementation.
- **Done:** implementation and the required verification are complete.

Rules:

- **Only I move a change from Draft to Ready.** Don't promote it based on assumptions. List unresolved decisions under Open Questions and ask me to resolve them. Never invent requirements and then treat them as approved.
- Don't start implementation while the status is Draft, unless I explicitly ask for a spike or prototype.
- Don't mark a change Done until all acceptance criteria are met and the required tests and verification are complete.

## Approach

- Before proposing a change, understand the relevant contract, business invariants, data ownership and impact on dependent systems.
- Follow established project conventions and engineering standards.
- Prefer small, incremental, independently testable changes.
- Consider backwards compatibility, deployment, rollback, failure scenarios and operational impact where relevant.

## Testing

- Define a testing regime proportional to the change, covering unit, integration, regression and security testing where relevant.
- Tests should demonstrate intended behaviour, not just make the suite green.
- For each significant test, state what it proves and what it doesn't.
- Passing tests and coverage are not evidence of correctness if the tests encode the wrong assumptions.
- Consider, where relevant: boundary conditions, numeric precision and rounding, idempotency and retries, partial failures and compensating actions, cross-service contracts, feature flag combinations, and legacy behaviour.

## Template

Omit sections that don't apply to the change.

```markdown
# <Change name>

**Status:** Draft | Ready | Done
**Last updated:** YYYY-MM-DD

## Problem
What is wrong or missing, and why it matters.

## Desired outcome
What success looks like.

## Acceptance criteria
- [ ] Measurable, testable criterion
- [ ] ...

## Scope
**In scope:**
**Out of scope:**

## Affected components and dependencies

## Assumptions

## Open questions
Decisions needed before this can move to Ready.

## Approach
Proposed design, including significant technical decisions and trade-offs.

## Risks

## Testing
What each test proves and what it doesn't.

## Deployment and rollback
Backwards compatibility, migration, rollout and rollback plan.

## Decision log
| Date | Decision | Rationale |
|------|----------|-----------|

## Verification
How each acceptance criterion was verified (filled in before Done).

## Limitations and follow-ups
Known limitations, deferred work and outstanding risks.
```
