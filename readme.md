# homelab

Self-hosted services on homelab using OrbStack, reachable
remotely over Tailscale instead of exposed to the public internet. Each
service gets its own directory with a `docker-compose.yml`.

## Services

- **atuin:** Shell history sync — [docs](https://docs.atuin.sh/self-hosting/), SQLite-backed.
- **qdrant:** Vector database — [docs](https://qdrant.tech/documentation/), storage persisted to `qdrant/storage/`, API key required (set `QDRANT_API_KEY` in `qdrant/.env`). REST on 30633, gRPC on 30634.
- **neo4j:** Graph database — [docs](https://neo4j.com/docs/operations-manual/current/docker/), data persisted to `neo4j/data/`, password required (set `NEO4J_PASSWORD` in `neo4j/.env`). Browser/HTTP on 30474, Bolt on 30687.
