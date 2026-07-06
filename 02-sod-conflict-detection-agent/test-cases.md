# Test Cases: SoD Conflict Detection Agent

## Test Case Summary

These test cases validate that the simulated SoD Conflict Detection Agent can identify conflicting permission combinations using fictional data.

| Test Case ID | Scenario | Expected Result | Priority |
|---|---|---|---|
| TC-SOD-001 | User has no SoD conflict | No conflict finding | High |
| TC-SOD-002 | User can create vendor and approve payment | Critical conflict finding | Critical |
| TC-SOD-003 | User can create and approve invoice | High conflict finding | High |
| TC-SOD-004 | User can administer users and approve role assignments | Critical conflict finding | Critical |
| TC-SOD-005 | User can update and approve payroll | Critical conflict finding | Critical |
| TC-SOD-006 | User can offboard employee and administer system access | High conflict finding | High |
| TC-SOD-007 | User can upload and approve audit evidence | High conflict finding | High |
| TC-SOD-008 | User can configure system and delete logs | Critical conflict finding | Critical |
| TC-SOD-009 | User can perform access review and approve access exceptions | High conflict finding | High |

---

## TC-SOD-001: Validate User with No SoD Conflict

**Rule Reference:** None  
**Test Data:** S2001 Tamara Cole

### Preconditions

- User has VENDOR_VIEW, INVOICE_CREATE, and PAYMENT_RECONCILE.
- User does not have any defined conflicting permission pair.

### Test Steps

1. Load `sample-access-conflicts.csv`.
2. Locate user S2001.
3. Compare current permissions to `sod-rules-matrix.csv`.
4. Confirm no matching conflict pair exists.

### Expected Result

The agent does not generate a SoD conflict finding.

### Status

Designed

---

## TC-SOD-002: Detect Vendor Create and Payment Approve Conflict

**Rule Reference:** SOD-001  
**Test Data:** S2002 Derrick Wells

### Preconditions

- User has VENDOR_CREATE.
- User has PAYMENT_APPROVE.

### Test Steps

1. Load user S2002.
2. Compare permissions to rule SOD-001.
3. Confirm both conflicting permissions are present.
4. Generate conflict finding.

### Expected Result

The agent flags a Critical SoD conflict because the user can create vendors and approve payments.

### Status

Designed

---

## TC-SOD-003: Detect Invoice Create and Invoice Approve Conflict

**Rule Reference:** SOD-002  
**Test Data:** S2003 Olivia Grant

### Preconditions

- User has INVOICE_CREATE.
- User has INVOICE_APPROVE.

### Test Steps

1. Load user S2003.
2. Compare permissions to rule SOD-002.
3. Confirm both conflicting permissions are present.
4. Generate conflict finding.

### Expected Result

The agent flags a High SoD conflict because the user can create and approve invoices.

### Status

Designed

---

## TC-SOD-004: Detect User Admin and Role Approval Conflict

**Rule Reference:** SOD-004  
**Test Data:** S2004 Kevin Morris

### Preconditions

- User has USER_ADMIN.
- User has ROLE_ASSIGNMENT_APPROVE.

### Test Steps

1. Load user S2004.
2. Compare permissions to rule SOD-004.
3. Confirm both conflicting permissions are present.
4. Generate conflict finding.

### Expected Result

The agent flags a Critical SoD conflict because the user can administer accounts and approve role assignments.

### Status

Designed

---

## TC-SOD-005: Detect Payroll Update and Payroll Approval Conflict

**Rule Reference:** SOD-005  
**Test Data:** S2006 Andre Price

### Preconditions

- User has PAYROLL_UPDATE.
- User has PAYROLL_APPROVE.

### Test Steps

1. Load user S2006.
2. Compare permissions to rule SOD-005.
3. Confirm both conflicting permissions are present.
4. Generate conflict finding.

### Expected Result

The agent flags a Critical SoD conflict because the user can update and approve payroll changes.

### Status

Designed

---

## TC-SOD-006: Detect Offboarding and User Admin Conflict

**Rule Reference:** SOD-006  
**Test Data:** S2008 Malik Turner

### Preconditions

- User has OFFBOARDING_UPDATE.
- User has USER_ADMIN.

### Test Steps

1. Load user S2008.
2. Compare permissions to rule SOD-006.
3. Confirm both conflicting permissions are present.
4. Generate conflict finding.

### Expected Result

The agent flags a High SoD conflict because the user can update offboarding status and administer access.

### Status

Designed

---

## TC-SOD-007: Detect Audit Evidence Upload and Approval Conflict

**Rule Reference:** SOD-007  
**Test Data:** S2010 Franklin Scott

### Preconditions

- User has EVIDENCE_UPLOAD.
- User has EVIDENCE_APPROVE.

### Test Steps

1. Load user S2010.
2. Compare permissions to rule SOD-007.
3. Confirm both conflicting permissions are present.
4. Generate conflict finding.

### Expected Result

The agent flags a High SoD conflict because the user can both upload and approve audit evidence.

### Status

Designed

---

## TC-SOD-008: Detect System Config and Log Delete Conflict

**Rule Reference:** SOD-010  
**Test Data:** S2011 Natalie Ford

### Preconditions

- User has SYSTEM_CONFIG.
- User has LOG_DELETE.

### Test Steps

1. Load user S2011.
2. Compare permissions to rule SOD-010.
3. Confirm both conflicting permissions are present.
4. Generate conflict finding.

### Expected Result

The agent flags a Critical SoD conflict because the user can configure systems and delete logs.

### Status

Designed

---

## TC-SOD-009: Detect Access Review and Exception Approval Conflict

**Rule Reference:** SOD-009  
**Test Data:** S2012 Grace Miller

### Preconditions

- User has ACCESS_REVIEW.
- User has ACCESS_EXCEPTION_APPROVE.

### Test Steps

1. Load user S2012.
2. Compare permissions to rule SOD-009.
3. Confirm both conflicting permissions are present.
4. Generate conflict finding.

### Expected Result

The agent flags a High SoD conflict because the user can perform access reviews and approve access exceptions.

### Status

Designed
