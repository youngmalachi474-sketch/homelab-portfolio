[Documentation](README.md) | [Configs](../configs/README.md) | [README](../README.md)

# Backup and recovery

This is a recovery checklist for the documented services. It is not evidence that each backup or restoration has already been performed.

| Service | Preserve | Verification |
| --- | --- | --- |
| Immich | Photo/video files, database backup, active deployment configuration, local secrets, storage mapping information | Restore separately; check accounts, albums, asset counts, representative file integrity, and storage references |
| Media services | Application configuration/state and media files; local VPN/API credentials stored separately | Restore settings; check mounts, permissions, connectivity, representative playback, and imports |
| Minecraft | World data, server settings, matching mod set/configuration, launcher/unit/Compose definition | Restore to an isolated copy; check world loading and representative gameplay |
| Proxmox/storage | Host configuration and mapping information appropriate to the chosen backup method | Verify VM restoration and that the intended storage mounts are accessible |

## Procedure

1. Decide what state must be consistent and whether the application must be stopped or use a supported backup mechanism.
2. Create the backup and record the service/version, date, and required dependencies.
3. Store recovery credentials separately from this repository.
4. Restore to an isolated location or test VM.
5. Validate application data and user-facing behavior.
6. Record the result and recovery steps.

A copied configuration folder does not replace an application database or user data backup. A shared storage pool or RAID layout does not by itself establish backup recoverability.

Do not test recovery by overwriting the only working library, database, or world. Published sanitized configuration files help document structure but do not contain the real secrets or data required for restoration.
