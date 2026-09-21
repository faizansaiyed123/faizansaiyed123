# Engineering Evidence

This page is the profile's fact-checkable index. It intentionally points back to repository code and documentation rather than repeating marketing claims.

## Primary systems

### FrameFlux

**Repositories**

- [FrameFlux-Backend](https://github.com/faizansaiyed123/FrameFlux-Backend)
- [FrameFlux-Frontend](https://github.com/faizansaiyed123/FrameFlux-Frontend)

**Evidence**

- Backend service composition and route registration: [app/main.py](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/app/main.py)
- Backend dependency/runtime definition: [pyproject.toml](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/pyproject.toml)
- Architecture, upload validation, background jobs and API surface: [README.md](https://github.com/faizansaiyed123/FrameFlux-Backend/blob/main/README.md)
- Frontend stack includes Next.js, React, TypeScript, Zustand and Playwright: [package.json](https://github.com/faizansaiyed123/FrameFlux-Frontend/blob/main/package.json)

### Telemetry

**Repositories**

- [telemetry-backend](https://github.com/faizansaiyed123/telemetry-backend)
- [telemetry-frontend](https://github.com/faizansaiyed123/telemetry-frontend)

**Evidence**

- Backend architecture, REST API, WebSocket contract, persistence design, auth/RBAC and testing scope: [README.md](https://github.com/faizansaiyed123/telemetry-backend/blob/main/README.md)
- Password hashing and JWT token implementation: [app/core/security.py](https://github.com/faizansaiyed123/telemetry-backend/blob/main/app/core/security.py)
- End-to-end browser journey covering public entry, authentication, live telemetry, simulation, alerts, analytics, hosts, administration, roles, settings, logout guards and mobile navigation: [qa/e2e/test_full_application.py](https://github.com/faizansaiyed123/telemetry-frontend/blob/main/qa/e2e/test_full_application.py)
- Frontend stack and scripts: [package.json](https://github.com/faizansaiyed123/telemetry-frontend/blob/main/package.json)

## Engineering themes

The profile emphasizes four themes because they recur across the verified repositories:

1. **Backend-first system design** — APIs are explicit, state is modeled, and persistence is deliberate.
2. **Realtime behavior** — Telemetry uses authenticated WebSockets and bounded runtime state; the frontend separates transport events from rendering.
3. **Asynchronous workloads** — FrameFlux delegates heavy FFmpeg work to background workers; Telemetry isolates database persistence from generation.
4. **Verification** — both repositories include automated tests, while Telemetry additionally contains a browser-level end-to-end journey that validates complete user flows.

## Repository curation

The GitHub account contains a mix of flagship systems, supporting applications, learning repositories and forks. The public profile deliberately foregrounds original engineering work and does not present forks as authored systems.

That distinction matters: a portfolio is more credible when project ownership and technical evidence are explicit.

## Scope discipline

Claims on the profile are intentionally limited to what can be supported by the current repositories. For example:

- Telemetry is described as **synthetic infrastructure telemetry**, not real production host monitoring.
- Redis/ARQ are associated with **FrameFlux** and not with the current Telemetry architecture.
- ML/AI experience is presented as **additional project experience**, not as the primary engineering identity.
- The profile does not claim Kubernetes, cloud-platform expertise, distributed-systems expertise, or production scale that is not directly demonstrated by the repositories.
