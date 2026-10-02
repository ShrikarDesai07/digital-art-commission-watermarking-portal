# Requirements Engineering - Problem Statement #58

## Project
**Digital Art Commission & Watermarking Portal**

## Functional Requirements

| ID | Type | Description | Priority | Acceptance Criteria | Rationale |
|---|---|---|---|---|---|
| FR-001 | Functional | The system shall apply a dynamic diagonal overlay watermark to all draft illustrations uploaded by artists before displaying them to the client. | High | Pass: Watermarked draft is rendered in the client portal. Fail: An unwatermarked draft is exposed. | Protects WIP artwork before final payment. |
| FR-002 | Functional | The system shall allow the Client Buyer to view a watermarked WIP draft and provide feedback or approval. | High | Pass: Client can review and submit feedback/approval. Fail: Review action is unavailable or not recorded. | Supports the iterative commission workflow. |
| FR-003 | Functional | The system shall allow the Client Buyer to make the required milestone payment through the payment service. | High | Pass: Successful payment is recorded against the milestone. Fail: Failed/pending payment is not treated as completed. | Payment is required before final asset release. |
| FR-004 | Functional | The system shall unlock the final high-resolution source file only after successful verification of the required milestone payment. | High | Pass: Final asset becomes available after verified payment. Fail: Asset is exposed before verified payment. | Prevents premature release of the paid deliverable. |
| FR-005 | Functional | The system shall allow an authorized Client Buyer to download the final high-resolution source file using a secure, time-limited download link. | High | Pass: Authorized client can download using a valid link. Fail: Unauthorized or expired links cannot retrieve the asset. | Protects the final source file during delivery. |

## Non-Functional Requirements

| ID | Type | Description | Priority | Acceptance Criteria | Rationale |
|---|---|---|---|---|---|
| NFR-001 | Performance & Security | Final high-resolution asset downloads must generate expiring signed S3 URLs valid for 60 minutes only. | High | Tests confirm acceptable download-link generation latency and that links become invalid after 60 minutes. | Limits the exposure period of high-value source files. |
| NFR-002 | Security | Access to commission data and assets shall be restricted to authenticated and authorized users associated with the relevant commission. | High | Unauthorized users cannot access private commission data or final assets. | Protects artwork, client information, and commission data. |

## Requirements Traceability Matrix (RTM)

| Requirement ID | Requirement Summary | Related Use Case / Flow | Primary Component(s) | Verification / Evidence |
|---|---|---|---|---|
| FR-001 | Watermark every WIP before client display | Upload WIP Draft -> Apply Dynamic Watermark | Watermark Service, Asset Storage | Inspect uploaded WIP in client portal and verify watermark is present. |
| FR-002 | Client reviews WIP and gives feedback/approval | Review WIP; Submit Feedback / Approval | Client & Artist Portal, Order Manager | Submit feedback/approval and verify it is stored against the commission. |
| FR-003 | Process milestone payment | Make Milestone Payment -> Verify Payment | Payment Service, Order Manager | Complete a successful payment and confirm milestone status changes to paid. |
| FR-004 | Unlock final asset only after payment verification | Verify Payment -> Unlock Final Asset | Order Manager, Asset Storage & Secure Delivery | Attempt access before and after verified payment and compare results. |
| FR-005 | Secure final asset download | Download Final Asset -> Generate Signed URL | Asset Storage & Secure Delivery, Portal | Verify authorized client receives a working time-limited download link. |
| NFR-001 | Signed URL expires after 60 minutes | Generate Signed URL | Asset Storage & Secure Delivery | Validate URL works within validity window and is rejected after expiry. |
| NFR-002 | Restrict private assets to authorized users | Authentication / authorization across commission flow | Portal, Order Manager, Asset Storage | Test authenticated authorized, authenticated unauthorized, and unauthenticated requests. |
