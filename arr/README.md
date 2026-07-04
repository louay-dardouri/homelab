# arr — Media Stack

Automated media pipeline: download, organize, stream, and subtitle.

## Services

| Container | Image | Port | Function |
|---|---|---|---|
| jellyfin | `jellyfin/jellyfin:latest` | 8096 | Media streaming server with Intel QSV/VAAPI transcoding |
| qbittorrent | `linuxserver/qbittorrent:latest` | 8088 | Torrent client (WebUI) |
| prowlarr | `linuxserver/prowlarr:latest` | 9696 | Indexer manager — feeds Sonarr/Radarr |
| sonarr | `linuxserver/sonarr:latest` | 8989 | TV series automation |
| radarr | `linuxserver/radarr:latest` | 7878 | Movie automation |
| bazarr | `linuxserver/bazarr:latest` | 6767 | Subtitle management (depends on Sonarr + Radarr) |
| flaresolverr | `ghcr.io/flaresolverr/flaresolverr:latest` | 8191 | Cloudflare challenge solver for indexers |
| dasharr | `schenanigans/dasharr:latest` | 3000 | Unified *arr dashboard |

## Volumes

| Path | Mount | Purpose |
|---|---|---|
| `./config/<service>/` | `/config` | Per-service config |
| `./cache/jellyfin/` | `/cache` | Jellyfin transcode cache |
| `/media` | `/media` | Media library (shared read access) |
| `/media/downloads` | `/downloads` | Torrent downloads (qBittorrent, Sonarr, Radarr) |
| `/dev/dri` | `/dev/dri` | GPU for hardware transcoding (Jellyfin only) |

## Networking

All services are on an isolated `media-stack` bridge network (default) and do
not connect to `homelab_network`.

## Configuration

Edit `./.env`:

```
PUID=1000
PGID=1000
TZ=Africa/Tunis
```
