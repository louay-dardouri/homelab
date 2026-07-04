# glance

Glance — self-hosted dashboard / homepage aggregating service status, RSS,
weather, bookmarks, and more.

## Services

| Container | Image | Port |
|---|---|---|
| glance | `glanceapp/glance:latest` | 8080 |

## Volumes

| Host | Container |
|---|---|
| `~/homelab_volumes/glance_config` | `/app/config` |

Configuration is done via `glance.yml` placed in the config directory.
See [glance documentation](https://github.com/glanceapp/glance) for syntax.
