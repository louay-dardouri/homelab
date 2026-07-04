# portracker

PortTracker — real-time port monitoring and discovery tool. Exposes running
processes, open ports, and Docker container networking details.

## Services

| Container | Image | Port | Function |
|---|---|---|---|
| docker-proxy | `tecnativa/docker-socket-proxy:latest` | 2375 | Read-only Docker socket proxy |
| portracker | `mostafawahied/portracker:latest` | 4999 | Port monitoring application |

### Security

Docker socket access is restricted via socket proxy:
- Only `CONTAINERS`, `IMAGES`, `INFO`, `NETWORKS` endpoints are exposed
- POST requests are disabled (`POST=0`) — read-only
- PortTracker connects to `docker-proxy:2375` instead of the socket directly

### Capabilities

Runs with `pid: host`, `SYS_PTRACE`, and `SYS_ADMIN` for process and port
visibility across the host namespace. `apparmor:unconfined` is set to avoid
profile restrictions on system calls.

## Volumes

| Host | Container |
|---|---|
| `./portracker-data` | `/data` |

## Networking

Uses the default bridge. No external network attachment.
