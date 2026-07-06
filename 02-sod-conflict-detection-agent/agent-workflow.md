# Agent Workflow: SoD Conflict Detection Agent

## Workflow Summary

This workflow simulates how an Agentic AI assistant can support Segregation of Duties conflict detection. The agent compares user permissions against a defined SoD rules matrix, identifies risky permission combinations, assigns risk ratings, and recommends human-reviewed remediation.

The agent does not remove, grant, or modify access. It only identifies possible conflicts and prepares findings for IAM, GRC, Security QA, and business owner review.

## Inputs

| Input | Description |
|---|---|
| `sod-rules-matrix.csv` | Approved Segregation of Duties rules and risk ratings. |
| `sample-access-conflicts.csv` | Fictional user permission dataset. |
| Business process context | Explains why permission combinations create risk. |
| Human review requirements | Defines approval and remediation checkpoints. |

## Outputs

| Output | Description |
|---|---|
| Conflict findings | Users with permission combinations that violate SoD rules. |
| Risk rating | Severity level based on conflict type and business impact. |
| Remediation recommendation | Suggested corrective action requiring human approval. |
| QA test results | Validation that the agent detected expected conflicts. |

## Agent Review Logic

### Step 1: Load SoD Rules

The agent loads each SoD rule with:

- Rule ID
- Business process
- Permission A
- Permission B
- Conflict description
- Risk rating
- Control objective
- Recommended mitigation

### Step 2: Load User Permissions

The agent loads fictional user permission data and verifies that each user record includes:

- User ID
- User name
- Department
- Role
- Employment status
- Current permissions
- Manager
- Review period

### Step 3: Compare User Permissions to SoD Rules

For each user, the agent checks whether the user has both permissions in a conflict pair.

Example:

```text
If user has VENDOR_CREATE and PAYMENT_APPROVE, then flag SOD-001.
```

### Step 4: Classify Conflict

When a conflict is detected, the agent records:

- User ID
- User name
- Department
- Role
- Conflicting permissions
- Matching SoD rule ID
- Conflict description
- Risk rating
- Recommended mitigation

### Step 5: Assign Review Priority

Priority rules:

| Risk Rating | Review Priority |
|---|---|
| Critical | Immediate IAM/GRC review |
| High | Priority review with manager validation |
| Medium | Standard access review queue |
| Low | Monitor or document exception |

### Step 6: Recommend Remediation

The agent recommends one or more remediation options:

- Remove one conflicting permission.
- Transfer one duty to another role.
- Require independent approval.
- Document a compensating control.
- Create or update a remediation ticket.
- Escalate critical conflicts to IAM/GRC leadership.

### Step 7: Preserve Human Approval

The agent cannot automatically remove access or approve exceptions.

Required human approval points:

- Business manager validates job need.
- IAM confirms role and permission design.
- GRC reviews risk and control impact.
- Control owner approves accepted exceptions.
- Auditor reviews evidence if required.

## Example Agent Prompt

```text
You are a Segregation of Duties Conflict Detection Agent. Review the fictional user permission data against the SoD rules matrix. Identify users who have conflicting permissions, assign the mapped risk rating, explain why the conflict matters, and recommend human-reviewed remediation. Do not recommend automatic access changes without manager, IAM, and GRC approval.
```

## Guardrails

- Use fictional data only.
- Do not connect to production IAM, ERP, HR, payroll, or finance systems.
- Do not automatically change access.
- Do not approve exceptions.
- Show assumptions and limitations clearly.
- Route high and critical conflicts for human review.

## Portfolio Value

This workflow demonstrates:

- IAM conflict analysis.
- Segregation of Duties review.
- GRC control awareness.
- Risk-based access review.
- Security QA test design.
- Agentic AI governance.
- Audit-ready documentation.
