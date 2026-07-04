# dashy

Dashy — self-hosted service dashboard with health monitoring, search, and
customizable categories.

## Services

| Container | Image | Port |
|---|---|---|
| dashy | `lissy93/dashy:latest` | 8082 |

## Volumes

| Host | Container |
|---|---|
| `./config` | `/app/user-data` |

See the [Dashy documentation](https://github.com/Lissy93/dashy) for the full
config spec.
