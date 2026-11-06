# Project Context

Copy this into a project's own `CLAUDE.md` and fill it in. Keep organisation-specific details in the private project repo, not in this public one.

## System overview

- **What this system does:** <one or two sentences>
- **Stack:** <languages, frameworks, datastores>
- **Architecture:** <monolith / services, messaging, orchestration patterns>
- **Neighbouring systems:** <services this one depends on or is depended on by>
- **Auth:** <how authentication and authorisation work>

## Known constraints

- <legacy behaviour that must be preserved>
- <technical debt to be aware of>
- <feature flags that change behaviour>

## Working in this codebase

- When discussing architecture, distinguish between how the system currently behaves, why it behaves that way, and how it should behave.
- Don't assume an existing implementation choice is correct because it is established, and don't recommend a rewrite just because an alternative is theoretically cleaner.

## Data ownership

- <which component is authoritative for which data>

## Optional: monetary values

Include this section if the system handles money.

- Represent monetary values at an appropriate, explicit precision.
- Distinguish chargeable values from reporting values.
- Use explicit rounding modes and policies. Be clear whether values are rounded then aggregated, or aggregated then rounded.
- Avoid silent precision loss at service boundaries.
- Preserve authoritative calculated values rather than reconstructing them downstream.
- Keep amendments, refunds, discounts and reporting consistent.
- Two values representing the same nominal amount are not necessarily interchangeable. A one-penny difference can indicate a contract or calculation problem, not just rounding noise.
- When investigating, follow the actual representation, transformations and rounding operations through the code.
