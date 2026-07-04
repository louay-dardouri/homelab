# syncthing

Syncthing — peer-to-peer file synchronization.

## Services

| Container | Image | Ports |
|---|---|---|
| syncthing | `syncthing/syncthing:latest` | 8384 (WebUI), 22000 TCP/UDP (sync), 21027 UDP (discovery) |

## Volumes

| Host | Container |
|---|---|
| `~/homelab_volumes` | `/var/syncthing` |

The entire `~/homelab_volumes` directory is mounted — this is the shared
volume directory used by other stacks (Portainer, Glance, FreshRSS, Speedtest
Tracker), so Syncthing keeps them in sync across machines.

Runs as PUID/PGID 1000. Hostname is set to `my-syncthing` for device
identification.
