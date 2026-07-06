# Test Cases: IAM/RBAC Access Review Agent

## Test Case Summary

These test cases validate the simulated IAM/RBAC Access Review Agent logic using fictional sample data.

| Test Case ID | Scenario | Expected Result | Priority |
|---|---|---|---|
| TC-001 | User access fully matches RBAC matrix | No exception finding | High |
| TC-002 | User has excessive finance access | Excessive access finding | High |
| TC-003 | Finance analyst has payment approval access | Excessive/restricted access finding | High |
| TC-004 | HR user is missing required access | Missing access finding | Medium |
| TC-005 | Terminated user has active access | Critical finding | Critical |
| TC-006 | Department-role mismatch exists | Mismatch finding | Medium |
| TC-007 | Auditor missing required access | Missing access finding | Medium |
| TC-008 | Finance manager has restricted admin access | Critical/high finding | Critical |

---

## TC-001: Validate Fully Aligned Customer Support Access

**Requirement Reference:** BR-001  
**User Story Reference:** US-001  
**Test Data:** U1001 Alicia Reed

### Preconditions

- RBAC matrix includes Customer Support Specialist role.
- User is active.
- User has CRM_VIEW, TICKET_CREATE, and TICKET_UPDATE.

### Test Steps

1. Load `sample-user-access-data.csv`.
2. Locate user U1001.
3. Match user role to Customer Support Specialist in `rbac-matrix.csv`.
4. Compare current access to required and optional access.
5. Confirm no restricted permissions are assigned.

### Expected Result

The agent marks the user's access as aligned and does not create an exception finding.

### Status

Designed

---

## TC-002: Flag Excessive Finance Access for Customer Support User

**Requirement Reference:** BR-002  
**User Story Reference:** US-002  
**Test Data:** U1002 Marcus Hill

### Preconditions

- User is active.
- User role is Customer Support Specialist.
- User has FINANCE_APPROVE access.

### Test Steps

1. Load user U1002.
2. Match role to Customer Support Specialist.
3. Compare current access to approved required and optional access.
4. Identify FINANCE_APPROVE as restricted access for the role.
5. Generate risk finding.

### Expected Result

The agent flags FINANCE_APPROVE as excessive/restricted access and assigns a High risk rating.

### Status

Designed

---

## TC-003: Flag Payment Approval Access for Finance Analyst

**Requirement Reference:** BR-002  
**User Story Reference:** US-002  
**Test Data:** U1004 Sean Brooks

### Preconditions

- User is active.
- User role is Finance Analyst.
- User has PAYMENT_APPROVE access.

### Test Steps

1. Load user U1004.
2. Match role to Finance Analyst.
3. Compare current access to approved access.
4. Identify PAYMENT_APPROVE as restricted access for Finance Analyst.
5. Generate risk finding.

### Expected Result

The agent flags PAYMENT_APPROVE as excessive/restricted access and assigns a High risk rating.

### Status

Designed

---

## TC-004: Flag Missing Required HR Access

**Requirement Reference:** BR-003  
**User Story Reference:** US-003  
**Test Data:** U1005 Kimberly Stone

### Preconditions

- User is active.
- User role is HR Specialist.
- Required role access includes EMPLOYEE_VIEW, ONBOARDING_UPDATE, and OFFBOARDING_UPDATE.
- User does not have OFFBOARDING_UPDATE.

### Test Steps

1. Load user U1005.
2. Match role to HR Specialist.
3. Compare current access to required access.
4. Identify OFFBOARDING_UPDATE as missing.
5. Generate missing access finding.

### Expected Result

The agent flags OFFBOARDING_UPDATE as missing required access and assigns a Medium operational risk rating.

### Status

Designed

---

## TC-005: Flag Terminated User with Active Access

**Requirement Reference:** BR-004  
**User Story Reference:** US-004  
**Test Data:** U1007 Monica Lewis

### Preconditions

- User employment status is Terminated.
- User still has USER_ADMIN, SYSTEM_CONFIG, and LOG_VIEW access.

### Test Steps

1. Load user U1007.
2. Check employment status.
3. Check current active access.
4. Determine whether access remains assigned after termination.
5. Generate critical finding.

### Expected Result

The agent flags the user as a terminated user with active access and assigns a Critical risk rating.

### Status

Designed

---

## TC-006: Flag Department-Role Mismatch

**Requirement Reference:** BR-005  
**User Story Reference:** US-005  
**Test Data:** U1011 Erica Johnson

### Preconditions

- User department is Human Resources.
- User role is Finance Analyst.
- Finance Analyst role belongs to Finance department.

### Test Steps

1. Load user U1011.
2. Match Finance Analyst role to RBAC matrix.
3. Compare user's department to expected role department.
4. Generate mismatch finding.

### Expected Result

The agent flags a department-role mismatch and recommends manager confirmation.

### Status

Designed

---

## TC-007: Flag Missing Auditor Access

**Requirement Reference:** BR-003  
**User Story Reference:** US-003  
**Test Data:** U1012 Samuel Green

### Preconditions

- User role is Auditor.
- Required access includes ACCESS_REVIEW, REPORT_VIEW, and EVIDENCE_VIEW.
- User does not have EVIDENCE_VIEW.

### Test Steps

1. Load user U1012.
2. Match role to Auditor.
3. Compare current access to required access.
4. Identify missing EVIDENCE_VIEW.
5. Generate missing access finding.

### Expected Result

The agent flags EVIDENCE_VIEW as missing required access and assigns a Medium risk rating.

### Status

Designed

---

## TC-008: Flag Restricted Admin Access for Finance Manager

**Requirement Reference:** BR-002  
**User Story Reference:** US-002  
**Test Data:** U1010 David Nguyen

### Preconditions

- User role is Finance Manager.
- Finance Manager restricted access includes USER_ADMIN and PAYROLL_ADMIN.
- User has USER_ADMIN.

### Test Steps

1. Load user U1010.
2. Match role to Finance Manager.
3. Compare current access to restricted access.
4. Identify USER_ADMIN as restricted for role.
5. Generate elevated risk finding.

### Expected Result

The agent flags USER_ADMIN as restricted access and assigns a Critical or High risk rating.

### Status

Designed
