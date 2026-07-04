# prunemate

PruneMate — automated Docker resource cleanup. Prunes unused containers,
images, volumes, and networks on a schedule.

## Services

| Container | Image | Port |
|---|---|---|
| prunemate | `anoniemerd/prunemate:latest` | 7676 (maps to container 8080) |

## Volumes

| Host | Container |
|---|---|
| `/var/run/docker.sock` | `/var/run/docker.sock` |
| `./logs` | `/var/log` |
| `./config` | `/config` |

Direct Docker socket mount allows container, image, and volume lifecycle
operations.

## Configuration

| Variable | Value |
|---|---|
| `PRUNEMATE_TZ` | Africa/Tunis |
| `PRUNEMATE_TIME_24H` | true |

## Networking

Uses the default bridge. No external network attachment.
