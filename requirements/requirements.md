# Requirements Table

## Functional Requirements

| ID | Description | Priority | Acceptance Criteria | Rationale |
|---|---|---|---|---|
| FR-001 | The system shall allow a Digital Artist to upload a WIP illustration and shall apply a dynamic diagonal overlay watermark before the draft is displayed to the Client Buyer. | High | **Pass:** Client sees only the watermarked WIP. **Fail:** Any unwatermarked WIP is displayed. | Protects artists' work during the review stage. |
| FR-002 | The system shall allow the Client Buyer to view a watermarked WIP and submit review feedback or approval for the current milestone. | High | **Pass:** Feedback/approval is stored against the milestone and visible to the artist. | Supports iterative commission review. |
| FR-003 | The system shall allow the Client Buyer to initiate and complete a milestone payment through the Payment Service. | High | **Pass:** A successful payment creates a recorded payment event for the milestone. **Fail:** An unsuccessful payment is not treated as paid. | Payment gates the release of the final asset. |
| FR-004 | The system shall unlock the final high-resolution asset only after the required milestone payment is successfully verified. | High | **Pass:** Eligible client receives a download option after verified payment. **Fail:** High-resolution asset remains inaccessible before payment. | Prevents premature exposure of paid deliverables. |
| FR-005 | The system shall allow the Digital Artist to upload the final high-resolution source file and allow an eligible Client Buyer to download it through a time-limited secure link. | High | **Pass:** Download works for an eligible client using a valid link. **Fail:** Unauthorized or expired links cannot retrieve the asset. | Completes the commission handoff while protecting the source file. |

## Non-Functional Requirements

| ID | Type | Description | Priority | Acceptance Criteria | Rationale |
|---|---|---|---|---|---|
| NFR-001 | Performance & Security | Final high-resolution asset downloads must generate expiring signed S3 URLs valid for 60 minutes only. | High | Benchmark/security tests confirm the target latency and that links become invalid after 60 minutes. | Limits the exposure window for high-value source files. |
| NFR-002 | Security | Access to commission data and assets shall be authorized by authenticated role and commission ownership; final assets shall not be directly publicly accessible. | High | Tests confirm a client can access only authorized commissions and that unauthenticated/public requests cannot retrieve private final assets. | Protects client, artist, payment, and intellectual-property data. |
