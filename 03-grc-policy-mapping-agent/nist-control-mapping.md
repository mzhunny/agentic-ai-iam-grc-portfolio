# NIST-Style Control Mapping

## Mapping Purpose

This document maps the fictional Sample Access Control Policy to NIST-style access control, audit, identification/authentication, and risk management control areas.

This is a portfolio demonstration and is not an official compliance assessment.

## Mapping Table

| Policy Statement | NIST-Style Control Area | Mapping Rationale | Evidence Needed | Notes |
|---|---|---|---|---|
| AC-01: Access Must Be Role-Based | Access Control / Least Privilege | The policy requires access based on role, department, and business need. | RBAC matrix, access request records, role design documentation | Supports least privilege and role-based provisioning. |
| AC-02: Access Requests Must Be Approved | Access Control / Account Management | The policy requires manager or system owner approval before provisioning. | Access request tickets, approval workflow records, system owner approvals | Approval evidence should show requester, approver, date, and access granted. |
| AC-03: Joiner-Mover-Leaver Events Must Be Reviewed | Access Control / Account Management | The policy requires access review during onboarding, transfer, and termination events. | HR event logs, JML tickets, access change records | JML review should include role changes and removal of old access. |
| AC-04: Terminated Users Must Be Deprovisioned | Access Control / Account Management | The policy requires removal or disabling of terminated user access. | Termination report, deprovisioning ticket, system access removal evidence | Timeliness should be tested against internal SLA. |
| AC-05: Privileged Access Must Be Restricted | Access Control / Privileged Account Management | The policy limits administrative access to authorized users with documented business need. | Privileged access list, approval records, periodic privileged access review | Privileged access should be reviewed more frequently. |
| AC-06: Segregation of Duties Must Be Enforced | Access Control / Separation of Duties | The policy prevents conflicting permissions without independent review. | SoD rules matrix, conflict report, remediation evidence | Critical for finance, payroll, IAM, and audit workflows. |
| AC-07: Access Reviews Must Be Performed Periodically | Access Control / Periodic Review | The policy requires periodic access review and documentation. | Access review campaign evidence, reviewer sign-off, exception tracking | Evidence should show scope, reviewers, findings, and remediation. |
| AC-08: Access Exceptions Must Be Documented | Risk Management / Exception Management | The policy requires justification, approval, expiration, and risk acceptance for exceptions. | Exception log, approval records, expiration tracking | Exceptions should not remain open indefinitely. |
| AC-09: Audit Evidence Must Be Retained | Audit and Accountability / Evidence Retention | The policy requires retention of approvals, reviews, deprovisioning, and remediation evidence. | Evidence repository, retention schedule, audit package | Evidence must support control operation during review period. |
| AC-10: AI-Assisted Access Review Must Require Human Approval | Risk Management / System and Services Governance | The policy restricts AI agents from approving or changing access without human approval. | AI workflow documentation, approval logs, agent permission review | Supports human-in-the-loop AI governance. |

## Control Coverage Summary

The sample policy covers the following major control themes:

- Role-based access control
- Least privilege
- Access approval
- Joiner-Mover-Leaver review
- Terminated user deprovisioning
- Privileged access management
- Segregation of Duties
- Periodic access review
- Exception management
- Audit evidence retention
- Human-in-the-loop AI governance

## Mapping Limitations

- This is a simulated mapping for portfolio purposes.
- It does not replace official NIST control interpretation.
- Control IDs are intentionally generalized as NIST-style areas rather than formal attestations.
- A real assessment would require organization-specific systems, control owners, audit scope, and evidence.
