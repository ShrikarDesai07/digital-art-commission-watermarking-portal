# Requirements Traceability Matrix

This matrix uses only the requirements already defined in `requirements.md`.

| Requirement ID | Requirement Summary | Related Use Case / Flow | Verification / Acceptance Criteria |
|---|---|---|---|
| FR-001 | Apply a dynamic diagonal watermark to every WIP draft before client display. | Upload WIP Draft -> Apply Dynamic Watermark | Verify the client portal renders the uploaded draft with a watermark; an unwatermarked draft is a failure. |
| FR-002 | Allow the Client Buyer to review a watermarked WIP draft and provide feedback or approval. | Review WIP; Submit Feedback / Approval | Verify the client can review and submit feedback or approval and that the action is recorded. |
| FR-003 | Allow the Client Buyer to make the required milestone payment. | Make Milestone Payment -> Verify Payment | Verify a successful payment is recorded against the milestone; failed or pending payment is not completed. |
| FR-004 | Unlock the final high-resolution source file only after successful payment verification. | Verify Payment -> Unlock Final Asset | Compare access before and after verified payment; the final asset must be unavailable before verification. |
| FR-005 | Allow an authorized Client Buyer to download the final source file using a secure, time-limited link. | Download Final Asset -> Generate Signed URL | Verify an authorized client can download with a valid link; unauthorized or expired links cannot retrieve the asset. |
| NFR-001 | Generate expiring signed S3 URLs valid for 60 minutes only. | Generate Signed URL | Verify acceptable link-generation latency, access during the validity window, and rejection after 60 minutes. |
| NFR-002 | Restrict commission data and assets to authenticated, authorized users associated with the commission. | Authentication / Authorization across the commission flow | Verify authorized access succeeds while unauthenticated and authenticated-but-unauthorized access is rejected. |