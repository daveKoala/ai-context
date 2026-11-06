---
name: investigate
description: Use when debugging, diagnosing a bug or incident, finding a root cause, or investigating unexpected system behaviour.
---

# Investigation

## 1. Frame the problem

- Establish the problem, the objective and the known facts before investigating.
- Identify the likely components, data flows and contracts involved.
- Recommend an investigation approach based on the available context:
  - **Narrow and deep:** examine a specific component, behaviour or suspected cause in detail.
  - **Broad and shallow:** explore multiple components, dependencies or potential causes to find where deeper investigation is warranted.
- Explain which approach you recommend and why. Change direction if the evidence shows the initial approach is wrong.
- Investigate until there is sufficient evidence to support a decision, not until every possible explanation has been exhausted. Consider the consequence of being wrong when deciding how much evidence is sufficient. If further investigation is unlikely to change the recommendation, stop and report remaining uncertainty.

## 2. Investigate scientifically

- Develop testable hypotheses rather than jumping to conclusions. For each, state what you believe is happening, why, and what evidence would confirm or disprove it.
- Actively try to falsify your preferred hypothesis, consider the null hypothesis where appropriate, and look for alternative explanations.
- Look for contradictory evidence, not just supporting evidence. For example, check cases where the suspected cause is present but the problem does not occur.
- Inspect the actual implementation. Don't infer likely code structure when you can read the code.
- Distinguish clearly between **observed behaviour**, **code-level facts**, **inferences**, **assumptions** and **unknowns**.
- Support findings with evidence such as logs, metrics, code references, tests or reproducible experiments.
- Prefer reusable scripts over repetitive manual commands or operations.
- Investigations are read-only by default. Ask before changing code, data or configuration to test a hypothesis, unless it's in a local or disposable environment.
- Don't give implementation instructions when I've asked for an investigation.

## 3. Cross-service problems

When behaviour spans services, establish:

- Which component owns the data, and which is authoritative.
- Where data is transformed, re-derived or loses precision.
- Whether business rules are duplicated across boundaries.
- Whether a downstream service makes assumptions that belong upstream.
- Whether the design allows inconsistent behaviour between components.

Prefer fixing the contract or the authoritative source over patching symptoms in several places.

## 4. Report

Lead with the conclusion or current verdict, then:

- **Findings:** what is established, each labelled as fact or inference, with a confidence level.
- **Evidence:** files, functions, logs, metrics, tests or experiments supporting each finding.
- **How to verify:** commands, queries, code and clear steps I can run to confirm the findings independently.
- **Remaining uncertainties:** what is still unknown, and what was not tested.
- **Recommended next steps.**

If the evidence is insufficient, say so. Do not present a plausible explanation as a confirmed root cause, and don't pad a thin investigation with speculative detail.
