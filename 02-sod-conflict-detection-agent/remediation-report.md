# Remediation Report: SoD Conflict Detection Agent

## Report Purpose

This report summarizes simulated Segregation of Duties conflicts identified from fictional user permission data.

The purpose is to demonstrate IAM risk analysis, GRC control thinking, Security QA validation, and audit-ready remediation documentation.

## Review Scope

| Item | Description |
|---|---|
| Review Period | Q3-2026 |
| Data Source | Fictional sample access conflict data |
| Control Area | IAM / Segregation of Duties / Access Governance |
| Review Type | Simulated AI-assisted SoD conflict detection |
| Human Approval Required | Yes |

## Executive Summary

The simulated SoD review identified multiple high and critical-risk conflicts across finance, IAM, payroll, HR, audit, and IT operations. These conflicts represent scenarios where one user has permissions that should be separated to preserve financial integrity, access governance, audit trail reliability, and independent review.

The highest-risk issues include users who can create vendors and approve payments, administer accounts and approve role assignments, update and approve payroll, and configure systems while deleting logs.

## Findings Overview

| Finding ID | User ID | User Name | Matching Rule | Conflict | Risk Rating | Recommended Action |
|---|---|---|---|---|---|---|
| SOD-F-001 | S2002 | Derrick Wells | SOD-001 | VENDOR_CREATE + PAYMENT_APPROVE | Critical | Remove one permission or document compensating control. |
| SOD-F-002 | S2003 | Olivia Grant | SOD-002 | INVOICE_CREATE + INVOICE_APPROVE | High | Separate invoice creation and approval. |
| SOD-F-003 | S2004 | Kevin Morris | SOD-004 | USER_ADMIN + ROLE_ASSIGNMENT_APPROVE | Critical | Remove role approval or require independent IAM approval. |
| SOD-F-004 | S2006 | Andre Price | SOD-005 | PAYROLL_UPDATE + PAYROLL_APPROVE | Critical | Separate payroll update and approval duties. |
| SOD-F-005 | S2008 | Malik Turner | SOD-006 | OFFBOARDING_UPDATE + USER_ADMIN | High | Require IAM review and deprovisioning audit evidence. |
| SOD-F-006 | S2010 | Franklin Scott | SOD-007 | EVIDENCE_UPLOAD + EVIDENCE_APPROVE | High | Separate evidence preparer and reviewer. |
| SOD-F-007 | S2011 | Natalie Ford | SOD-010 | SYSTEM_CONFIG + LOG_DELETE | Critical | Remove log deletion or require restricted break-glass control. |
| SOD-F-008 | S2012 | Grace Miller | SOD-009 | ACCESS_REVIEW + ACCESS_EXCEPTION_APPROVE | High | Route exception approval to independent control owner. |

---

## SOD-F-001: Vendor Creation and Payment Approval Conflict

**User:** Derrick Wells  
**User ID:** S2002  
**Department:** Finance  
**Role:** AP Manager  
**Matching Rule:** SOD-001  
**Risk Rating:** Critical

### Finding Details

The user has both VENDOR_CREATE and PAYMENT_APPROVE permissions.

### Risk Rationale

This combination could allow one person to create a vendor and approve payments to that vendor. In a real environment, this may create fraud, financial loss, or audit control failure risk.

### Recommended Remediation

- Remove either VENDOR_CREATE or PAYMENT_APPROVE.
- Validate business justification if temporary access is required.
- Require documented compensating control if access must remain.
- Obtain approval from Finance management and GRC.

---

## SOD-F-002: Invoice Creation and Invoice Approval Conflict

**User:** Olivia Grant  
**User ID:** S2003  
**Department:** Finance  
**Role:** Invoice Processor  
**Matching Rule:** SOD-002  
**Risk Rating:** High

### Finding Details

The user has both INVOICE_CREATE and INVOICE_APPROVE permissions.

### Risk Rationale

This combination may allow the same user to create and approve invoices without independent review.

### Recommended Remediation

- Remove INVOICE_APPROVE from the invoice processor role.
- Route invoice approvals to a manager or independent approver.
- Review historical approvals if needed.

---

## SOD-F-003: User Administration and Role Assignment Approval Conflict

**User:** Kevin Morris  
**User ID:** S2004  
**Department:** Information Security  
**Role:** IAM Analyst  
**Matching Rule:** SOD-004  
**Risk Rating:** Critical

