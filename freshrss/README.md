# freshrss

FreshRSS — RSS feed aggregator with multi-user support, OPML import, and
API compatibility for mobile clients.

## Services

| Container | Image | Ports |
|---|---|---|
| freshrss | `linuxserver/freshrss:latest` | 8081 (HTTP), 8444 (HTTPS) |

## Volumes

| Host | Container |
|---|---|
| `~/homelab_volumes/freshrss/config` | `/config` |

Runs as PUID/PGID 1000.
