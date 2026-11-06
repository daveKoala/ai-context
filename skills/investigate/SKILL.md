---
name: investigate
description: Use when debugging, diagnosing a bug or incident, finding a root cause, or investigating unexpected system behaviour.
---

# Investigation

## 1. Frame the problem

- Establish the problem, the objective and the known facts before investigating.
- Recommend an investigation approach based on the available context:
  - **Narrow and deep:** examine a specific component, behaviour or suspected cause in detail.
  - **Broad and shallow:** explore multiple components, dependencies or potential causes to find where deeper investigation is warranted.
- Explain which approach you recommend and why. Change direction if the evidence shows the initial approach is wrong.

## 2. Investigate scientifically

- Develop testable hypotheses rather than jumping to conclusions.
- Apply the scientific method where practical. Actively try to falsify your preferred hypothesis, consider the null hypothesis where appropriate, and look for alternative explanations.
- Look for contradictory evidence, not just evidence that supports the initial hypothesis. For example, check cases where the suspected cause is present but the problem does not occur.
- Distinguish clearly between **facts**, **assumptions**, **inferences** and **speculation**.
- Support findings with evidence such as logs, metrics, code references, documentation or reproducible experiments.
- Prefer reusable scripts over repetitive manual commands or operations.
- Investigations are read-only by default. Ask before changing code, data or configuration to test a hypothesis, unless it's in a local or disposable environment.

## 3. Report

Summarise in this structure:

- **Findings:** what is established, each labelled as fact or inference.
- **Evidence:** logs, metrics, code references or experiments supporting each finding.
- **How to verify:** commands, queries, code and clear steps I can run to confirm the findings independently.
- **Remaining uncertainties:** what is still unknown or unconfirmed.
- **Recommended next steps.**

If the evidence is insufficient, say so. Do not present a plausible explanation as a confirmed root cause.
