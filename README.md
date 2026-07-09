# VibeNest Template: 2FAuth

This is a thin VibeNest-ready deploy adapter for [2FAuth](https://github.com/Bubka/2FAuth).

It does not fork or modify 2FAuth. The repo only provides Docker defaults that VibeNest can turn into generated secrets and a public route:

- official image: `2fauth/2fauth:latest`
- app port: `8000`
- SQLite volume
- generated `APP_KEY`
- trusted proxy and app URL placeholders

## VibeNest notes

One-click deploy stays disabled until the recipe generates `APP_KEY`, sets `APP_URL` from the final VibeNest subdomain, opens the public setup screen, and documents backup expectations for token data.

## Upstream

- Product: https://github.com/Bubka/2FAuth
- Docker compose docs: https://docs.2fauth.app/getting-started/installation/docker/docker-compose/
- Env docs: https://docs.2fauth.app/getting-started/config/env-vars/
