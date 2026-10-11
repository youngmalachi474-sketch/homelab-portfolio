[Documentation](../README.md) | [Configs](../../configs/README.md) | [README](../../README.md)

# Minecraft hosting

## Documented deployment

Earlier project documentation described a Docker-hosted Forever Stranded server on Linux Mint, using Minecraft 1.10.2 and Forge 12.18.3.2511. A 4 GiB Java heap was recorded.

The project included JourneyMap server settings, waypoint teleporting, and Ultimine configuration. Separate setup documentation covered backups and troubleshooting, but the original document was not available in this workspace.

## Skills practiced

- Managing an application through Docker.
- Editing server and mod configuration.
- Checking service connectivity and logs.
- Separating persistent world data from disposable container runtime state.

## Open checks

- Confirm which of the Mint and Proxmox deployments is intended to be the primary server.
- Confirm the final hunger and thirst settings.
- Record the current persistent data mounts and restart behavior.
- Perform a backup and restore test before claiming recoverability.

The versions above describe a historical deployment and are not a recommendation for a new installation.

## Direct server configuration collection

The [configuration collection](../../configs/README.md) includes separate sanitized files from both the Mint host and the Proxmox Minecraft VM, retrieved directly on October 11, 2026. The Proxmox VM uses a native Minecraft installation managed by a user systemd service; Docker is not installed there. Use files prefixed `minecraft-vm` for that deployment and `minecraft-mint` for the Mint Docker deployment.
