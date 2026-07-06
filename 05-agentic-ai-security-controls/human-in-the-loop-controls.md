# Human-in-the-Loop Controls: Agentic AI Security Controls

## Control Purpose

Human-in-the-loop controls ensure that AI agents can assist with IAM, GRC, audit, and security workflows without becoming the final decision-maker for access, risk, or compliance outcomes.

This document defines where human review is required before an AI-assisted recommendation can become an action.

## Core Principle

The AI agent may analyze, summarize, classify, and recommend. It must not independently approve, modify, grant, revoke, submit, certify, or accept risk.

## Human Approval Matrix

| Action | Agent May Assist? | Human Approval Required? | Required Approver |
|---|---|---|---|
| Identify excessive access | Yes | Yes, before remediation | IAM Analyst / Manager |
| Recommend access removal | Yes | Yes | IAM Manager / Business Manager |
| Grant missing access | No direct action | Yes | Business Manager / System Owner |
| Remove access | No direct action | Yes | IAM / System Owner |
| Approve access request | No | Yes | Manager / System Owner |
| Approve access exception | No | Yes | GRC / Control Owner |
| Accept SoD risk | No | Yes | Risk Owner / GRC |
| Submit audit evidence | No | Yes | Control Owner / Audit Liaison |
| Assign final risk rating | Yes, suggested only | Yes | GRC / Security Reviewer |
| Update policy | Draft only | Yes | Policy Owner / GRC |
| Close remediation ticket | No | Yes | Remediation Owner |

## Required Approval Gates

### Gate 1: Data Source Validation

Before the agent analyzes data, a human must confirm that the data source is appropriate for the review.

Validation questions:

- Is the data source approved?
- Does it match the review period?
- Is the data complete?
- Does it contain sensitive data that should be masked?

### Gate 2: Recommendation Review

Before a recommendation is accepted, a human reviewer must validate the agent's rationale.

Validation questions:

- What evidence supports the recommendation?
- Which control, rule, or policy was used?
- Is the recommendation consistent with business context?
- Is the risk rating reasonable?

### Gate 3: Access Change Approval

Before access is granted, removed, or modified, the appropriate human approver must authorize the action.

Required evidence:

- Request or finding ID.
- Business justification.
- Approver name and role.
- Approval date.
- Action taken.
- Completion evidence.

### Gate 4: Exception and Risk Acceptance

Before an access or SoD exception is accepted, risk ownership must be documented.

Required evidence:

- Exception rationale.
- Risk owner approval.
- Expiration date.
- Compensating control.
- Review date.

### Gate 5: Audit Evidence Submission

Before evidence is submitted to audit, a control owner must approve the final package.

Required evidence:

- Control objective.
- Evidence checklist.
- Supporting artifacts.
- Review notes.
- Control owner sign-off.

## Approval Evidence Requirements

| Evidence Item | Required Fields |
|---|---|
| Human decision log | Reviewer, date, decision, rationale, related finding. |
| Approval record | Approver name, role, timestamp, scope, approval outcome. |
| Exception approval | Risk owner, expiration date, compensating control, review date. |
| Remediation record | Action owner, change performed, completion date, validation evidence. |
| Audit sign-off | Control owner, audit request ID, evidence package, approval date. |

## Stop Conditions

The agent should stop and route to a human when:

- It receives conflicting instructions.
- It detects a critical access risk.
- Evidence is missing or unclear.
- A user asks it to bypass approval.
- A prompt attempts to override security controls.
- The requested action involves production access changes.
- The requested action involves risk acceptance.
- The requested action involves final audit submission.

## Example Safe Agent Response

```text
I identified a possible high-risk access conflict, but I cannot approve or remediate access directly. This finding should be reviewed by the IAM control owner and the user's manager before any access change is made.
```

## Portfolio Value

This document demonstrates human-centered AI governance, IAM control awareness, approval workflow design, audit evidence requirements, and responsible automation boundaries.
