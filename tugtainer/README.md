# tugtainer

Tugtainer — automated Docker container update manager. Polls registries for
new image versions and restarts containers with updated images.

## Services

| Container | Image | Port | Function |
|---|---|---|---|
| socket-proxy | `linuxserver/socket-proxy:latest` | — | Read/write Docker socket proxy |
| tugtainer | `ghcr.io/quenary/tugtainer:1` | 9412 | Update management agent |

### Security

Docker socket access is restricted via socket proxy:
- Endpoints enabled: `CONTAINERS`, `EVENTS`, `IMAGES`, `INFO`, `PING`,
  `NETWORKS`, `VERSION`
- POST is enabled (`POST=1`) — required for container lifecycle operations
- Proxy runs read-only filesystem with tmpfs for `/run`
- Both containers are labeled `dev.quenary.tugtainer.protected: True` to
  prevent accidental management by other tools

## Volumes

| Name | Container path | Purpose |
|---|---|---|
| `tugtainer_data` (named volume) | `/tugtainer` | Agent state and configuration |

## Configuration

Set `AGENT_SECRET` in `./.env`. This authenticates the agent with the Tugtainer
API for remote management.

## Networking

Both containers share an isolated `tugtainer` bridge network. Not connected to
`homelab_network`.
