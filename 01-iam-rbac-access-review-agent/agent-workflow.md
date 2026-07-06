# Agent Workflow: IAM/RBAC Access Review Agent

## Workflow Summary

This workflow simulates how an Agentic AI assistant can support an IAM/RBAC access review. The agent reviews fictional user access data, compares access against an approved RBAC matrix, identifies exceptions, and prepares findings for human review.

The agent does not grant, remove, or modify access. All remediation recommendations require human approval.

## Inputs

| Input | Description |
|---|---|
| `rbac-matrix.csv` | Approved role-based access rules by role and department. |
| `sample-user-access-data.csv` | Fictional user access data for the review period. |
| Business requirements | Review rules and expected behavior. |
| User stories | Role-based acceptance criteria. |

## Outputs

| Output | Description |
|---|---|
| Risk findings report | Summary of access review exceptions. |
| Audit evidence checklist | Evidence needed to support audit readiness. |
| Test case results | QA validation of expected access review behavior. |

## Agent Review Logic

### Step 1: Load Review Data

The agent loads the RBAC matrix and sample user access data.

Validation checks:

- Required fields are present.
- User records include role, department, employment status, current access, manager, and review period.
- RBAC matrix includes required, optional, restricted, and sensitivity fields.

### Step 2: Match User Role to RBAC Matrix

For each user, the agent matches the user's role to the RBAC matrix.

If the role is found, the agent compares access permissions.

If the role is not found, the agent creates a finding for undefined role mapping.

### Step 3: Validate Department Alignment

The agent compares the user's department to the department associated with the assigned role.

Possible outcomes:

- Department aligned.
- Department mismatch requiring manager confirmation.

### Step 4: Check Employment Status

The agent checks whether the user is active or terminated.

Rules:

- Active users may retain approved access.
- Terminated users should not have active access.
- Terminated users with active access are high-risk exceptions.

### Step 5: Identify Excessive Access

The agent compares the user's current access to approved required and optional access.

If a user has access outside the approved required or optional list, the agent flags excessive access.

### Step 6: Identify Missing Required Access

The agent compares required access to current access.

If a required permission is missing, the agent flags missing access as an operational risk.

### Step 7: Check Restricted Access

The agent checks whether the user has any access listed as restricted for their role.

Restricted access findings receive elevated risk ratings.

### Step 8: Assign Risk Rating

Risk rating rules:

| Condition | Suggested Risk |
|---|---|
| Terminated user with active access | Critical |
| Restricted access assigned | High or Critical |
| Excessive access with financial/admin permission | High |
| Department-role mismatch | Medium |
| Missing required access | Medium |
| Fully aligned access | No finding |

### Step 9: Generate Human Review Recommendations

The agent recommends one of the following actions:

- Approve access as aligned.
- Remove excessive access after manager/IAM approval.
- Grant missing access after manager approval.
- Investigate department-role mismatch.
- Immediately review terminated user access.

### Step 10: Preserve Human-in-the-Loop Control

The agent must not perform remediation automatically.

Required human approval points:

- Manager approval for access changes.
- IAM approval for role or permission changes.
- GRC review for audit-impacting exceptions.
- Security escalation for terminated users with active access.

## Example Agent Prompt

```text
You are an IAM/RBAC Access Review Agent. Review the fictional user access data against the approved RBAC matrix. Identify excessive access, missing required access, terminated users with active access, department-role mismatches, and restricted access. Assign risk ratings, explain the rationale, and recommend human review actions. Do not recommend automatic access changes without human approval.
```

## Guardrails

- Use only fictional data.
- Do not process real employee records.
- Do not connect to production IAM tools.
- Do not make automatic access changes.
- Show assumptions clearly.
- Require human approval for all remediation.

## Portfolio Value

This workflow demonstrates:

- IAM/RBAC analysis.
- Business rule validation.
- QA testing logic.
- GRC risk documentation.
- Audit readiness.
- Agentic AI governance.
