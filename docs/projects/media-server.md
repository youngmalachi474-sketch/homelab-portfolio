# Self-hosted media server

## Goal

Maintain a Jellyfin library with consistent storage paths and supporting containerized services.

## Documented design

Jellyfin ran natively on Debian through systemd. Supporting applications ran in Docker Compose. The standardized host path was `/mnt/media`, mapped to `/media` inside containers, with subdirectories for movies, shows, music, and download staging.

Native Jellyfin uses the host paths. Containerized applications use their mapped paths. Keeping that distinction clear addresses a recurring source of missing-library and import problems.

The documented environment included Sonarr, Radarr, Prowlarr, Seerr, qBittorrent, Gluetun, and music-related services. End-to-end request and import behavior was not fully verified in the reviewed summaries.

## Troubleshooting examples

| Problem | Finding or response | Evidence limit |
| --- | --- | --- |
| Shared media inaccessible | Worked on shared group membership and standard storage paths | Recheck effective permissions after changes |
| qBittorrent WebUI unavailable | Recreated the container after a stale Gluetun network namespace issue; a subsequent check returned HTTP 200 | Historical fix, not a current health check |
| Root filesystem full | A Docker log was reported at roughly 150 GB | Log rotation and monitoring need current verification |
| Downloads absent from library | Investigated inconsistent roots and import paths | Full request-to-library test remains open |

Hardware transcoding through AMD VA-API was reported working in prior FFmpeg output. This does not establish compatibility for every codec or client.

## Next validation

- Record current service placement and installed versions.
- Verify mount paths and permissions across the complete workflow.
- Test a request and library import using authorized test content.
- Verify bounded container logging.
- Test application configuration backups and restoration.

This repository does not include a production Compose file because the reviewed chats did not provide a reliable, current configuration to reproduce.
