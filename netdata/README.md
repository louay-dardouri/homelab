# netdata

Netdata — real-time system monitoring with interactive charts for CPU, memory,
disk, network, processes, and more.

## Services

| Container | Image | Port |
|---|---|---|
| netdata | `netdata/netdata:latest` | 19999 |

## Volumes

| Name | Container |
|---|---|
| `netdataconfig` | `/etc/netdata` |
| `netdatalib` | `/var/lib/netdata` |
| `netdatacache` | `/var/cache/netdata` |
