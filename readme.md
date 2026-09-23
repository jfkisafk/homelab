# homelab

Self-hosted services on homelab using OrbStack, reachable
remotely over Tailscale instead of exposed to the public internet. Each
service gets its own directory with a `docker-compose.yml`.

## Services

- **atuin:** Shell history sync — [docs](https://docs.atuin.sh/self-hosting/), SQLite-backed.
- **qdrant:** Vector database — [docs](https://qdrant.tech/documentation/), storage persisted to `qdrant/storage/`, API key required (set `QDRANT_API_KEY` in `qdrant/.env`). REST on 30633, gRPC on 30634.
- **valkey:** In-memory KV store — [docs](https://valkey.io/topics/introduction/), data persisted to `valkey/data/`, password required (set `VALKEY_PASSWORD` in `valkey/.env`). Port 30379.
