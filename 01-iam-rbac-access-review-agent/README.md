# IAM/RBAC Access Review Agent

## Project Summary

This project demonstrates a simulated Agentic AI workflow that reviews user access against an RBAC matrix and identifies access governance risks.

The goal is to show how an AI agent can support IAM teams during access reviews while still requiring human approval before any access changes are made.

## Business Problem

Organizations must regularly review user access to ensure users only have the permissions required for their job role. Excessive access, missing access, and outdated permissions can create security, compliance, and audit risks.

## Agent Use Case

The AI agent reviews fictional user access data, compares it against an approved RBAC matrix, and produces findings such as:

- Excessive access
- Missing required access
- Role mismatch
- Department mismatch
- Terminated user with active access
- Access requiring manager review
- Audit evidence gaps

## Skills Demonstrated

- IAM access review
- RBAC validation
- Joiner-Mover-Leaver lifecycle awareness
- QA test design
- Business rule validation
- Risk reporting
- Audit evidence thinking
- Human-in-the-loop AI governance

## Planned Deliverables

- business-requirements.md
- user-stories.md
- rbac-matrix.csv
- sample-user-access-data.csv
- agent-workflow.md
- test-cases.md
- risk-findings-report.md
- audit-evidence-checklist.md
