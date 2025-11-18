# Roadmap — Billing Automation System

This roadmap is designed to span from initial MVP -> pilot -> production-ready product. It's modular and allows parallel work across backend, frontend, and ML.

## MVP (0 - 3 months)
- Setup monorepo scaffold (backend/react/ml/docs)
- Basic auth + project management APIs (FastAPI)
- Simple frontend dashboard and file upload form
- Server-side PDF ingestion + OCR stub (Tesseract)
- Basic BOQ/quantity extractor (rule-based for areas & lengths)
- RA bill PDF/Excel export
- Unit tests + CI pipeline (GitHub Actions)
- Documentation (SRS, Architecture, CONTRIBUTING)

## Beta (3 - 6 months)
- Improve OCR with trained models (Detectron2 / custom CV)
- Implement BBS generator (structural steel length calculator)
- Introduce manual correction UI (human-in-the-loop)
- Basic audit rules engine (rate checks, quantity variances)
- Mobile-friendly measurement capture (photo-based measurements)
- Onboard 3 pilot contractors for feedback

## Production (6 - 12 months)
- Model optimization and scaling (GPU inference, model-serving)
- Multi-tenant architecture for enterprises
- Role-based access & advanced approval workflows
- Billing integrations (Tally, QuickBooks exports)
- SLA, monitoring, logging, and hardened infra
- Marketplace for region-specific rate libraries

## Long-term
- Integrate BIM (Revit / IFC) pipelines for direct QTO
- Add tender/estimation modules
- Expand locality-specific tax rules & templates
- Localized UIs (multi-language)
