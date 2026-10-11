[Documentation](README.md) | [Configs](../configs/README.md) | [README](../README.md)

# Documentation

This is the documentation hub for the homelab. The configuration collection was read directly from the servers on October 11, 2026 and sanitized before publication. It includes 538 server files, plus a source manifest and an empty environment-variable scaffold.

## Start here

| Guide | Contents |
| --- | --- |
| [Architecture](architecture.md) | Host roles, storage, access paths, and known placement limits |
| [Operations](operations.md) | Finding the active deployment, service checks, and configuration changes |
| [Backup and recovery](backup-and-recovery.md) | What to preserve and how to verify restoration |
| [Troubleshooting](troubleshooting.md) | A repeatable investigation workflow |
| [Configuration reference](reference/README.md) | A catalog entry for every retrieved server file |
| [Roadmap](roadmap.md) | Unfinished validation and portfolio work |
| [Source notes](source-notes.md) | Evidence, collection dates, and confidence limits |

## Service guides

| Guide | Deployment |
| --- | --- |
| [Immich](immich.md) | Personal and second photo-management VMs |
| [Media services](media-services.md) | Jellyfin, ARR stack, download networking, music, and Homarr |
| [Minecraft](minecraft.md) | Native Proxmox service and separate Mint Docker deployment |

## Project background

[Photo backup project](projects/photo-backup.md) · [Media server project](projects/media-server.md) · [Minecraft project](projects/minecraft.md)

These guides describe the collected setup, not a verified clean installation recipe. Configuration snapshots contain replacement values and must be reviewed before use. A running service does not prove that backups, imports, isolation, or every client workflow have been tested.
