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
  <a href="#open-source">Open-source contributions</a>
  ·
  <a href="./docs/ENGINEERING.md">Engineering evidence</a>
</p>

## Backend engineering, end to end

I build full-stack products with a **backend-first focus**: Python APIs, persistent data, authentication and authorization, background processing, realtime delivery, and the interfaces that connect them. I care about clear service boundaries, safe data access, reliable workflows, and implementation details that can be inspected in the code.

<p align="center"><strong>API design · Data integrity · Security boundaries · Async workflows · Realtime systems</strong></p>

## Featured systems

### FrameFlux — Asynchronous media processing

A media-processing platform that moves long-running FFmpeg work out of the request path and makes upload and processing state explicit.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/profile/frameflux-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/profile/frameflux-light.svg">
  <img src="./assets/profile/frameflux-light.svg" alt="FrameFlux architecture: uploads pass validation before Redis and ARQ workers run FFmpeg processing, while PostgreSQL stores application metadata" width="100%">
</picture>

- **Job lifecycle:** queued processing with status and progress tracking.
- **Upload boundaries:** direct and resumable uploads with size, type, and binary-signature checks.
- **Work separation:** PostgreSQL stores metadata while Redis / ARQ coordinates background workers.

**Stack:** FastAPI · PostgreSQL · Redis / ARQ · FFmpeg · Next.js

[Backend repository](https://github.com/faizansaiyed123/FrameFlux-Backend) · [Frontend repository](https://github.com/faizansaiyed123/FrameFlux-Frontend)

<details>
<summary><strong>Inspect implementation and verification evidence</strong></summary>

**Runtime paths:** [API composition](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/main.py) · [Worker](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/infrastructure/worker.py) · [Background tasks](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/infrastructure/tasks.py) · [Media engine](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/features/media/engine.py)

**Verification paths:** [Authentication](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_auth.py) · [Authorization](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_authorization.py) · [Processing and editing](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_media_processing_and_editing.py) · [Upload validation](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_validation_and_uploads.py) · [Jobs and status](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_status_and_jobs.py)

</details>

---

### Telemetry — Realtime observability

An observability platform with two inputs: repeatable synthetic signals and a **psutil-based host agent** that sends machine metrics through an authenticated ingestion API. Both enter the same backend processing path.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/profile/telemetry-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/profile/telemetry-light.svg">
  <img src="./assets/profile/telemetry-light.svg" alt="Telemetry architecture: host and synthetic signals enter one processing pipeline for anomaly detection, alert lifecycle, PostgreSQL persistence, and authenticated WebSocket delivery" width="100%">
</picture>

- **Observability:** anomaly detection, alert rules and lifecycle, incident correlation, SLO and error-budget evaluation.
- **Host ingestion:** host-scoped API keys, bounded batches, sequence-based deduplication, and an optional HTTP probe.
- **Realtime delivery:** authenticated WebSockets stream state to the React dashboard while persistence is handled separately.

**Stack:** FastAPI · PostgreSQL · SQLAlchemy · WebSockets · psutil · React · TypeScript · Vite

[Live application](https://telemetry-frontend-chi.vercel.app) · [Backend repository](https://github.com/faizansaiyed123/telemetry-backend) · [Frontend repository](https://github.com/faizansaiyed123/telemetry-frontend)

<details>
<summary><strong>Inspect implementation and verification evidence</strong></summary>

**Runtime and ingestion:** [Host agent](https://github.com/faizansaiyed123/telemetry-backend/blob/main/agent/telemetry_agent.py) · [Agent setup](https://github.com/faizansaiyed123/telemetry-backend/blob/main/agent/README.md) · [Authenticated ingestion API](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/api/ingestion.py) · [Telemetry manager](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/telemetry_manager.py) · [Anomaly detector](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/anomaly_detector.py) · [WebSocket API](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/api/websocket.py) · [Persistence](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/telemetry_persistence.py)

**Security and verification:** [Security helpers](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/core/security.py) · [Authorization tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/unit/test_authorization.py) · [Authentication API tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_auth_api.py) · [WebSocket integration tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_websocket.py) · [Telemetry API integration tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_telemetry_api.py)

</details>

## More full-stack systems

These projects show the range of product workflows I work on, from individual productivity tools to multi-tenant platforms and data-heavy applications.

- **[Focus Journal](https://github.com/faizansaiyed123/Focus-Journal-Frontend) · [Backend](https://github.com/faizansaiyed123/Focus-Journal-Backend)** — A journaling and focus product with OAuth sign-in, daily check-ins, focus sessions, search, calendar views, and consent-aware AI insights.
- **[Autofix](https://github.com/faizansaiyed123/autofix_frontend) · [Backend](https://github.com/faizansaiyed123/autofix_backend)** — Automotive service workflows spanning repair orders, estimates, invoices, payments, staff access, and a customer portal.
- **[Feature Flag Platform](https://github.com/faizansaiyed123/feature-flag-platform-frontend) · [Backend](https://github.com/faizansaiyed123/feature-flag-platform-backend)** — Organization-scoped feature flags with targeting rules, deterministic rollouts, environment configuration, and scoped SDK keys.
- **[Product Analytics](https://github.com/faizansaiyed123/product_analytics_frontend) · [Backend](https://github.com/faizansaiyed123/product_analytics_backend)** — Event ingestion, idempotency, project API keys, identity merging, access-scoped analytics queries, and exports.
- **[Gemini Chat Clone](https://github.com/faizansaiyed123/gemini-frontend-clone) · [Backend](https://github.com/faizansaiyed123/gemini-backend-clone)** — Persisted chatrooms and messages, queued AI processing, and subscription workflows.

Explore the rest of my [frontend and backend repositories](https://github.com/faizansaiyed123?tab=repositories).

## Open-source contributions

Merged contributions to established projects:

- **[Sentry JavaScript #25488 — Cloudflare Workers KV instrumentation](https://github.com/getsentry/sentry-javascript/pull/25488)** — Adds tracing instrumentation for Workers KV operations, including reads, writes, deletes, and listing.
- **[TrustFlow SDK #586 — Export `isWalletRejection`](https://github.com/trustflow-protocol/trustflow-sdk/pull/586)** — Exposes the existing wallet helper through the public wallet entry point and adds regression coverage.
- **[Sentry JavaScript #25357 — Export the `LoaderSentry` type](https://github.com/getsentry/sentry-javascript/pull/25357)** — Adds a TypeScript type for the APIs exposed by the CDN loader stub.
- **[Sentry Python #7825 — Move active-thread tracking into Starlette](https://github.com/getsentry/sentry-python/pull/7825)** — Centralizes synchronous-handler thread tracking in the Starlette integration.

## Technical toolkit

| Area | Technologies |
|---|---|
| Backend and APIs | Python · FastAPI · Flask · Pydantic · REST · OAuth2 / JWT |
| Data and async work | PostgreSQL · SQLAlchemy · Alembic · Redis · ARQ · Celery |
| Realtime and media | WebSockets · FFmpeg · Uvicorn |
| Frontend | React · Next.js · TypeScript · Vite · Tailwind CSS |
| Delivery and verification | Docker · GitHub Actions · Pytest · integration testing · Playwright |

I prefer showing implementation paths over unsupported performance claims or decorative statistics. The deeper [engineering evidence map](./docs/ENGINEERING.md) links selected architecture, security, and verification paths to their source repositories.

---

<p align="center">
  <strong>Backend Developer · Python APIs · Systems Engineering</strong><br>
  <sub>Open to backend and full-stack engineering opportunities.</sub>
</p>