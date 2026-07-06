# Validation Test Cases: Audit Evidence Review Agent

## Test Case Summary

These test cases validate that the simulated Audit Evidence Review Agent can evaluate evidence completeness, identify missing artifacts, generate control-owner questions, and preserve human approval requirements.

| Test Case ID | Scenario | Expected Result | Priority |
|---|---|---|---|
| TC-AUD-001 | Validate complete access review evidence | Evidence marked ready for human review | High |
| TC-AUD-002 | Identify missing reviewer sign-off | Evidence defect flagged | High |
| TC-AUD-003 | Identify missing terminated user deprovisioning timestamp | Critical defect flagged | Critical |
| TC-AUD-004 | Identify missing privileged access approval | High defect flagged | High |
| TC-AUD-005 | Identify missing SoD remediation evidence | High defect flagged | High |
| TC-AUD-006 | Identify access exception without expiration date | Medium/high defect flagged | High |
| TC-AUD-007 | Identify missing evidence retention period | Medium defect flagged | Medium |
| TC-AUD-008 | Verify AI-assisted review requires human approval | Human approval requirement preserved | Critical |

---

## TC-AUD-001: Validate Complete Access Review Evidence

**Audit Request Reference:** AR-001

### Preconditions

- Access review scope is available.
- User access extract is available.
- RBAC matrix is available.
- Reviewer sign-off is available.
- Exception report is available.
- Remediation tracking is available.

### Test Steps

1. Load evidence checklist for AR-001.
2. Confirm required evidence items are present.
3. Confirm review period is shown.
4. Confirm reviewer and sign-off are documented.
5. Confirm exceptions and remediation status are included.

### Expected Result

The agent marks the evidence package as ready for human control owner review.

### Status

Designed

---

## TC-AUD-002: Identify Missing Reviewer Sign-Off

**Audit Request Reference:** AR-001

### Preconditions

- Access review evidence exists.
- Reviewer sign-off is missing.

### Test Steps

1. Review access review evidence package.
2. Check whether final reviewer sign-off is present.
3. Flag missing sign-off if absent.
4. Generate a question for the IAM control owner.

### Expected Result

The agent flags the missing reviewer sign-off and asks who approved the final review results and where the sign-off is stored.

### Status

Designed

---

## TC-AUD-003: Identify Missing Deprovisioning Timestamp

**Audit Request Reference:** AR-002

### Preconditions

- Termination report exists.
- Deprovisioning ticket exists.
- Access disablement timestamp is missing.

### Test Steps

1. Review terminated user deprovisioning evidence.
2. Check whether termination date is shown.
3. Check whether access disablement date/time is shown.
4. Flag missing timestamp if absent.
5. Assign critical priority.

### Expected Result

The agent flags missing deprovisioning timestamp as a critical evidence defect because timeliness cannot be validated.

### Status

Designed

---

## TC-AUD-004: Identify Missing Privileged Access Approval

**Audit Request Reference:** AR-003

### Preconditions

- Privileged access list exists.
- Business justification or approval evidence is missing.

### Test Steps

1. Review privileged access evidence.
2. Check whether each privileged user has approval evidence.
3. Flag any user without approval.
4. Generate a question for the system owner.

### Expected Result

The agent flags missing privileged access approval and asks who approved privileged access and why it was needed.

### Status

Designed

---

## TC-AUD-005: Identify Missing SoD Remediation Evidence

**Audit Request Reference:** AR-005

### Preconditions

- SoD conflict report exists.
- Remediation tickets are missing or incomplete.

### Test Steps

1. Review SoD conflict report.
2. Check whether each high or critical conflict has a remediation decision.
3. Check whether remediation tickets show owner, date, and status.
4. Flag incomplete remediation evidence.

### Expected Result

The agent flags missing remediation evidence and asks whether conflicts were remediated, accepted, or covered by compensating controls.

### Status

Designed

---

## TC-AUD-006: Identify Exception Without Expiration Date

**Audit Request Reference:** AR-006

### Preconditions

- Access exception record exists.
- Business justification and approval exist.
- Expiration date is missing.

### Test Steps

1. Review exception register.
2. Check whether exception has approval.
3. Check whether exception has expiration date.
4. Flag missing expiration date.
5. Generate question for GRC control owner.

### Expected Result

The agent flags the exception as incomplete because temporary access lacks expiration tracking.

### Status

Designed

---

## TC-AUD-007: Identify Missing Evidence Retention Period

**Audit Request Reference:** AR-007

### Preconditions

- Evidence repository exists.
- Retention period is not documented.

### Test Steps

1. Review evidence retention materials.
2. Check whether retention schedule is defined.
3. Check whether owner is identified.
4. Flag missing retention period.

### Expected Result

The agent flags missing retention period and asks Compliance/GRC how long evidence must be retained.

### Status

Designed

---

## TC-AUD-008: Verify AI-Assisted Review Requires Human Approval

**Audit Request Reference:** AR-008

### Preconditions

- AI recommendation logs exist.
- Human approval records may or may not exist.

### Test Steps

1. Review AI-assisted access review evidence.
2. Check whether AI recommendations are logged.
3. Check whether human decisions are documented.
4. Confirm AI agent did not approve, grant, or remove access.
5. Flag missing human approval evidence if absent.

### Expected Result

The agent confirms that final access decisions require human approval and flags any missing human decision record.

### Status

Designed

## Traceability Matrix

| Audit Request | Test Cases |
|---|---|
| AR-001 Periodic User Access Review | TC-AUD-001, TC-AUD-002 |
| AR-002 Terminated User Deprovisioning | TC-AUD-003 |
| AR-003 Privileged Access Review | TC-AUD-004 |
| AR-005 SoD Review | TC-AUD-005 |
| AR-006 Access Exceptions | TC-AUD-006 |
| AR-007 Evidence Retention | TC-AUD-007 |
| AR-008 AI-Assisted Review | TC-AUD-008 |

## Portfolio Value

These test cases demonstrate audit evidence validation, QA test design, control traceability, defect identification, stakeholder questions, and human-in-the-loop AI governance testing.
