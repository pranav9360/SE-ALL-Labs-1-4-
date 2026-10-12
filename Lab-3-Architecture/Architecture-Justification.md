# Lab 3 — Architecture Selection Justification

**Project:** Patient Health Record Consent Management System  
**Name:** D Pranav Sai  
**SRN:** PES1UG24CS139  
**Section:** C  
**Lab:** 03

## Scenario

Patient Health Record Consent Management System

## Selected Architecture

Layered Architecture is selected for the Patient Health Record Consent Management System. The system is divided into Presentation, Business/Service, and Data/Integration layers. This separation allows user interfaces, consent rules, access validation, auditing, and data storage to be developed, tested, and maintained independently.

## Scenario-Specific Reason 1 — Security and Consent Enforcement

The system handles sensitive medical records and must ensure that access is granted only when valid consent exists. Centralizing consent grant, revocation, expiry validation, requester verification, and record-level access in the Business/Service layer prevents different user interfaces from implementing inconsistent security rules. Every request can pass through Access Control before medical records are returned.

## Scenario-Specific Reason 2 — Maintainability and Modularity

The requirements include separate activities for granting and revoking consent, selecting medical records, selecting medical administrators, requesting access, and viewing consent history. Layered Architecture keeps these responsibilities modular. Changes to the patient or clinic portals can be made without changing the database implementation, while database changes can be isolated from the presentation layer.

## Security Advantage

The architecture supports centralized identity verification and access control. The system can check the requester's identity, validate whether consent is active or revoked, verify expiry conditions, and record grant, revoke, and access events through the Audit Service. Separating the Medical Record Store, Consent Database, and Identity & Verification components also reduces the risk of unauthorized direct access to sensitive data.

## Performance Benefit

Frequently used operations such as consent validation, requester verification, and consent-data queries are handled by dedicated service components. The Consent Database can use indexed lookups for patient, requester, consent status, and expiry information. This reduces duplicated processing and supports the requirement that normal consent grant or revocation requests should complete within three seconds.

## Component Interaction

The Patient Portal communicates with Consent Management for granting, revoking, and viewing consent history. The Clinic Portal communicates with Access Control for requesting and accessing medical records, while the Admin Console supports requester verification. Consent Management queries the Medical Record Store, Access Control queries the Consent Database and Identity & Verification services, and Audit Service records relevant system events.

## Diagram files

The use-case and component diagram image files were supplied separately in the conversation but have not yet been uploaded into this repository. Add them under a `diagrams/` subfolder before submission. The original justification PDF should also be uploaded here if the original PDF format is required.
