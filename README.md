# CLI Proxy API with Envoy

API proxy using CLI Proxy API and Envoy for request routing and model aliasing.

## Quick Start

```bash
# Configure environment
cp .env.example .env
# Edit .env with your ANTHROPIC_API_KEY

# Start services
docker compose up -d

# Login with Antigravity
docker compose exec cliproxyapi /CLIProxyAPI/CLIProxyAPI -no-browser --antigravity-login
```

## Ports

| Port | Service                          |
|------|----------------------------------|
| 8318 | Envoy (main API endpoint)        |
| 8317 | CLI Proxy API (direct access)    |

## Configuration

- **`.env`** - Set `ANTHROPIC_API_KEY` for token counting
- **`config.yaml`** - API keys, model aliases, routing strategy
- **`envoy.yaml`** - Proxy routing rules

## Routing

- `/v1/messages/count_tokens` → Anthropic API (direct)
- All other requests → CLI Proxy API

## Auto-Update

Watchtower automatically updates labeled containers every 5 minutes.

## Commands

```bash
docker compose logs -f      # View logs
docker compose restart      # Restart services
docker compose down && docker compose up -d  # Reset
```
