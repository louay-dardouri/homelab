# pihole

Pi-hole — DNS sinkhole and optional DHCP server.

## Services

| Container | Image | Ports |
|---|---|---|
| pihole | `pihole/pihole:latest` | 53 (DNS), 67 (DHCP), 8000 (HTTP admin), 8443 (HTTPS admin) |

### DNS listening mode

`FTLCONF_dns_listeningMode` is set to `all`, so Pi-hole responds on every
interface. Required for environments where queries arrive via Docker bridge
networks.

### Capabilities

`NET_ADMIN` is added for low-port binding (53, 67) and DHCP lease management.

## Volumes

| Name | Container path | Purpose |
|---|---|---|
| `config` (named volume) | `/etc/pihole` | Pi-hole config, gravity DB, DHCP leases |

## Configuration

Set `ADMIN_PASSWORD` in `./.env`.
