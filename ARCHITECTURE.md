# Architecture — Billing Automation System

## Overview
A modular system with clear separation between:
- API / Business Logic (FastAPI)
- ML Services (Python model servers)
- Frontend UI (React)
- Storage (MongoDB + S3-compatible for files)
- Queueing (Redis/RQ or RabbitMQ)
- Auth (JWT / OAuth2)

## High-level Components
1. **API Gateway / Backend**
   - Authentication, Projects, Users, Jobs, Billing endpoints
2. **Processing Worker**
   - Long-running tasks: OCR, QTO, BBS computations
3. **ML Service**
   - Model inference endpoints, versioned models
4. **Frontend**
   - Dashboard, file upload, viewer, bill editor
5. **Storage**
   - Object storage for drawings, artifact versioning
6. **Notification Service**
   - Email/webhook notifications for approvals and job completion

## Data Flow
1. User uploads drawings/BOQ.
2. API stores file, enqueues processing job.
3. Worker picks job, calls ML service + rule engines.
4. Results saved to DB, user notified.
5. User reviews, corrects, generates RA bill export.

## Security
- TLS for all endpoints
- JWT-based auth and RBAC
- Encrypted storage for sensitive attachments
- Audit logs for all critical operations

## Scaling considerations
- Autoscale worker pool
- Use GPU instances for ML inference
- Cache common BOQ items and rate tables
