# portainer

Portainer CE — container management Web UI.

## Services

| Container | Image | Ports |
|---|---|---|
| portainer | `portainer/portainer-ce:latest` | 9000 (HTTP), 9443 (HTTPS) |

## Volumes

| Host | Container |
|---|---|
| `~/homelab_volumes/portainer/data` | `/data` |
| `/var/run/docker.sock` | `/var/run/docker.sock` |

Direct Docker socket mount allows Portainer to manage the host daemon and
inspect containers, images, volumes, and networks.
