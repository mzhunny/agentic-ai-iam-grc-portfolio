# Test Cases: GRC Policy Mapping Agent

## Test Case Summary

These test cases validate that the simulated GRC Policy Mapping Agent can map policy statements to control themes, identify gaps, and preserve human review requirements.

| Test Case ID | Scenario | Expected Result | Priority |
|---|---|---|---|
| TC-GRC-001 | Map role-based access policy to access control theme | Correct control mapping created | High |
| TC-GRC-002 | Map access approval policy to user access management theme | Correct approval mapping created | High |
| TC-GRC-003 | Map JML policy to identity lifecycle theme | Correct lifecycle mapping created | High |
| TC-GRC-004 | Map terminated user deprovisioning policy | Correct deprovisioning mapping created | Critical |
| TC-GRC-005 | Identify missing deprovisioning SLA gap | Gap flagged as Critical | Critical |
| TC-GRC-006 | Identify missing review frequency gap | Gap flagged as High | High |
| TC-GRC-007 | Identify missing AI logging gap | Gap flagged as High | High |
| TC-GRC-008 | Verify AI does not approve policy interpretation automatically | Human review requirement preserved | Critical |

---

## TC-GRC-001: Map Role-Based Access Policy

**Policy Statement:** AC-01: Access Must Be Role-Based

### Preconditions

- Sample Access Control Policy exists.
- AC-01 states access must be based on role, department, business need, and least privilege.

### Test Steps

1. Load `sample-access-control-policy.md`.
2. Locate AC-01.
3. Map the policy statement to NIST-style and ISO-style access control themes.
4. Verify evidence expectations are identified.

### Expected Result

The agent maps AC-01 to access control / least privilege / identity and access control themes and identifies RBAC matrix and access provisioning records as evidence.

### Status

Designed

---

## TC-GRC-002: Map Access Approval Policy

**Policy Statement:** AC-02: Access Requests Must Be Approved

### Preconditions

- AC-02 requires manager or system owner approval before provisioning.

### Test Steps

1. Load AC-02.
2. Map it to access approval and user access management control themes.
3. Identify approval evidence needed.

### Expected Result

The agent maps AC-02 to access request approval control themes and identifies access tickets, manager approvals, and system owner approvals as evidence.

### Status

Designed

---

## TC-GRC-003: Map Joiner-Mover-Leaver Policy

**Policy Statement:** AC-03: Joiner-Mover-Leaver Events Must Be Reviewed

### Preconditions

- AC-03 requires access review during onboarding, job changes, transfers, and termination events.

### Test Steps

1. Load AC-03.
2. Map it to identity lifecycle management and account management themes.
3. Identify HR event and access change evidence.

### Expected Result

The agent maps AC-03 to JML and identity lifecycle management themes and identifies HR event logs, JML tickets, and access change records as evidence.

### Status

Designed

---

## TC-GRC-004: Map Terminated User Deprovisioning Policy

**Policy Statement:** AC-04: Terminated Users Must Be Deprovisioned

### Preconditions

- AC-04 requires terminated user access to be disabled or removed.

### Test Steps

1. Load AC-04.
2. Map it to account management and removal of access rights themes.
3. Identify termination and deprovisioning evidence.

### Expected Result

The agent maps AC-04 to terminated user deprovisioning controls and identifies termination reports, deprovisioning tickets, and access removal evidence.

### Status

Designed

---

## TC-GRC-005: Identify Missing Deprovisioning SLA Gap

**Gap Reference:** GAP-002

### Preconditions

- Sample policy requires deprovisioning but does not define a timeframe.

### Test Steps

1. Review AC-04.
2. Determine whether a deprovisioning SLA is defined.
3. Create a gap when no SLA exists.
4. Assign risk priority.

### Expected Result

The agent identifies a missing deprovisioning SLA and assigns Critical priority.

### Status

Designed

---

## TC-GRC-006: Identify Missing Access Review Frequency Gap

**Gap Reference:** GAP-001

### Preconditions

- AC-07 requires access reviews periodically but does not define frequency.

### Test Steps

1. Review AC-07.
2. Determine whether standard, privileged, and third-party review frequency is defined.
3. Create a gap if frequency is missing.
4. Assign risk priority.

### Expected Result

The agent identifies missing access review frequency and assigns High priority.

### Status

Designed

---

## TC-GRC-007: Identify Missing AI Agent Logging Gap

**Gap Reference:** GAP-007

### Preconditions

- AC-10 requires human approval for AI-assisted access review.
- AC-10 does not define AI input/output or recommendation logging.

### Test Steps

1. Review AC-10.
2. Determine whether AI recommendation and human decision logs are required.
3. Create a gap if logging requirements are missing.
4. Assign risk priority.

### Expected Result

The agent identifies missing AI agent logging requirements and assigns High priority.

### Status

Designed

---

## TC-GRC-008: Verify Human Review Requirement

**Policy Statement:** AC-10: AI-Assisted Access Review Must Require Human Approval

### Preconditions

- The agent produces policy mappings and gap recommendations.
- AI-assisted recommendations require human review.

### Test Steps

1. Generate policy mapping output.
2. Generate gap analysis output.
3. Check whether the output states that final decisions require human review.
4. Confirm the agent does not approve risk, approve policy, or modify access.

### Expected Result

The agent clearly states that final interpretation, risk acceptance, and access decisions require human approval.

### Status

Designed

## Traceability Matrix

| Requirement / Policy | Test Cases |
|---|---|
| AC-01 Role-Based Access | TC-GRC-001 |
| AC-02 Access Approval | TC-GRC-002 |
| AC-03 JML Review | TC-GRC-003 |
| AC-04 Terminated User Deprovisioning | TC-GRC-004, TC-GRC-005 |
| AC-07 Periodic Access Review | TC-GRC-006 |
| AC-10 AI Human Approval | TC-GRC-007, TC-GRC-008 |

## Portfolio Value

These test cases demonstrate:

- GRC control mapping validation.
- Policy review QA.
- Gap analysis validation.
- Control evidence thinking.
- AI output review.
- Human-in-the-loop governance testing.
