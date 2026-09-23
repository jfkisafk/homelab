# AGENTS.md

## Overview

Self-hosted services on a homelab via OrbStack, reachable over Tailscale rather
than exposed to the public internet. Each service is a top-level directory with
a `docker-compose.yml`. No build, lint, or test tooling.

## Services

- **atuin/** — Shell history sync server ([docs](https://docs.atuin.sh/self-hosting/)),
  SQLite-backed. Config and the DB live in the gitignored `atuin/config/`; only
  `docker-compose.yml` and `.gitignore` are tracked per service.
- **valkey/** — In-memory KV store. Data lives in the gitignored `valkey/data/`.

## Adding a service

- New top-level directory named after the service, containing a `docker-compose.yml`.
- Gitignore any directory holding runtime state/config/databases (see
  `atuin/.gitignore` — typically just `config/`).
- Prefer pinned image tags (e.g. `ghcr.io/atuinsh/atuin:18.21.0`) over `latest`.
- Add a bullet under **Services** in `readme.md` describing it and linking to its docs.

## CI

`.github/workflows/gitleaks.yml` runs gitleaks on every push/PR. Since real
config/DB files are gitignored, don't force-add them.
