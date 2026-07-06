# Agent Risk Assessment: Agentic AI Security Controls

## Assessment Purpose

This assessment identifies risks that may occur when an AI agent supports IAM, RBAC, GRC, audit evidence, or access governance workflows.

The goal is to demonstrate AI security awareness, governance thinking, risk classification, and human-in-the-loop control design.

This is a fictional portfolio artifact and does not assess a real AI system.

## Agent Scope

| Item | Description |
|---|---|
| Agent Name | IAM/GRC Support Agent |
| Use Case | Assist with access review, SoD analysis, policy mapping, evidence review, and recommendation summaries. |
| Data Type | Fictional IAM/GRC sample data only. |
| Systems Access | No production system access in this portfolio. |
| Human Approval Required | Yes |
| Automation Level | Assistive only; no autonomous access changes. |

## Risk Assessment Summary

| Risk ID | Risk Area | Risk Description | Impact | Likelihood | Risk Rating | Recommended Control |
|---|---|---|---|---|---|---|
| AI-R-001 | Excessive Tool Access | Agent may have access to tools or systems beyond its approved purpose. | High | Medium | High | Apply least privilege and restrict tools by role. |
| AI-R-002 | Unauthorized Access Change | Agent may grant, remove, or modify access without approval. | Critical | Low | Critical | Block write actions unless approved by human workflow. |
| AI-R-003 | Prompt Injection | Malicious instructions may attempt to override security rules. | High | Medium | High | Use prompt validation, guardrails, and tool permission boundaries. |
| AI-R-004 | Sensitive Data Exposure | Agent may reveal employee, access, or audit information in output. | High | Medium | High | Mask sensitive fields and apply data minimization. |
| AI-R-005 | Unsupported Recommendation | Agent may generate a recommendation not supported by evidence. | Medium | Medium | Medium | Require evidence citation and human validation. |
| AI-R-006 | Missing Audit Trail | Agent actions and recommendations may not be logged. | High | Medium | High | Log inputs, outputs, decisions, approvals, and tool calls. |
| AI-R-007 | Over-Reliance on AI | Human reviewers may accept AI output without validation. | High | Medium | High | Require human approval, reviewer attestation, and QA sampling. |
| AI-R-008 | Inaccurate Risk Rating | Agent may assign risk incorrectly. | Medium | Medium | Medium | Use approved risk criteria and manual review. |
| AI-R-009 | Data Integrity Issue | Agent may analyze outdated, incomplete, or manipulated data. | High | Medium | High | Validate data source, timestamp, and completeness. |
| AI-R-010 | Exception Approval Abuse | Agent may recommend approval of risky exceptions without proper owner review. | High | Low | High | Require control owner approval and expiration tracking. |

## Key Controls

### Least Privilege Tool Access

The agent should only access tools and data needed for its approved use case.

### Human Approval Gates

The agent must not approve access, approve exceptions, accept risk, submit audit evidence, or modify production records without human approval.

### Logging and Monitoring

Agent activity should be logged to support auditability, troubleshooting, and security monitoring.

### Data Minimization

Agent inputs and outputs should exclude unnecessary sensitive information.

### Evidence-Based Recommendations

The agent should explain which data, rule, policy statement, or evidence item supports each recommendation.

### Secure Failure Behavior

When the agent is unsure, lacks evidence, or detects conflicting instructions, it should stop and route the item to a human reviewer.

## Risk Rating Criteria

| Rating | Description |
|---|---|
| Critical | Could result in unauthorized access, privilege escalation, audit failure, or material control breakdown. |
| High | Could create significant security, compliance, or operational risk. |
| Medium | Could create moderate risk requiring review or clarification. |
| Low | Limited impact or primarily documentation-related. |

## Human-in-the-Loop Statement

The AI agent supports analysis and documentation only. Human IAM, GRC, Security, Audit, and business control owners remain accountable for final decisions.

## Portfolio Value

This assessment demonstrates AI security risk analysis, IAM/GRC workflow awareness, control design, and responsible Agentic AI governance.
