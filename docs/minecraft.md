[Documentation](README.md) | [Configs](../configs/README.md) | [README](../README.md)

# Minecraft deployments

Two different servers were inspected directly. Do not treat their configuration files as interchangeable.

| Deployment | Runtime | Configuration prefix |
| --- | --- | --- |
| Proxmox Minecraft VM | Native installation; user systemd service; Docker was not installed | `minecraft-vm` |
| Linux Mint host | Running Docker container named `forever-stranded` | `minecraft-mint` |

[Proxmox file catalog](reference/minecraft-vm.md) · [Mint file catalog](reference/minecraft-mint.md)

## Proxmox VM

The server files were found under `/opt/minecraft/forever-stranded`. The user unit was found under the login user's `.config/systemd/user/forever-stranded.service`. The catalog includes that actual unit, server.properties, mod configuration, and JourneyMap server configuration.

From a login session for the service's owning user, inspect:

```bash
systemctl --user status forever-stranded.service --no-pager
journalctl --user -u forever-stranded.service -n 100 --no-pager
```

Read the unit to identify its working directory, Java invocation, memory options, and restart policy. This guide does not infer additional systemd settings such as lingering from the unit's existence.

## Mint host

The Compose file was read from the existing Forever Stranded directory. Earlier documentation recorded Minecraft 1.10.2 and Forge 12.18.3.2511; check the running server's version before treating those historical versions as current.

From the real Compose project directory:

```bash
docker compose ps
docker compose logs --tail 100
```

The repository replaces personal home-directory names with `/home/example`. Inspect volumes before moving or recreating the container.

## Configuration families

- `server.properties`: server-level settings. Some identifying settings were blanked during sanitization.
- Forge/mod `.cfg` files: settings grouped by mod or subsystem. Typed keys often use `B`, `I`, `D`, or `S` prefixes for boolean, integer, decimal, or string values.
- JourneyMap `.config` files: global and dimension-specific settings. Review both when a feature differs by dimension.
- Mod XML: structured configuration or recipe data. Preserve valid XML and the mod's expected element names.
- Compose or systemd files: runtime launch and persistence, separate from gameplay settings.

Every retrieved file has an entry in the relevant catalog. Individual catalog entries list observed groups or setting names; they do not claim a verified behavioral explanation for every third-party mod option.

## Safe changes

Back up the world and relevant configuration before changing mods, versions, or gameplay settings. Make one change at a time. Record the original value and verify behavior after restart. Preserve mod-specific syntax; a valid text file alone does not prove the mod accepts a setting.

Keep player lists, account credentials, worlds, and server logs private. The collection excludes world data and logs. Some replacement values make the published snapshots unsuitable for direct deployment.

## Recovery checks

Stop writes or otherwise create a consistent backup according to the running server's backup mechanism. Restore a copy in an isolated test directory and verify that the world opens with the matching mod set. Backup/restore success and the intended primary deployment still need explicit confirmation.
