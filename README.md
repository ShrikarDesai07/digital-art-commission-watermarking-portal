# Digital Art Commission & Watermarking Portal

Software Engineering lab repository for **Problem Statement #58 — Digital Art Commission & Watermarking Portal**.

The system supports a commission workflow in which a Client Buyer submits a creative brief, a Digital Artist submits watermarked WIP drafts, milestone payment is processed, and the final high-resolution source file is released only after payment verification.

## Repository Deliverables

| Path | Deliverable |
|---|---|
| `requirements/requirements.md` | Exactly 5 Functional Requirements + 2 Non-Functional Requirements |
| `uml/use-case-diagram.png` | UML Use-Case Diagram |
| `uml/use-case-diagram.pdf` | Printable Use-Case Diagram |
| `docs/use-case-flow-specification.docx` | One-page core use-case flow |
| `docs/use-case-flow-specification.pdf` | PDF version of the flow specification |
| `architecture/component-diagram.png` | UML Component Diagram |
| `architecture/component-diagram.pdf` | Printable Component Diagram |
| `docs/architecture-justification.docx` | One-page architecture justification |
| `docs/architecture-justification.pdf` | PDF version of architecture justification |
| `docs/problem-statement.md` | Problem statement used for the design |
| `README.md` | Repository guide |

## Architecture

**Selected architectural style: Microservices Architecture**

Main components required by the Lab 3 handout:
- Order Manager Component
- Payment Service Component

Additional components:
- Client & Artist Portal
- Watermark Service
- Asset Storage & Secure Delivery

The component diagram shows provided/required service interfaces and the main data/control flow.

## UML Relationships

The use-case diagram includes:
- `<<include>>` relationships for mandatory sub-functions.
- `<<extend>>` relationship for optional review feedback.

## Suggested GitHub Submission Structure

```text
digital-art-commission-watermarking-portal/
├── README.md
├── requirements/
│   └── requirements.md
├── uml/
│   ├── use-case-diagram.png
│   └── use-case-diagram.pdf
├── architecture/
│   ├── component-diagram.png
│   └── component-diagram.pdf
└── docs/
    ├── problem-statement.md
    ├── use-case-flow-specification.docx
    ├── use-case-flow-specification.pdf
    ├── architecture-justification.docx
    └── architecture-justification.pdf
```

## Submission Checklist

- [x] Problem statement captured
- [x] 5 FRs: FR-001 to FR-005
- [x] 2 NFRs: NFR-001 and NFR-002
- [x] Use-case diagram with actors and `<<include>>` / `<<extend>>`
- [x] One-page use-case flow with preconditions, postconditions, main success scenario and alternate flow
- [x] Component diagram with at least 5 components
- [x] At least 4 interfaces between components
- [x] Provided/required interface notation
- [x] Architecture selection and justification
- [x] Security advantage
- [x] Performance benefit
