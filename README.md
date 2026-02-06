# CLI Proxy API

CLI Proxy API is a proxy server designed to manage and route API requests, particularly for large-scale AI model providers. It features remote management, usage statistics, and model aliasing.

## Features

- **Model Aliasing**: Maps custom model names to specific provider model versions (e.g., Antigravity models to Gemini/Claude).
- **Remote Management**: Optional remote control panel integration.
- **Quota Management**: Automatic project switching on quota exhaustion.
- **Docker Support**: Easy deployment using Docker Compose with automatic updates via Watchtower.

## Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Configuration

The application is configured via `config.yaml`. Key settings include:

- `port`: The main server port (default: 8317).
- `api-keys`: Authorized API keys for accessing the proxy.
- `oauth-model-alias`: Custom mappings for various AI models.
- `routing`: Strategy for request distribution (e.g., `fill-first`).

## Deployment

To start the service using Docker Compose:

```bash
docker-compose up -d
```

This will launch two services:

1. `cliproxyapi`: The core proxy service.
2. `watchtower`: Automatically updates the container image when new versions are released.

## Usage

Once running, the API will be available on the ports defined in `docker-compose.yml`. Use your configured API keys to authenticate requests.

## License

Refer to the project repository for licensing information.
