# Control Owner Questions: Audit Evidence Review Agent

## Document Purpose

This document provides targeted questions an Audit Evidence Review Agent can generate for control owners when audit evidence is incomplete, unclear, or missing required context.

These questions are designed to help IAM, GRC, Security QA, HR, Finance, Audit, and AI Governance teams prepare audit-ready responses.

## How to Use This Document

Use these questions when reviewing audit evidence for completeness, accuracy, control alignment, and human approval.

The AI agent may suggest these questions, but human stakeholders must provide the final answers and approve audit responses.

---

## Access Review Questions

### For IAM Control Owner

- What systems and applications were included in the access review?
- What user population was included?
- Were privileged users included?
- Were contractors, vendors, or service accounts included?
- Who performed the review?
- Who approved the final review results?
- What exceptions were identified?
- Were exceptions remediated or formally accepted?
- Where is the final review sign-off stored?

### For Business Managers

- Did you review access for all users assigned to you?
- Did you approve access that remains required for job duties?
- Did you reject or flag access that was no longer needed?
- Were any users transferred or terminated during the period?
- Did you approve any exceptions?

---

## Terminated User Access Questions

### For HR Control Owner

- What is the source of truth for termination dates?
- When was the termination event sent to IAM?
- Were any terminations retroactive?
- Were any termination records corrected after initial submission?

### For IAM Control Owner

- What is the required deprovisioning SLA?
- When was each terminated user's access disabled?
- Were all applications included in the deprovisioning workflow?
- Were privileged accounts checked separately?
- Were any deprovisioning actions delayed?
- If delayed, was an exception documented?

---

## Privileged Access Questions

### For Security / IAM Control Owner

- How is privileged access defined?
- Who owns privileged access approval?
- How often is privileged access reviewed?
- Are privileged actions logged?
- Are privileged sessions monitored?
- Are break-glass accounts included in the review?
- Are service accounts included?
- Were any privileged accounts removed during the period?

---

## RBAC Questions

### For IAM / GRC Control Owner

- Who owns the RBAC matrix?
- When was the RBAC matrix last reviewed?
- Are roles mapped to departments and job functions?
- How are role changes approved?
- How are department-role mismatches handled?
- Are high-risk permissions clearly identified?
- Are restricted permissions documented?

---

## Segregation of Duties Questions

### For GRC / Finance / IAM Control Owners

- Who owns the SoD rules matrix?
- How often are SoD rules reviewed?
- What systems are included in SoD monitoring?
- Which conflicts are considered critical?
- How are SoD conflicts remediated?
- Who can approve a SoD exception?
- Are compensating controls required for accepted conflicts?
- Are exception expiration dates tracked?

---

## Access Exception Questions

### For GRC Control Owner

- What qualifies as an access exception?
- Who approves exceptions?
- Are exceptions time-bound?
- Are exception expiration dates tracked?
- Are expired exceptions removed or recertified?
- Are high-risk exceptions reviewed by GRC?
- Is risk acceptance documented?
- Are compensating controls required?

---

## Evidence Retention Questions

### For Compliance / GRC Control Owner

- What is the evidence retention period?
- Where is evidence stored?
- Who owns the evidence repository?
- Who can modify evidence?
- Are access controls applied to the evidence repository?
- Are audit artifacts protected from unauthorized changes?
- Is evidence disposal documented after the retention period ends?

---

## AI-Assisted Review Questions

### For AI Governance / Security Control Owner

- What actions can the AI agent perform?
- What actions is the AI agent prohibited from performing?
- Can the AI agent grant, remove, or approve access?
- Are AI recommendations logged?
- Are human decisions recorded separately from AI recommendations?
- Who approves final access decisions?
- How are incorrect AI recommendations corrected?
- Is the AI agent's tool access reviewed periodically?
- Are prompt injection or data leakage risks considered?
- Are AI outputs validated by a human before submission to audit?

## Escalation Questions

Use these questions when evidence indicates a high-risk control issue:

- Does this issue require immediate IAM or Security review?
- Does this issue impact audit readiness?
- Does this issue require control owner sign-off?
- Does this issue require risk acceptance?
- Does this issue require legal, compliance, or privacy review?
- Has a remediation owner been assigned?
- Has a due date been documented?

## Portfolio Value

This document demonstrates stakeholder communication, audit evidence clarification, IAM/GRC control ownership awareness, and AI-assisted audit support with human oversight.
