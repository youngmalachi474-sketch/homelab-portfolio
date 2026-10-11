[Documentation](README.md) | [Configs](../configs/README.md) | [README](../README.md)

# Media services

The [media configuration catalog](reference/media.md) documents 16 files read directly from the media VM. It includes Compose definitions and application settings; credentials and identifying endpoints are removed.

## Services and relationships

| Component | Role in the documented setup |
| --- | --- |
| Jellyfin | Media library and playback; collected settings are under `/etc/jellyfin` |
| Seerr | Request interface linked to the media-management workflow |
| Sonarr / Radarr | TV/movie management and imports |
| Prowlarr | Indexer configuration and integration with supported applications |
| qBittorrent | Download client |
| Gluetun | VPN container used by the download client's documented network arrangement |
| Lidarr | Music library management |
| Soularr / slskd | Music-related integration and transfer services |
| FlareSolverr | Supporting indexer request service where configured |
| Homarr | Dashboard; separate Compose project |

Presence in Compose shows configuration, not proof that every integration works. The complete request-to-library and music import workflows still need end-to-end validation with authorized test content.

## Storage paths

The documented shared host root is `/mnt/media`; supporting containers use their mapped paths, commonly `/media`. Native Jellyfin uses host paths. Compare the active mount definitions and application roots when investigating missing media or failed imports.

The collection contains qBittorrent settings, ARR application XML, Soularr settings, slskd YAML, Jellyfin XML, and Docker logging settings. The catalog links each actual file to its anonymized source path.

## Read-only checks

Run from the appropriate Compose directory:

```bash
docker compose ps
docker compose config --quiet
docker compose logs --tail 100
```

The published `/home/example/...` path is an anonymized placeholder. Use the real path on the server. For native Jellyfin:

```bash
systemctl status jellyfin --no-pager
journalctl -u jellyfin -n 100 --no-pager
findmnt /mnt/media
df -h / /mnt/media
```

Inspect the active Compose file before assuming a WebUI port belongs to the download container itself. The qBittorrent/Gluetun arrangement described in earlier troubleshooting shares a network namespace.

## Editing and validation

Keep credentials and VPN keys in local secret storage, not this repository. Compare port mappings, mounts, service names, and external URLs against the actual host. Validate Compose syntax before applying a change. Restart only the affected service after backing up its configuration and checking dependencies.

Application XML and client settings may be rewritten by the running application. Prefer supported application settings interfaces where available; if editing a file directly, establish whether the service needs to be stopped first. Sanitized copies are not suitable replacements for production files.

## Recovery

Back up application configuration and persistent state, and keep the media data separate from disposable containers. Confirm that logs are bounded and disk space remains available. See [project history](projects/media-server.md) and [backup and recovery](backup-and-recovery.md).
