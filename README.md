# Digital Art Commission & Watermarking Portal

## Software Engineering Lab

| Student Name | Shrikar Desai |
|---|---|
| SRN | PES1UG24CS916 |
| Section | 5H |
| Project Name | Digital Art Commission & Watermarking Portal |
| Problem Statement | #58 |
| Domain | Media, Events & Community |

---

## Problem Statement

**Digital Art Commission & Watermarking Portal**

An art commission platform where clients submit visual creative briefs, artists submit watermarked WIP progress drafts, and final high-resolution source files unlock upon milestone payment.

The system supports a commission workflow in which:

1. The Client Buyer submits a creative brief.
2. The Digital Artist works on the commissioned artwork.
3. The Digital Artist submits watermarked WIP drafts.
4. The Client Buyer reviews the WIP and provides feedback or approval.
5. The Client Buyer completes the required milestone payment.
6. The final high-resolution source file is released after payment verification.
7. The Client Buyer downloads the final asset through a secure, time-limited link.

---

## Repository Deliverables

| Path | Deliverable |
|---|---|
| `requirements/requirements.md` | Exactly 5 Functional Requirements + 2 Non-Functional Requirements |
| `requirements/requirements.pdf` | Requirements document |
| `uml/use-case-diagram.png` | UML Use-Case Diagram |
| `uml/use-case-diagram.pdf` | Printable Use-Case Diagram |
| `docs/use-case-flow-specification.docx` | One-page core use-case flow |
| `docs/use-case-flow-specification.pdf` | PDF version of the flow specification |
| `architecture/component-diagram.png` | UML Component Diagram |
| `architecture/component-diagram.pdf` | Printable Component Diagram |
| `docs/architecture-justification.docx` | Architecture justification |
| `docs/architecture-justification.pdf` | PDF version of architecture justification |
| `docs/problem-statement.md` | Problem statement |
| `docs/submission-notes.md` | Submission notes |
| `README.md` | Repository documentation |

---

## Architecture

**Selected Architectural Style: Microservices Architecture**

### Main Components

The Lab 3 handout provides the following components:

- Order Manager Component
- Payment Service Component

Additional components identified for the system:

- Client & Artist Portal
- Watermark Service
- Asset Storage & Secure Delivery

The component architecture demonstrates the interaction between these components through service interfaces and data/control flows.

---

## UML Use-Case Model

The use-case diagram models the following actors:

- **Client Buyer**
- **Digital Artist**

The diagram includes:

- Primary system use cases
- `<<include>>` relationships for mandatory sub-functions
- `<<extend>>` relationship for optional review feedback

---

## Requirements

The requirements specification contains:

### Functional Requirements

- FR-001
- FR-002
- FR-003
- FR-004
- FR-005

### Non-Functional Requirements

- NFR-001
- NFR-002

Each requirement contains:

- ID
- Type
- Description
- Priority
- Acceptance Criteria
- Rationale

---

## Security

The system protects artwork throughout the commission lifecycle.

Key security considerations include:

- Dynamic watermarking of WIP artwork
- Authentication and authorization
- Protection of final high-resolution assets
- Payment verification before final asset release
- Time-limited signed S3 URLs for final asset downloads

---

## Performance

The selected microservices architecture allows resource-intensive operations such as watermarking and asset delivery to be scaled independently from order management and payment processing.

This supports concurrent commission activity while avoiding the need to scale the complete system whenever a single service experiences higher workload.

---

## Component Diagram Requirements

The component diagram satisfies the Lab 3 requirements by including:

- At least 5 components
- At least 4 interfaces
- Component dependencies
- Provided/required service interfaces
- Data/control flow between components

---

## Use-Case Flow

The core use case documented in this repository is:

**Release Final High-Resolution Asset**

The specification contains:

- Preconditions
- Postconditions
- Main Success Scenario
- Alternate Flow
- Requirement traceability

---

## Repository Structure

```text
digital-art-commission-watermarking-portal/
│
├── README.md
├── .gitignore
│
├── requirements/
│   ├── requirements.md
│   └── requirements.pdf
│
├── uml/
│   ├── use-case-diagram.png
│   ├── use-case-diagram.pdf
│   └── use-case.dot
│
├── architecture/
│   ├── component-diagram.png
│   ├── component-diagram.pdf
│   └── component.dot
│
└── docs/
    ├── problem-statement.md
    ├── submission-notes.md
    ├── use-case-flow-specification.docx
    ├── use-case-flow-specification.pdf
    ├── architecture-justification.docx
    └── architecture-justification.pdf
