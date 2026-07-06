# ISO-Style Control Mapping

## Mapping Purpose

This document maps the fictional Sample Access Control Policy to ISO-style information security control themes related to identity, access control, privileged access, audit evidence, and governance.

This is a portfolio demonstration and is not an official ISO 27001 certification assessment.

## Mapping Table

| Policy Statement | ISO-Style Control Theme | Mapping Rationale | Evidence Needed | Notes |
|---|---|---|---|---|
| AC-01: Access Must Be Role-Based | Identity and Access Control | The policy requires access based on role, department, and business need. | RBAC matrix, approved role catalog, access provisioning records | Supports least privilege and access restriction. |
| AC-02: Access Requests Must Be Approved | User Access Management | The policy requires approval before new, modified, or elevated access is provisioned. | Access request tickets, manager approvals, system owner approvals | Evidence should show approval before access was granted. |
| AC-03: Joiner-Mover-Leaver Events Must Be Reviewed | Identity Lifecycle Management | The policy requires review during onboarding, transfer, and termination events. | HR event reports, JML workflow tickets, access change logs | Mover events should remove old access, not only add new access. |
| AC-04: Terminated Users Must Be Deprovisioned | Removal or Adjustment of Access Rights | The policy requires timely removal or disabling of terminated user access. | Termination report, deprovisioning record, access disablement evidence | Timeliness metrics should be included in a mature control. |
| AC-05: Privileged Access Must Be Restricted | Privileged Access Rights | The policy limits administrative access to users with documented business need. | Privileged user list, approvals, privileged access review evidence | Privileged access should be monitored and reviewed frequently. |
| AC-06: Segregation of Duties Must Be Enforced | Segregation of Duties | The policy requires conflicting permissions to be separated or independently reviewed. | SoD rules, conflict report, remediation tickets, exception approvals | High-risk duties should not be combined without control owner approval. |
| AC-07: Access Reviews Must Be Performed Periodically | Review of User Access Rights | The policy requires recurring review and documentation of user access. | Access certification records, reviewer sign-off, exception log | Review frequency should be defined by access sensitivity. |
| AC-08: Access Exceptions Must Be Documented | Information Security Risk Treatment | The policy requires justification, approval, expiration, and risk acceptance for exceptions. | Exception register, approval evidence, expiration tracking | Exceptions should be time-bound and reviewed. |
| AC-09: Audit Evidence Must Be Retained | Compliance and Audit Evidence Management | The policy requires retention of access approvals, reviews, deprovisioning, and remediation evidence. | Evidence repository, retention requirements, audit package | Evidence should be complete, accurate, and tied to the review period. |
| AC-10: AI-Assisted Access Review Must Require Human Approval | Governance of AI-Assisted Security Processes | The policy requires human approval for AI-assisted access decisions. | AI workflow design, agent permissions, human approval logs | Supports accountable use of AI in security workflows. |

## Control Coverage Summary

The sample policy supports these ISO-style themes:

- Access control policy and implementation
- Identity lifecycle management
- User access provisioning and approvals
- Privileged access rights
- Review of user access rights
- Segregation of Duties
- Evidence retention
- Risk acceptance and exception governance
- Human accountability for AI-assisted security workflows

## Mapping Limitations

- This is a simulated mapping for portfolio purposes.
- It does not replace official ISO 27001 or ISO 27002 interpretation.
- A real ISO assessment would require evidence from actual systems, process owners, and internal control records.
- AI governance requirements may vary based on organization, region, industry, and regulatory expectations.
