# Gap Analysis Report: GRC Policy Mapping Agent

## Report Purpose

This report evaluates the fictional Sample Access Control Policy for coverage, clarity, audit readiness, and AI governance maturity.

The goal is to demonstrate GRC analysis, policy review, control mapping, and risk-based recommendations.

## Review Scope

| Item | Description |
|---|---|
| Policy Reviewed | Sample Access Control Policy |
| Review Type | Simulated AI-assisted policy mapping and gap analysis |
| Control Themes | IAM, RBAC, JML, privileged access, SoD, audit evidence, AI governance |
| Data Type | Fictional portfolio artifact |
| Human Approval Required | Yes |

## Executive Summary

The sample policy provides strong baseline coverage for access control, role-based access, approvals, Joiner-Mover-Leaver events, privileged access, Segregation of Duties, periodic access reviews, exception documentation, audit evidence retention, and human approval for AI-assisted access review.

However, several areas need more detail before the policy would be audit-ready in a real organization. The most important gaps are missing review frequency by access type, missing deprovisioning SLA, missing evidence retention period, missing exception expiration enforcement, and missing AI agent logging requirements.

## Gap Summary

| Gap ID | Gap Area | Current State | Risk | Recommendation | Priority |
|---|---|---|---|---|---|
| GAP-001 | Access Review Frequency | Policy says access must be reviewed periodically but does not define timing. | Inconsistent reviews and weak audit evidence. | Define review frequency by access type: standard, privileged, critical, and third-party. | High |
| GAP-002 | Deprovisioning SLA | Policy requires terminated users to be deprovisioned but does not define timeframe. | Delayed removal of access after termination. | Define offboarding SLA, such as same-day or within 24 hours based on risk. | Critical |
| GAP-003 | Privileged Access Monitoring | Policy restricts privileged access but does not define monitoring requirements. | Privileged misuse may go undetected. | Add logging, monitoring, and periodic privileged access review requirements. | High |
| GAP-004 | Exception Expiration | Policy requires expiration dates but does not define enforcement. | Temporary access may become permanent. | Require automated or manual expiration review and owner reapproval. | High |
| GAP-005 | Evidence Retention Period | Policy requires evidence retention but does not define duration. | Evidence may be unavailable during audit. | Define retention period based on legal, regulatory, and audit requirements. | Medium |
| GAP-006 | SoD Review Ownership | Policy requires SoD enforcement but does not assign control ownership. | Conflicts may remain unresolved. | Assign IAM/GRC owner for SoD rules, review, remediation, and exception tracking. | High |
| GAP-007 | AI Agent Logging | Policy requires human approval but does not define AI activity logging. | AI-assisted decisions may lack traceability. | Require logs of AI inputs, outputs, recommendations, approvals, and final human decisions. | High |
| GAP-008 | Third-Party Access | Policy scope includes contractors but lacks special requirements for third-party access. | Vendor or contractor access may not be reviewed appropriately. | Add third-party access owner, expiration, and periodic review requirements. | Medium |
| GAP-009 | Access Recertification Evidence | Policy requires access reviews but does not define sign-off requirements. | Review completion may be hard to prove. | Require reviewer name, date, scope, decision, exceptions, and remediation status. | High |
| GAP-010 | Compensating Controls | Policy mentions exceptions but does not define compensating controls. | Accepted risks may lack mitigating safeguards. | Require documented compensating controls for approved SoD or access exceptions. | Medium |

## Detailed Gap Analysis

### GAP-001: Access Review Frequency Not Defined

The policy states that access reviews must be performed periodically, but it does not define how often reviews must occur.

**Risk:** Different teams may interpret periodic review differently, leading to inconsistent control operation.

**Recommended Update:** Define review frequency by access sensitivity. For example, privileged access may be reviewed monthly or quarterly, while standard access may be reviewed quarterly or semiannually.

---

### GAP-002: Deprovisioning SLA Not Defined

The policy requires terminated users to be deprovisioned, but it does not define the expected removal timeframe.

**Risk:** Terminated users may retain access longer than intended.

**Recommended Update:** Define a measurable offboarding SLA and require evidence of completion.

---

### GAP-003: Privileged Access Monitoring Not Defined

The policy requires privileged access to be restricted but does not define monitoring, logging, or review expectations.

**Risk:** Administrative misuse or unauthorized activity may not be detected timely.

**Recommended Update:** Require monitoring of privileged access, periodic review, and escalation of suspicious activity.

---

### GAP-004: Exception Expiration Enforcement Missing

The policy requires expiration dates for exceptions but does not define how expiration will be enforced.

**Risk:** Temporary access exceptions may become long-term access.

**Recommended Update:** Require exception owner review, expiration tracking, and removal of expired exceptions.

---

### GAP-005: Evidence Retention Period Missing

The policy requires evidence retention but does not specify how long evidence must be retained.

**Risk:** Audit evidence may not be available when needed.

**Recommended Update:** Define a retention period aligned to audit, legal, and regulatory expectations.

---

### GAP-006: SoD Review Ownership Missing

The policy requires Segregation of Duties enforcement but does not clearly assign ownership.

**Risk:** SoD conflicts may not be reviewed, remediated, or tracked consistently.

**Recommended Update:** Assign IAM/GRC ownership for SoD rule maintenance, conflict review, remediation tracking, and exception approval.

---

### GAP-007: AI Agent Logging Missing

The policy requires human approval for AI-assisted access review but does not specify logging requirements.

**Risk:** AI recommendations and human decisions may lack traceability.

**Recommended Update:** Require AI recommendation logs, human decision records, approval timestamps, reviewer identity, and final actions taken.

## Human-in-the-Loop Statement

The AI agent may assist with policy mapping and gap identification, but final control interpretation, risk acceptance, and policy approval must remain with human GRC, IAM, legal, compliance, and business stakeholders.

## Portfolio Value

This artifact demonstrates:

- GRC gap analysis.
- Policy interpretation.
- IAM control review.
- Audit readiness thinking.
- AI governance awareness.
- Risk-based recommendation writing.
