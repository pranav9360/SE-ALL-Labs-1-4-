# Lab 1 — Requirements Specification

**Project:** Patient Health Record Consent Management System

This document captures the requirements and acceptance criteria from the supplied requirements table.

| Requirement ID | Type | Description | Priority | Acceptance criteria | Rationale |
|---|---|---|---|---|---|
| FR-001 | Functional | The system shall allow patients to grant time-bounded access permissions for specific medical records to verified clinic doctors. | High | **Pass:** Access automatically expires at the specified time. **Fail:** The doctor can access records after expiry. | Gives patients control over who can access their health records. |
| FR-002 | Functional | The system shall allow patients to revoke previously granted consent before its expiry time. | High | **Pass:** Access is denied immediately after revocation. **Fail:** The authorized party can still access the record after revocation. | Patients must be able to withdraw consent at any time. |
| FR-003 | Functional | The system shall allow patients to select specific medical records when granting access permissions. | High | **Pass:** Only selected records are accessible to the authorized party. **Fail:** Unselected records are accessible. | Ensures granular control over sensitive health information. |
| FR-004 | Functional | The system shall allow verified clinic administrators to request access to a patient's medical records. | Medium | **Pass:** A valid access request is sent to the patient for authorization. **Fail:** An invalid or unverified requester obtains access directly. | Supports a controlled process for requesting patient data. |
| FR-005 | Functional | The system shall allow patients to view the history of consent grants, revocations, and record access events. | Medium | **Pass:** The patient can view event type, requester, and timestamp. **Fail:** Consent or access events are missing from the history. | Provides transparency and accountability. |
| NFR-001 | Nonfunctional — Security | The system shall permanently record all consent grant, revoke, and access events in an append-only audit trail. | High | **Pass:** Audit records cannot be modified or deleted through normal system operations. **Fail:** An existing audit event can be altered or removed. | Ensures accountability and supports security auditing. |
| NFR-002 | Nonfunctional — Performance | The system shall process consent grant or revocation requests within 3 seconds under normal operating conditions. | Medium | **Pass:** At least 95% of tested requests complete within 3 seconds. **Fail:** More than 5% exceed 3 seconds. | Ensures a responsive experience for patients and healthcare providers. |

> This Markdown file is a searchable transcription of the supplied requirements table. Upload the original Word document(s) in this folder as well if the professor expects the original format.
