# VibeNest Template: 2FAuth

This is a thin VibeNest-ready deploy adapter for [2FAuth](https://github.com/Bubka/2FAuth).

It does not fork or modify 2FAuth. The repo only provides Docker defaults that VibeNest can turn into generated secrets and a public route:

- official image: `2fauth/2fauth:latest`
- app port: `8000`
- SQLite volume
- explicit `DB_CONNECTION=sqlite` with the upstream Docker sqlite path
- generated `APP_KEY`
- generated public `APP_URL`
- trusted proxy defaults
- no custom Docker healthcheck, so Coolify/VibeNest route validation uses the public HTTP route instead of an image-local curl dependency

## VibeNest notes

The `.env.example` intentionally declares `APP_KEY=` and `APP_URL=` as empty values. VibeNest reads those during a compose deploy, generates a valid Laravel `APP_KEY`, and injects the final VibeNest subdomain as `APP_URL`.

One-click deploy stays disabled until the adapter opens the public setup screen and the catalog copy documents backup expectations for token data.

## Upstream

- Product: https://github.com/Bubka/2FAuth
- Docker compose docs: https://docs.2fauth.app/getting-started/installation/docker/docker-compose/
- Env docs: https://docs.2fauth.app/getting-started/config/env-vars/
