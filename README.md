<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./assets/profile/hero-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="./assets/profile/hero-light.svg">
    <img src="./assets/profile/hero-light.svg" alt="Faizan Saiyed — Backend Developer focused on Python APIs and systems engineering" width="100%">
  </picture>
</p>

<p align="center">
  <a href="https://faizansaiyed123.github.io/portfolio/">Portfolio</a>
  ·
  <a href="https://www.linkedin.com/in/faizan-saiyed-52b289228/">LinkedIn</a>
  ·
  <a href="./docs/ENGINEERING.md">Engineering evidence</a>
</p>

## Backend & systems engineering

I build web products with a backend-first focus: Python APIs, authorization, persistent data, asynchronous work, realtime delivery, and verification. The projects below show these concerns in larger codebases, with links to the implementation rather than unsupported performance claims or decorative statistics.

## Selected systems

### FrameFlux — Asynchronous media processing

A media-processing platform that moves long-running FFmpeg work into background jobs and makes upload and processing state explicit.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/profile/frameflux-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/profile/frameflux-light.svg">
  <img src="./assets/profile/frameflux-light.svg" alt="FrameFlux architecture: uploads pass validation before Redis and ARQ workers run FFmpeg processing, with PostgreSQL storing application metadata" width="100%">
</picture>

- **Job lifecycle:** queued media processing with status and progress tracking.
- **Upload boundaries:** direct and resumable uploads with size, type and binary-signature checks; resumable sessions support pause, resume, retry and cancellation.
- **Work separation:** PostgreSQL stores application metadata while Redis / ARQ coordinates background workers.

**Stack:** FastAPI · PostgreSQL · Redis / ARQ · FFmpeg · Next.js

[Backend repository](https://github.com/faizansaiyed123/FrameFlux-Backend) · [Frontend repository](https://github.com/faizansaiyed123/FrameFlux-Frontend)

<details>
<summary><strong>Inspect the implementation</strong></summary>

**Runtime paths:** [API composition](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/main.py) · [Worker](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/infrastructure/worker.py) · [Background tasks](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/infrastructure/tasks.py) · [Media engine](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/features/media/engine.py)

**Verification paths:** [Authentication](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_auth.py) · [Authorization](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_authorization.py) · [Processing and editing](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_media_processing_and_editing.py) · [Upload validation](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_validation_and_uploads.py) · [Jobs and status](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_status_and_jobs.py)

</details>

---

### Telemetry — Realtime observability

An observability platform with two inputs: repeatable synthetic signals and a **psutil-based host agent** that sends real machine metrics through an authenticated ingestion API. Both enter the same backend processing path.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/profile/telemetry-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/profile/telemetry-light.svg">
  <img src="./assets/profile/telemetry-light.svg" alt="Telemetry architecture: synthetic signals and a real host agent enter one processing pipeline for anomaly detection, alert lifecycle, PostgreSQL persistence and authenticated WebSocket delivery" width="100%">
</picture>

- **Observability:** anomaly detection, alert rules and lifecycle, incident correlation, SLO and error-budget evaluation, and runtime metrics.
- **Host ingestion:** host-scoped API keys, bounded batches and sequence-based deduplication; an optional HTTP probe reports response latency and success/error state.
- **Realtime delivery:** authenticated WebSockets stream state to the React dashboard while persistence is handled separately.

**Stack:** FastAPI · PostgreSQL · SQLAlchemy · WebSockets · psutil · React · TypeScript · Vite

[Live application](https://telemetry-frontend-chi.vercel.app) · [Backend repository](https://github.com/faizansaiyed123/telemetry-backend) · [Frontend repository](https://github.com/faizansaiyed123/telemetry-frontend)

<details>
<summary><strong>Inspect the implementation</strong></summary>

**Runtime and ingestion:** [Host agent](https://github.com/faizansaiyed123/telemetry-backend/blob/main/agent/telemetry_agent.py) · [Agent setup and retry behavior](https://github.com/faizansaiyed123/telemetry-backend/blob/main/agent/README.md) · [Authenticated ingestion API](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/api/ingestion.py) · [Telemetry manager](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/telemetry_manager.py) · [Anomaly detector](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/anomaly_detector.py) · [WebSocket API](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/api/websocket.py) · [Persistence](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/telemetry_persistence.py)

**Security and verification:** [Security helpers](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/core/security.py) · [Authorization tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/unit/test_authorization.py) · [Authentication API tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_auth_api.py) · [WebSocket integration tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_websocket.py) · [Telemetry API tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_telemetry_api.py) · [Browser journey](https://github.com/faizansaiyed123/telemetry-frontend/blob/main/qa/e2e/test_full_application.py)

</details>

## Technical focus

| Area | Tools demonstrated in these repositories |
|---|---|
| Backend | Python · FastAPI · Flask · Pydantic |
| Data and asynchronous work | PostgreSQL · SQLAlchemy · Alembic · Redis · ARQ |
| Realtime and processing | WebSockets · FFmpeg · Uvicorn |
| Product interfaces | React · Next.js · TypeScript · Vite · Tailwind CSS |
| Verification and delivery | Pytest · integration tests · Playwright · Docker · GitHub Actions |

The deeper [engineering evidence map](./docs/ENGINEERING.md) links profile claims to specific source files and verification paths.

---

<p align="center">
  <sub>Backend Developer · Python APIs · Systems Engineering</sub>
</p>