# Module 2: API Gateway

**Tech Stack:** FastAPI (Python)

## Purpose
REST API server and SSE handler that orchestrates pipeline execution via job queue (BullMQ).

## Key Features
- REST Endpoints (upload, job status, video download, authentication)
- SSE Streaming for real-time progress events
- Job Queue (BullMQ + Redis)
- Pipeline Orchestrator (executes modules 3-8 sequentially)
- Cost Tracking (aggregate costs per stage, enforce $20 budget limit)

## Endpoints
- `POST /api/v1/upload-audio` → Create job, upload to storage
- `GET /api/v1/jobs/{id}` → Job status (polling fallback)
- `GET /api/v1/jobs/{id}/stream` → SSE progress stream
- `GET /api/v1/jobs/{id}/download` → Final video file
- `POST /api/v1/auth/login` → JWT token

