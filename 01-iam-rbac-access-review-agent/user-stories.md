# User Stories: IAM/RBAC Access Review Agent

## Epic

As an IAM/GRC team, we need an AI-assisted access review workflow so that user permissions can be evaluated against RBAC rules, exceptions can be identified, and access risks can be reviewed before remediation.

---

## US-001: Compare User Access to RBAC Matrix

**As an** IAM Analyst,  
**I want** the agent to compare each user's access against the approved RBAC matrix,  
**so that** I can identify whether access aligns with the user's role.

### Acceptance Criteria

- Given a user has access listed in the sample user access data, when the agent reviews the user's role, then the agent compares the access to the approved RBAC matrix.
- Given the user's access matches the approved RBAC matrix, when the review is completed, then the agent marks the access as aligned.
- Given the user's access does not match the approved RBAC matrix, when the review is completed, then the agent creates an exception finding.

---

## US-002: Flag Excessive Access

**As an** IAM Analyst,  
**I want** the agent to identify access that is not approved for a user's role,  
**so that** excessive access can be reviewed and removed if appropriate.

### Acceptance Criteria

- Given a user has a permission not listed for their role in the RBAC matrix, when the agent reviews the record, then the agent flags the permission as excessive access.
- Given excessive access is identified, when the finding is created, then the agent assigns a risk rating based on access sensitivity.
- Given excessive access is identified, when the review is complete, then the agent routes the finding for human review.

---

## US-003: Flag Missing Required Access

**As a** Business Manager,  
**I want** the agent to identify missing required access,  
**so that** users can perform their job duties without unnecessary delays.

### Acceptance Criteria

- Given a user's role requires a permission, when that permission is missing from the user's access, then the agent flags it as missing required access.
- Given missing required access is identified, when the finding is created, then the agent marks it as an operational risk.
- Given missing access is identified, when remediation is needed, then manager approval is required before access is granted.

---

## US-004: Flag Terminated Users with Active Access

**As a** GRC Analyst,  
**I want** the agent to identify terminated users with active access,  
**so that** offboarding control failures can be reviewed quickly.

### Acceptance Criteria

- Given a user's employment status is Terminated, when the user still has active access, then the agent creates a high-risk finding.
- Given a terminated user has no active access, when the review is performed, then the agent marks the record as compliant.
- Given a terminated user has active access, when the finding is created, then the agent recommends immediate human review.

---

## US-005: Flag Department and Role Mismatch

**As a** Security QA Analyst,  
**I want** the agent to validate department and role alignment,  
**so that** role-based access can be tested using business rules.

### Acceptance Criteria

- Given a user has a role assigned to a different department, when the agent reviews the data, then the agent flags the record as a department-role mismatch.
- Given a department-role mismatch exists, when the finding is created, then the agent recommends manager confirmation.
- Given department and role are aligned, when the review is completed, then no mismatch finding is created.

---

## US-006: Produce Risk Findings Report

**As an** Auditor,  
**I want** a summary of access review exceptions,  
**so that** I can understand what was reviewed, what was flagged, and what actions were recommended.

### Acceptance Criteria

- Given the agent completes the review, when findings exist, then the report includes finding type, affected user, risk rating, rationale, and recommended action.
- Given no findings exist for a user, when the report is generated, then the user may be listed as aligned or excluded from exceptions.
- Given a finding requires remediation, when the report is reviewed, then it must show that human approval is required before action.
