---
name: security-review
description: Use when reviewing code or a design for security issues, or investigating a suspected vulnerability.
---

# Security Review

## Scope

Go beyond surface-level validation and obvious vulnerabilities. Pay particular attention to:

- Authentication versus authorisation. A valid token or permission scope does not by itself authorise access to a specific resource.
- Object-level ownership checks and insecure direct object references.
- Cross-customer and cross-tenant data access.
- Service-to-service trust boundaries, and overly broad shared scopes or permissions.
- Whether internal endpoints are genuinely isolated, and how much trust is placed in gateway, infrastructure or deployment configuration.
- Whether privileged operations can be reached indirectly.
- Replay attacks and idempotency.
- Sensitive information exposure, including logs, errors and responses.

## Method

- Trace the actual code paths. Don't infer behaviour you can read.
- For each potential issue, establish the prerequisites an attacker would need.
- Prefer non-destructive methods: code analysis, synthetic data and isolated tests. Never test against production or real customer data without my explicit authorisation.

## Classifying findings

Give every finding a status:

- **Confirmed:** demonstrated through code analysis or reproducible evidence.
- **Partially confirmed:** a specific weakness is demonstrated, but exploitation or an important prerequisite is unproven.
- **Unconfirmed:** plausible, but the evidence is insufficient.
- **Disproved:** the evidence contradicts the hypothesis.

Rules:

- Severity and confidence are separate. Rate both.
- An absent defence is not proof an exploit is possible. State the prerequisites.
- "I couldn't demonstrate exploitation" never means "the system is secure". State what was not tested.

## Report

For each finding: status, severity, confidence, prerequisites, evidence (files, functions, endpoints), limitations of the review, and recommended remediation. Order by remediation priority.