### Finding Details

The user has both USER_ADMIN and ROLE_ASSIGNMENT_APPROVE permissions.

### Risk Rationale

This combination could allow one user to administer accounts and approve role assignments, creating privilege escalation risk.

### Recommended Remediation

- Remove role assignment approval from the same user who administers accounts.
- Require IAM manager approval for role changes.
- Ensure privileged actions are logged and reviewed.

---

## SOD-F-004: Payroll Update and Payroll Approval Conflict

**User:** Andre Price  
**User ID:** S2006  
**Department:** Payroll  
**Role:** Payroll Manager  
**Matching Rule:** SOD-005  
**Risk Rating:** Critical

### Finding Details

The user has both PAYROLL_UPDATE and PAYROLL_APPROVE permissions.

### Risk Rationale

This combination could allow one user to update and approve payroll changes, creating payroll fraud and compliance risk.

### Recommended Remediation

- Separate payroll update and approval responsibilities.
- Require independent approval for payroll changes.
- Review recent payroll changes for suspicious activity if this were a real environment.

---

## SOD-F-005: HR Offboarding and User Administration Conflict

**User:** Malik Turner  
**User ID:** S2008  
**Department:** Human Resources  
**Role:** HRIS Admin  
**Matching Rule:** SOD-006  
**Risk Rating:** High

### Finding Details

The user has both OFFBOARDING_UPDATE and USER_ADMIN permissions.

### Risk Rationale

This combination could allow one user to update offboarding records and control system access, reducing independent validation between HR and IAM.

### Recommended Remediation

- Keep HR employment status updates separate from IAM access administration.
- Require IAM review of offboarding-related access changes.
- Preserve deprovisioning ticket evidence.

---

## SOD-F-006: Audit Evidence Upload and Approval Conflict

**User:** Franklin Scott  
**User ID:** S2010  
**Department:** Audit  
**Role:** Audit Manager  
**Matching Rule:** SOD-007  
**Risk Rating:** High

### Finding Details

The user has both EVIDENCE_UPLOAD and EVIDENCE_APPROVE permissions.

### Risk Rationale

This combination may allow the same person to prepare and approve audit evidence without independent review.

### Recommended Remediation

- Separate evidence upload and approval responsibilities.
- Require independent review by a control owner or audit lead.
- Document final approval and review notes.

---

## SOD-F-007: System Configuration and Log Deletion Conflict

**User:** Natalie Ford  
**User ID:** S2011  
**Department:** IT Operations  
**Role:** System Administrator  
**Matching Rule:** SOD-010  
**Risk Rating:** Critical

### Finding Details

The user has both SYSTEM_CONFIG and LOG_DELETE permissions.

### Risk Rationale

This combination could allow a user to make system changes and delete logs that would otherwise support detection, monitoring, and audit review.

### Recommended Remediation

- Remove LOG_DELETE from standard administrator access.
- Restrict log deletion to break-glass access with approval.
- Require monitoring of privileged system configuration activity.

---

## SOD-F-008: Access Review and Exception Approval Conflict

**User:** Grace Miller  
**User ID:** S2012  
**Department:** Information Security  
**Role:** GRC Analyst  
**Matching Rule:** SOD-009  
**Risk Rating:** High

### Finding Details

The user has both ACCESS_REVIEW and ACCESS_EXCEPTION_APPROVE permissions.

### Risk Rationale

This combination could allow the same person to perform an access review and approve exceptions, reducing independent oversight.

### Recommended Remediation

- Route exception approvals to an independent control owner.
- Require management approval for accepted risk.
- Document exception rationale and expiration date.

## Human-in-the-Loop Statement

The AI agent only identifies potential conflicts and recommends remediation. It must not remove access, approve exceptions, or close remediation actions without human review from IAM, GRC, business management, and control owners.

## Audit Evidence Needed

- Approved SoD rules matrix.
- User permission extract for the review period.
- Conflict findings report.
- Manager review notes.
- Remediation tickets.
- Exception approval documentation.
- Control owner sign-off.
- Evidence of completed access changes, if applicable.

## Portfolio Value

This report demonstrates:

- Segregation of Duties analysis.
- IAM and GRC risk classification.
- Security QA validation thinking.
- Business impact explanation.
- Audit-ready remediation documentation.
- Human-in-the-loop Agentic AI governance.
