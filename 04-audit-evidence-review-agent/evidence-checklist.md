# Evidence Checklist: Audit Evidence Review Agent

## Checklist Purpose

This checklist helps evaluate whether audit evidence is complete, accurate, traceable, and ready for human review before submission to auditors.

This artifact uses fictional audit scenarios and is intended for portfolio demonstration only.

## Evidence Readiness Criteria

| Criteria | Description |
|---|---|
| Complete | Evidence includes all required artifacts for the audit request. |
| Accurate | Evidence matches the control objective and review period. |
| Traceable | Evidence can be tied to users, systems, approvals, dates, and actions. |
| Approved | Evidence includes appropriate manager, IAM, GRC, or control owner approval. |
| Timely | Evidence shows control activity occurred within the required timeframe. |
| Protected | Evidence does not expose unnecessary sensitive data. |
| Retained | Evidence is stored according to retention expectations. |

## Master Evidence Checklist

| Evidence ID | Evidence Item | Supports Requests | Evidence Owner | Readiness Status | Review Notes |
|---|---|---|---|---|---|
| E-001 | Access review campaign scope | AR-001 | IAM | Needed | Must show systems, users, and review period. |
| E-002 | User access extract | AR-001, AR-004, AR-005 | IAM | Needed | Must match the audit period. |
| E-003 | Approved RBAC matrix | AR-001, AR-004 | IAM / GRC | Needed | Must show role-to-access mapping. |
| E-004 | Reviewer sign-off | AR-001 | IAM Manager | Needed | Must show reviewer identity and date. |
| E-005 | Access exception report | AR-001, AR-006 | IAM / GRC | Needed | Must include status and remediation actions. |
| E-006 | Termination report | AR-002 | HR | Needed | Must show termination date. |
| E-007 | Deprovisioning ticket | AR-002 | IAM | Needed | Must show access removed or disabled. |
| E-008 | Privileged access list | AR-003 | IAM / Security | Needed | Must identify privileged users and permissions. |
| E-009 | Privileged access approval | AR-003 | System Owner | Needed | Must show business justification. |
| E-010 | SoD rules matrix | AR-005 | GRC / IAM | Needed | Must identify conflicting permission pairs. |
| E-011 | SoD conflict report | AR-005 | IAM / GRC | Needed | Must show conflicts, risk ratings, and decisions. |
| E-012 | Remediation tickets | AR-001, AR-002, AR-005 | IAM | Needed | Must show action owner, date, and closure status. |
| E-013 | Exception register | AR-006 | GRC | Needed | Must include justification, approval, expiration, and risk owner. |
| E-014 | Evidence retention policy | AR-007 | Compliance / GRC | Needed | Must define retention requirements. |
| E-015 | Evidence repository record | AR-007 | GRC | Needed | Must show evidence storage location and owner. |
| E-016 | AI agent workflow documentation | AR-008 | Security / AI Governance | Needed | Must define agent role and limitations. |
| E-017 | AI recommendation logs | AR-008 | Security / IAM | Needed | Must show recommendations and timestamps. |
| E-018 | Human approval records | AR-008 | IAM / Control Owner | Needed | Must show final decisions were human-approved. |
| E-019 | Agent permission review | AR-008 | Security / GRC | Needed | Must show the agent cannot make unauthorized changes. |
| E-020 | Final control owner sign-off | All | Control Owner | Needed | Must approve final audit package. |

## Evidence Review Questions

Use the following questions before submitting evidence:

- Does the evidence directly answer the audit request?
- Does the evidence match the review period?
- Is the evidence tied to the correct control objective?
- Does the evidence show who performed or approved the control activity?
- Does the evidence show the date and outcome?
- Are exceptions clearly documented?
- Are remediation actions tracked to closure?
- Are screenshots or exports readable and complete?
- Is sensitive data masked where appropriate?
- Is final control owner approval documented?

## Common Evidence Defects

| Defect | Example | Risk |
|---|---|---|
| Missing review period | Evidence does not show Q3-2026 or audit dates. | Auditor cannot confirm scope. |
| Missing approver | Access request shows provisioned access but no approval. | Control may fail. |
| Missing remediation status | Exception identified but no closure evidence. | Risk may remain unresolved. |
| Incomplete user population | Access review excludes privileged users. | Review may be unreliable. |
| Unclear screenshots | Screenshot lacks timestamp, user, or system context. | Evidence may be rejected. |
| No human approval | AI recommendation exists but no human decision record. | AI governance control gap. |

## Portfolio Value

This checklist demonstrates evidence analysis, audit readiness, control validation, documentation quality review, and AI-assisted workflow governance.
