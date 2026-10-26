# Engineering Evidence

This document is the profile's fact-checkable index. The profile focuses on **FrameFlux** and **Telemetry** and links back to repository code and verification paths instead of relying on arbitrary scores or performance claims.

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

**Runtime and host ingestion evidence**

- [Telemetry manager](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/telemetry_manager.py)
- [Synthetic signal generator](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/telemetry_generator.py)
- [Host agent collector](https://github.com/faizansaiyed123/telemetry-backend/blob/main/agent/telemetry_agent.py)
- [Agent setup, batching and retry behavior](https://github.com/faizansaiyed123/telemetry-backend/blob/main/agent/README.md)
- [Authenticated, host-scoped ingestion API](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/api/ingestion.py)
- [Anomaly detector](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/anomaly_detector.py)
- [Telemetry persistence](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/telemetry_persistence.py)
- [WebSocket manager](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/services/websocket_manager.py)
- [WebSocket API](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/api/websocket.py)

**Security evidence**

- [Authentication API](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/api/auth.py)
- [Security helpers](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/core/security.py)
- [Authorization tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/unit/test_authorization.py)
- [Security tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/unit/test_security.py)

**Realtime and integration verification**

- [Telemetry API integration tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_telemetry_api.py)
- [WebSocket integration tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_websocket.py)
- [Simulation API integration tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_simulation_api.py)
- [Authentication API tests](https://github.com/faizansaiyed123/telemetry-backend/blob/main/tests/integration/test_auth_api.py)
- [Frontend browser journey](https://github.com/faizansaiyed123/telemetry-frontend/blob/main/qa/e2e/test_full_application.py)

## Boundaries and claims

- Telemetry supports both deterministic synthetic events and locally collected host metrics. The repository includes a host agent and authenticated ingestion API; this is implementation evidence, not a claim that a live production fleet is connected.
- The optional HTTP probe derives latency and success/error signals from a configured URL. It does not claim to measure that service's actual application request volume.
- The backend repository describes the current runtime as single-process. The profile does not claim horizontally distributed state or multi-worker scale.
- No arbitrary performance numbers, usage counts, user counts or production-scale metrics are presented.
- No Kubernetes, cloud-platform or distributed-systems expertise is claimed solely from these repositories.
- The profile does not present forks, learning repositories or small experiments as flagship authored systems.

## Visual system

- One light/dark SVG hero and matching light/dark architecture diagrams keep the profile visually consistent.
- Graphite surfaces and a cyan/teal signal accent carry through the light and dark variants.
- Source links and an expandable evidence map make key technical claims inspectable.
- The README does not depend on external statistic widgets, remote badge services or decorative animations.

## Future project contract

New projects can reuse the same evidence-first structure:

1. Project name and category
2. One-sentence purpose
3. A light/dark architecture visual where useful
4. Three or fewer engineering highlights
5. Direct implementation and verification evidence
6. Repository and demo links, when verifiable

The visual identity stays stable while the evidence grows.