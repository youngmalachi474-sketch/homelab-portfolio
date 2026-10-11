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

- Confirm whether the server still runs on Mint or has moved to Proxmox.
- Confirm the final hunger and thirst settings.
- Record the current persistent data mounts and restart behavior.
- Perform a backup and restore test before claiming recoverability.

The versions above describe a historical deployment and are not a recommendation for a new installation.
