# Engineering Evidence

This document is the profile's fact-checkable index. The profile is intentionally selective: it highlights **FrameFlux** and **Telemetry** and points back to their repositories for implementation evidence.

## FrameFlux

**Repositories**

- [FrameFlux-Backend](https://github.com/faizansaiyed123/FrameFlux-Backend)
- [FrameFlux-Frontend](https://github.com/faizansaiyed123/FrameFlux-Frontend)

**Architecture evidence**

- [Backend application composition](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/main.py)
- [Worker](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/infrastructure/worker.py)
- [Background tasks](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/infrastructure/tasks.py)
- [Redis infrastructure](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/infrastructure/redis.py)
- [Media engine](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/features/media/engine.py)
- [Conversion](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/features/media/conversion.py)
- [Editing](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/features/media/editing.py)

**Verification evidence**

- [Authentication tests](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_auth.py)
- [Authorization tests](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_authorization.py)
- [Processing/editing tests](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_media_processing_and_editing.py)
- [Upload/validation tests](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_validation_and_uploads.py)
- [Status/job tests](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/tests/test_status_and_jobs.py)

## Telemetry

**Repositories**

- [telemetry-backend](https://github.com/faizansaiyed123/telemetry-backend)
- [telemetry-frontend](https://github.com/faizansaiyed123/telemetry-frontend)

**Runtime evidence**

- [Telemetry manager](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/telemetry_manager.py)
- [Telemetry generator](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/telemetry_generator.py)
- [Anomaly detector](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/anomaly_detector.py)
- [Telemetry persistence](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/telemetry_persistence.py)
- [Alert persistence](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/alert_persistence.py)
- [WebSocket manager](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/websocket_manager.py)
- [WebSocket API](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/api/websocket.py)
- [Telemetry API](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/api/telemetry.py)

**Security evidence**

- [Authentication API](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/api/auth.py)
- [Security helpers](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/core/security.py)
- [Authorization tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/unit/test_authorization.py)
- [Security tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/unit/test_security.py)

**Realtime and integration verification**

- [Telemetry API integration tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_telemetry_api.py)
- [WebSocket integration tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_websocket.py)
- [Simulation API integration tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_simulation_api.py)
- [Full browser journey](https://github.com/faizansaiyed123/telemetry-frontend/blob/main/qa/e2e/test_full_application.py)

## What the profile deliberately does not claim

- Telemetry is **synthetic telemetry**, not a claim of production host-agent monitoring.
- Redis/ARQ belongs to the current FrameFlux architecture; Redis is intentionally not part of the current Telemetry architecture.
- No arbitrary expertise scores, performance numbers, user counts or production-scale metrics are presented.
- No Kubernetes, cloud-platform or distributed-systems expertise is claimed solely from these repositories.
- The profile does not present forks, learning repositories or small experiments as flagship authored systems.

## Visual system

The profile uses a single visual language:

- **Signal Rail** — represents data, jobs and events moving through a system.
- **Graphite surfaces + cyan/teal signal accent** — consistent across dark and light themes.
- **Custom diagrams** — presentation layer for architecture.
- **Mermaid** — inspectable, GitHub-native technical representation inside expandable sections.
- **One restrained animated GIF** — the Signal Rail; no script-driven README animation or third-party dashboard widgets.

## Future project contract

New projects can reuse the same profile structure without redesigning the page:

1. Project name + category
2. One-sentence purpose
3. Custom light/dark architecture visual
4. Three or fewer engineering highlights
5. Expandable implementation evidence
6. Repository / architecture / demo links

The identity stays stable while the evidence grows.
