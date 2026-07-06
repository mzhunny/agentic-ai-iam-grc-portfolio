# Risk Findings Report: IAM/RBAC Access Review Agent

## Report Purpose

This report summarizes simulated access review findings generated from fictional user access data and an approved RBAC matrix.

The purpose is to demonstrate IAM/RBAC analysis, access governance review, risk classification, and audit-ready documentation.

## Review Scope

| Item | Description |
|---|---|
| Review Period | Q3-2026 |
| Data Source | Fictional sample user access data |
| Control Area | IAM / RBAC / Access Review |
| Review Type | Simulated AI-assisted access review |
| Human Approval Required | Yes |

## Executive Summary

The simulated access review identified multiple access governance exceptions, including excessive access, restricted access, missing required access, department-role mismatch, and terminated user access.

The most critical issue is a terminated user who still has active administrative access. This finding would require immediate IAM and security review in a real-world environment.

## Findings Overview

| Finding ID | User ID | User Name | Finding Type | Risk Rating | Recommended Action |
|---|---|---|---|---|---|
| F-001 | U1002 | Marcus Hill | Excessive/restricted access | High | Review and remove FINANCE_APPROVE if not approved. |
| F-002 | U1004 | Sean Brooks | Excessive/restricted access | High | Review and remove PAYMENT_APPROVE if not approved. |
| F-003 | U1005 | Kimberly Stone | Missing required access | Medium | Confirm whether OFFBOARDING_UPDATE is needed. |
| F-004 | U1007 | Monica Lewis | Terminated user with active access | Critical | Immediately review and disable active access. |
| F-005 | U1010 | David Nguyen | Restricted admin access | Critical | Review USER_ADMIN access and remove if inappropriate. |
| F-006 | U1011 | Erica Johnson | Department-role mismatch | Medium | Confirm role assignment with manager and HR. |
| F-007 | U1012 | Samuel Green | Missing required access | Medium | Confirm whether EVIDENCE_VIEW should be granted. |

---

## F-001: Customer Support User Has Finance Approval Access

**User:** Marcus Hill  
**User ID:** U1002  
**Department:** Customer Operations  
**Role:** Customer Support Specialist  
**Finding Type:** Excessive/restricted access  
**Risk Rating:** High

### Finding Details

The user has FINANCE_APPROVE access, which is listed as restricted access for the Customer Support Specialist role.

### Risk Rationale

Finance approval access could allow a user outside the Finance department to perform or influence financial approval activities. This creates access governance and potential financial control risk.

### Recommended Action

- Validate whether access was approved as an exception.
- Confirm with the user's manager.
- Remove FINANCE_APPROVE if no valid approval exists.
- Document final decision as audit evidence.

---

## F-002: Finance Analyst Has Payment Approval Access

**User:** Sean Brooks  
**User ID:** U1004  
**Department:** Finance  
**Role:** Finance Analyst  
**Finding Type:** Excessive/restricted access  
**Risk Rating:** High

### Finding Details

The user has PAYMENT_APPROVE access, which is restricted for the Finance Analyst role.

### Risk Rationale

Finance Analysts may reconcile or view financial data, but payment approval is a higher-risk permission that should be limited to authorized approvers.

### Recommended Action

- Confirm whether payment approval is job-required.
- Validate approval evidence.
- Remove access if it is not approved.
- Review whether SoD controls are impacted.

---

## F-003: HR Specialist Missing Offboarding Access

**User:** Kimberly Stone  
**User ID:** U1005  
**Department:** Human Resources  
**Role:** HR Specialist  
**Finding Type:** Missing required access  
**Risk Rating:** Medium

### Finding Details

The HR Specialist role requires OFFBOARDING_UPDATE, but the user does not have this permission.

### Risk Rationale

Missing offboarding access may prevent HR from completing timely employee termination workflows, which can create downstream access removal delays.

### Recommended Action

- Confirm with HR manager whether the user performs offboarding duties.
- Grant access only if approved.
- Document approval and provisioning evidence.

---

## F-004: Terminated User Has Active Administrative Access

**User:** Monica Lewis  
**User ID:** U1007  
**Department:** IT Operations  
**Role:** System Administrator  
**Finding Type:** Terminated user with active access  
**Risk Rating:** Critical

### Finding Details

The user's employment status is Terminated, but the user still has active access: USER_ADMIN, SYSTEM_CONFIG, and LOG_VIEW.

### Risk Rationale

A terminated user with active administrative access represents a critical identity governance failure. In a real environment, this could create unauthorized access, data exposure, system change, and audit risk.

### Recommended Action

- Escalate immediately to IAM and Security Operations.
- Disable all active access after authorized review.
- Confirm termination date and offboarding ticket.
- Validate deprovisioning evidence.
- Document root cause and corrective action.

---

## F-005: Finance Manager Has Restricted User Admin Access

**User:** David Nguyen  
**User ID:** U1010  
**Department:** Finance  
**Role:** Finance Manager  
**Finding Type:** Restricted admin access  
**Risk Rating:** Critical

### Finding Details

The user has USER_ADMIN access, which is restricted for the Finance Manager role.

### Risk Rationale

Combining finance approval responsibilities with user administration privileges can create elevated access governance and Segregation of Duties risk.

### Recommended Action

- Validate whether USER_ADMIN was formally approved.
- Confirm business justification.
- Remove access if not required.
- Review related SoD rules.

---

## F-006: HR User Assigned Finance Analyst Role

**User:** Erica Johnson  
**User ID:** U1011  
**Department:** Human Resources  
**Role:** Finance Analyst  
**Finding Type:** Department-role mismatch  
**Risk Rating:** Medium

### Finding Details

The user's department is Human Resources, but the assigned role is Finance Analyst, which belongs to the Finance department.

### Risk Rationale

Department-role mismatch may indicate incorrect role assignment, outdated HR data, or inappropriate access provisioning.

### Recommended Action

- Confirm user's current job role with HR and manager.
- Update role assignment if incorrect.
- Review whether current access is still appropriate.

---

## F-007: Auditor Missing Evidence View Access

**User:** Samuel Green  
**User ID:** U1012  
**Department:** Audit  
**Role:** Auditor  
**Finding Type:** Missing required access  
**Risk Rating:** Medium

### Finding Details

The Auditor role requires EVIDENCE_VIEW, but the user does not have this permission.

### Risk Rationale

Missing evidence view access may prevent audit staff from reviewing required control evidence.

### Recommended Action

- Confirm audit responsibilities with manager.
- Grant EVIDENCE_VIEW only after approval.
- Document approval and access provisioning evidence.

## Human-in-the-Loop Statement

All findings in this report require human validation before remediation. The AI agent provides analysis and recommendations only. It must not directly grant, remove, or modify user access.
