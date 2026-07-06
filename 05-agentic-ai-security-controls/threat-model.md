# Threat Model: Agentic AI Security Controls

## Threat Model Purpose

This threat model identifies potential threats for an AI agent that supports IAM, RBAC, GRC, audit evidence, and access governance workflows.

The goal is to show how Agentic AI systems should be evaluated before they are allowed to interact with sensitive security processes.

This is a fictional portfolio artifact and does not represent a production environment.

## System Overview

### Agent Use Case

The IAM/GRC Support Agent assists with:

- Access review analysis.
- RBAC exception identification.
- Segregation of Duties review.
- Policy mapping.
- Audit evidence checklist creation.
- Risk findings summaries.
- Control-owner question generation.

### Trust Boundaries

| Boundary | Description | Risk |
|---|---|---|
| User to Agent | Human users submit requests and data to the agent. | Prompt injection or incorrect instructions. |
| Agent to Data Source | Agent reads access data, policy text, or evidence lists. | Sensitive data exposure or stale data. |
| Agent to Tools | Agent may use connected tools to read or write files, tickets, or repo content. | Excessive permissions or unauthorized changes. |
| Agent to Human Reviewer | Agent sends recommendations for approval. | Over-reliance or missed validation. |
| Agent to Audit Package | Agent helps organize evidence. | Incomplete or unsupported audit response. |

## Threat Scenarios

| Threat ID | Threat | Scenario | Impact | Control |
|---|---|---|---|---|
| T-001 | Prompt Injection | A user includes instructions telling the agent to ignore human approval rules. | Unauthorized recommendation or unsafe output. | System guardrails, prompt filtering, and approval gates. |
| T-002 | Unauthorized Tool Use | Agent attempts to update access, tickets, or evidence without permission. | Control failure or unauthorized change. | Tool allowlist and write-action approval. |
| T-003 | Sensitive Data Leakage | Agent includes employee identifiers or sensitive access details unnecessarily. | Privacy or compliance issue. | Data minimization and output masking. |
| T-004 | Evidence Hallucination | Agent invents evidence that was not provided. | Audit failure or false assurance. | Require evidence references and reviewer validation. |
| T-005 | Risk Misclassification | Agent assigns incorrect risk rating to a critical issue. | Under-prioritized remediation. | Approved risk scoring rubric and QA sampling. |
| T-006 | Over-Automation | Agent executes access changes without human review. | Unauthorized access grant/removal. | Disable autonomous remediation. |
| T-007 | Stale Data Analysis | Agent analyzes outdated access records. | Incorrect findings. | Validate timestamps and source freshness. |
| T-008 | Logging Gap | Agent recommendations are not logged. | No audit trail for decisions. | Centralized logging and retention. |
| T-009 | Exception Approval Abuse | Agent recommends accepting risky exceptions without compensating controls. | Persistent access risk. | Control owner approval and expiration tracking. |
| T-010 | Tool Credential Exposure | Agent output exposes secrets, tokens, or system credentials. | Credential compromise. | Secret scanning, redaction, and no-secret policy. |

## STRIDE-Style View

| Category | Example in This Portfolio | Control Response |
|---|---|---|
| Spoofing | User attempts to impersonate a control owner. | Verify identity and approval authority. |
| Tampering | User modifies evidence before submission. | Evidence integrity checks and review logs. |
| Repudiation | No record of who accepted an AI recommendation. | Approval logs and reviewer attestation. |
| Information Disclosure | Agent reveals sensitive access data. | Mask sensitive fields and limit outputs. |
| Denial of Service | Agent workflow overwhelmed with malformed evidence. | Input validation and graceful failure. |
| Elevation of Privilege | Agent grants or approves access beyond authority. | Block autonomous access changes. |

## High-Risk Assets

- User access extracts.
- Privileged access lists.
- RBAC and SoD rules.
- Audit evidence packages.
- Exception registers.
- Human approval logs.
- AI agent prompts and outputs.
- Tool credentials or API tokens.

## Required Controls

- Least privilege tool access.
- Human approval before write actions.
- Prompt injection resistance.
- Sensitive data masking.
- Evidence source validation.
- Activity logging.
- Role-based reviewer approval.
- Exception expiration tracking.
- QA validation of AI outputs.
- Incident escalation for unsafe behavior.

## Human-in-the-Loop Statement

Any AI recommendation involving access, risk acceptance, audit evidence, or control effectiveness must be reviewed by an authorized human before final action.

## Portfolio Value

This threat model demonstrates security architecture thinking, AI risk analysis, IAM/GRC process awareness, and control design for Agentic AI workflows.
