# Business Requirements: IAM/RBAC Access Review Agent

## Project Purpose

The IAM/RBAC Access Review Agent is a simulated Agentic AI workflow that assists an IAM or GRC team by reviewing user access against an approved RBAC matrix and identifying access governance risks.

The project demonstrates how AI can support security review activities while keeping final access decisions under human control.

## Business Problem

Organizations must ensure users have access that matches their job responsibilities. When access is excessive, missing, outdated, or misaligned with a user's department or employment status, the organization may face security, operational, and audit risks.

Manual access reviews can be time-consuming and inconsistent. This project simulates how an AI agent can help analyze access data, identify exceptions, and prepare findings for human review.

## Business Objectives

- Validate user access against approved RBAC rules.
- Identify excessive access based on role and department.
- Identify missing required access for a user's role.
- Flag terminated users who still have active access.
- Flag users whose assigned access does not align with their department.
- Generate risk findings for IAM, GRC, and audit stakeholders.
- Maintain human approval before any access is changed.
- Produce audit-ready documentation showing review logic and outcomes.

## In Scope

- Fictional user access data.
- Fictional RBAC matrix.
- Simulated access review workflow.
- Exception identification and risk classification.
- QA test cases for access review logic.
- Audit evidence checklist.
- Human-in-the-loop approval design.

## Out of Scope

- Connection to real IAM systems.
- Automated access provisioning or deprovisioning.
- Use of real employee data.
- Production API integrations.
- Automatic remediation without human approval.

## Stakeholders

| Stakeholder | Responsibility |
|---|---|
| IAM Analyst | Reviews access exceptions and validates recommendations. |
| GRC Analyst | Reviews control alignment, audit evidence, and risk documentation. |
| Security QA Analyst | Validates agent logic, test cases, and expected results. |
| Business Manager | Approves or rejects access changes for employees. |
| Auditor | Reviews evidence showing the access review was performed. |

## Functional Requirements

| ID | Requirement |
|---|---|
| BR-001 | The agent shall compare user access against an approved RBAC matrix. |
| BR-002 | The agent shall identify access assigned to a user that is not allowed for the user's role. |
| BR-003 | The agent shall identify required access that is missing for the user's role. |
| BR-004 | The agent shall identify users with active access when employment status is terminated. |
| BR-005 | The agent shall flag users whose department does not match the department expected for their role. |
| BR-006 | The agent shall assign a risk rating to each finding. |
| BR-007 | The agent shall generate a summary of findings for human review. |
| BR-008 | The agent shall not remove, grant, or modify access automatically. |

## Non-Functional Requirements

| ID | Requirement |
|---|---|
| NFR-001 | The workflow shall use only fictional sample data. |
| NFR-002 | The workflow shall include traceable test cases. |
| NFR-003 | The workflow shall document assumptions and limitations. |
| NFR-004 | The workflow shall include human approval before remediation. |
| NFR-005 | The workflow shall be clear enough for a recruiter, auditor, or hiring manager to understand. |

## Key Assumptions

- The RBAC matrix is the source of truth for approved role-based access.
- Employment status is available in the user access data.
- Department and role data are accurate enough to support review logic.
- All findings require human review before remediation.

## Success Criteria

- The project clearly demonstrates IAM/RBAC review logic.
- The sample data includes normal and exception scenarios.
- Test cases validate positive, negative, and edge cases.
- Risk findings are easy to understand.
- Documentation shows QA, BA, IAM, GRC, and audit-readiness skills.
