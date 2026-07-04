# speedtest-tracker

Speedtest Tracker — periodic internet speed test logging with history and
charts. Built on Laravel with SQLite storage.

## Services

| Container | Image | Ports |
|---|---|---|
| speedtest-tracker | `linuxserver/speedtest-tracker:latest` | 8083 (HTTP), 8445 (HTTPS) |

## Schedule

Runs on a cron schedule: `*/30 * * * *` (every 30 minutes).

## Database

Uses SQLite (`DB_CONNECTION=sqlite`), backed by the config volume. No
external database required.

## Volumes

| Host | Container |
|---|---|
| `~/homelab_volumes/speedtest-tracker/config` | `/config` |
| `~/homelab_volumes/speedtest-tracker/config/keys` | `/config/keys` |

## Configuration

Set `APP_KEY` in `./.env` (Laravel app encryption key). The key should be a
random 32-character base64 string.
