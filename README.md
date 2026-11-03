# cloady-xray

Minimal xray image for deploying a VLESS + WebSocket node on Cloady (or any container PaaS whose edge terminates TLS).

The container reads its config from environment variables — no secrets are stored in this repo:

- `UUID` — the VLESS client id
- `WSPATH` — the WebSocket path, e.g. `/cl-abc123`
- `PORT` — the port xray listens on (Cloady serves the app on this port)

Build: multi-stage Dockerfile copies the xray binary from `ghcr.io/xtls/xray-core:latest` into Alpine.
