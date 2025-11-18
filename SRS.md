# Software Requirements Specification (SRS)

## 1. Introduction
This SRS describes the Billing Automation System for civil construction billing workflows.

### 1.1 Purpose
Provide an accurate and efficient platform to automate RA billing, BOQ extraction, BBS generation, and billing audits.

### 1.2 Scope
- Ingest: PDF drawings, BOQs, measurement sheets.
- Process: OCR, element detection, quantity computation.
- Output: BOQ, RA bills (PDF/Excel), BBS, audit reports.
- UI: Dashboard, viewer, editing tools, approval workflow.

## 2. Functional Requirements

### FR-001: User Management
- Register, login, roles (admin, billing_engineer, contractor, viewer)
- Password reset, 2FA (future)

### FR-002: Project Management
- Create projects, assign users, upload documents

### FR-003: Document Ingestion
- Upload PDFs and DWG exports
- Validate file types and sizes

### FR-004: Quantity Extraction
- Extract lines/areas/volumes and tabulate measured items
- Provide confidence scores for each extracted item

### FR-005: RA Bill Generator
- Create RA bills using executed quantities and contract rates
- Apply tax rules (GST) and retention logic
- Support multi-stage approval and certification

### FR-006: BBS Generator
- From structural drawings, calculate bar lengths and weights
- Export to CSV/Excel and include bar bending diagram data

### FR-007: Audit Engine
- Rule-based checks (rate mismatches, over-quantities)
- Generate a report of flagged items

### FR-008: Exports & Integrations
- Export to PDF/Excel
- Webhook callback on job completion
- Integrate with accounting systems (future)

## 3. Non-Functional Requirements

### NFR-001: Performance
- Small job (<5 pages) processed within 30s (target)
- System handles 100 concurrent jobs (scaleable)

### NFR-002: Accuracy
- Quantity extraction median error ≤ 7% for MVP; target 5% within 6 months

### NFR-003: Security
- TLS, JWT, role-based access, encrypted storage

### NFR-004: Reliability & Maintainability
- 99% uptime SLO for core APIs (post-production)
- CI/CD with automated tests for PRs

## 4. Data Requirements
- Support various BOQ formats
- Annotated datasets for ML models (stored separately, not committed to repo)

## 5. Constraints & Assumptions
- Users will manually verify ML outputs initially
- High-quality drawings increase accuracy
- Legal/GST rules vary by region and will be modularized

