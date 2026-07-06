# Audit Request Examples: Audit Evidence Review Agent

## Document Purpose

This document contains fictional audit request examples for IAM, RBAC, access reviews, deprovisioning, privileged access, Segregation of Duties, and AI-assisted review governance.

The goal is to demonstrate how an Audit Evidence Review Agent can help organize audit requests, identify evidence needs, and prepare control-owner questions while keeping final audit response approval with humans.

## Audit Request Summary

| Request ID | Control Area | Audit Request | Priority |
|---|---|---|---|
| AR-001 | Access Review | Provide evidence that user access was reviewed for Q3-2026. | High |
| AR-002 | Terminated User Access | Provide evidence that terminated users were deprovisioned timely. | Critical |
| AR-003 | Privileged Access | Provide evidence that privileged access was reviewed and approved. | Critical |
| AR-004 | RBAC | Provide evidence that access is assigned based on approved roles. | High |
| AR-005 | Segregation of Duties | Provide evidence that SoD conflicts were identified and remediated. | High |
| AR-006 | Access Exceptions | Provide evidence that access exceptions were approved and time-bound. | Medium |
| AR-007 | Audit Evidence Retention | Provide evidence that access control artifacts are retained for audit review. | Medium |
| AR-008 | AI-Assisted Review | Provide evidence that AI-assisted access review recommendations required human approval. | High |

---

## AR-001: Periodic User Access Review

**Audit Request:** Provide evidence that user access was reviewed for Q3-2026 and that exceptions were documented and routed for remediation.

### Evidence Expected

- Access review campaign scope.
- User access extract for the review period.
- Approved RBAC matrix or role catalog.
- Reviewer assignments.
- Completed review sign-off.
- Exception report.
- Remediation tracking evidence.

### Control Owner Questions

- Who performed the review?
- What systems and users were included?
- Were privileged users included?
- How were exceptions tracked?
- Were remediation actions completed?

---

## AR-002: Terminated User Deprovisioning

**Audit Request:** Provide evidence that terminated users were removed or disabled according to the organization's offboarding requirements.

### Evidence Expected

- Termination report from HR.
- IAM deprovisioning ticket.
- Account disablement or removal evidence.
- Timestamp showing when access was disabled.
- Exception or delay approval, if applicable.

### Control Owner Questions

- What is the required deprovisioning SLA?
- Were any terminated users deprovisioned late?
- Were privileged accounts checked separately?
- Were downstream applications included?

---

## AR-003: Privileged Access Review

**Audit Request:** Provide evidence that privileged access was approved, reviewed, and limited to authorized users.

### Evidence Expected

- Privileged access list.
- Business justification for privileged access.
- Manager or system owner approval.
- Privileged access review results.
- Evidence of removed or remediated access.

### Control Owner Questions

- How is privileged access defined?
- How often is privileged access reviewed?
- Are service accounts included?
- Are privileged actions logged and monitored?

---

## AR-004: RBAC Alignment

**Audit Request:** Provide evidence that user access is assigned based on approved roles and business need.

### Evidence Expected

- Approved RBAC matrix.
- Role catalog.
- User-role assignments.
- Access request and approval records.
- Access review exception report.

### Control Owner Questions

- Who owns the RBAC matrix?
- How often are roles reviewed?
- How are role changes approved?
- Are department-role mismatches reviewed?

---

## AR-005: Segregation of Duties Review

**Audit Request:** Provide evidence that Segregation of Duties conflicts were identified, reviewed, and remediated or formally approved.

### Evidence Expected

- Approved SoD rules matrix.
- User permission extract.
- Conflict report.
- Manager review notes.
- Remediation tickets.
- Exception approvals and compensating controls.

### Control Owner Questions

- Who owns SoD rules?
- How often are SoD conflicts reviewed?
- What conflicts are considered critical?
- How are accepted exceptions approved and tracked?

---

## AR-006: Access Exception Governance

**Audit Request:** Provide evidence that temporary or exception-based access was approved, justified, and reviewed before expiration.

### Evidence Expected

- Exception register.
- Business justification.
- Approval evidence.
- Expiration date.
- Risk acceptance, if applicable.
- Evidence of removal or recertification.

### Control Owner Questions

- Are exceptions time-bound?
- Who approves exceptions?
- Are expired exceptions removed automatically or manually?
- Are high-risk exceptions reviewed by GRC?

---

## AR-007: Evidence Retention

**Audit Request:** Provide evidence that access control artifacts are retained and available for audit review.

### Evidence Expected

- Evidence retention policy.
- Access review evidence repository.
- Retention schedule.
- Sample retained artifacts.
- Evidence owner or custodian list.

### Control Owner Questions

- How long is evidence retained?
- Where is evidence stored?
- Who can modify evidence?
- Is evidence protected from unauthorized changes?

---

## AR-008: AI-Assisted Access Review Human Approval

**Audit Request:** Provide evidence that AI-assisted access review recommendations required human review and approval before access changes or risk decisions were made.

### Evidence Expected

- AI agent workflow documentation.
- AI recommendation logs.
- Human approval records.
- Final decision notes.
- Agent permission review.
- Evidence that the AI agent cannot grant, remove, or approve access automatically.

### Control Owner Questions

- What actions can the AI agent perform?
- What actions require human approval?
- Are AI recommendations logged?
- Who approves final access decisions?
- How are incorrect AI recommendations corrected?

## Portfolio Value

These examples demonstrate audit request interpretation, evidence planning, control-owner communication, IAM/GRC awareness, and AI governance review.
