# homelab

Self-hosted services on homelab using OrbStack, reachable
remotely over Tailscale instead of exposed to the public internet. Each
service gets its own directory with a `docker-compose.yml`.

## Services

- **atuin:** Shell history sync — [docs](https://docs.atuin.sh/self-hosting/), SQLite-backed.
