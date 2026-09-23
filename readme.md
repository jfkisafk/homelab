# homelab

Self-hosted services on homelab using OrbStack, reachable
remotely over Tailscale instead of exposed to the public internet. Each
service gets its own directory with a `docker-compose.yml`.

## Services

- **atuin:** Shell history sync — [docs](https://docs.atuin.sh/self-hosting/), SQLite-backed.
- **qdrant:** Vector database — [docs](https://qdrant.tech/documentation/), storage persisted to `qdrant/storage/`, API key required (set `QDRANT_API_KEY` in `qdrant/.env`). REST on 30633. Also runs `memory-mcp`, a [mcp-server-qdrant](https://github.com/qdrant/mcp-server-qdrant) instance exposing shared agent memory over streamable-HTTP on 30800, model cache persisted to `qdrant/cache/`.
- **valkey:** In-memory KV store — [docs](https://valkey.io/topics/introduction/), data persisted to `valkey/data/`, password required (set `VALKEY_PASSWORD` in `valkey/.env`). Port 30379.
