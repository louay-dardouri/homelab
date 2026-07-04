# uptime-kuma

Uptime Kuma — service availability monitoring with push notifications
(Discord, Telegram, email, etc.) and a public status page.

## Services

| Container | Image | Port |
|---|---|---|
| uptime-kuma | `louislam/uptime-kuma:latest` | 3001 |

## Volumes

| Host | Container |
|---|---|
| `~/homelab_volumes/uptime-kuma` | `/app/data` |
