[Documentation](../docs/README.md) | [Configs](README.md) | [README](../README.md)

# Sanitized server configurations

Retrieved directly from accessible server files on October 11, 2026 through existing SSH access and Proxmox guest execution. These are sanitized copies of files read from the servers, not configurations reconstructed from chat history.

## Browse the documentation

[Personal Immich](../docs/reference/immich-personal.md) · [Second Immich](../docs/reference/immich-secondary.md) · [Media VM](../docs/reference/media.md) · [Minecraft VM](../docs/reference/minecraft-vm.md) · [Mint Minecraft](../docs/reference/minecraft-mint.md)

Each catalog links to every file for that server role and lists its purpose, format, source path, and observed setting names.

## Coverage

| Server role | Retrieved files | Configuration covered |
| --- | ---: | --- |
| Personal Immich VM | 3 | Active Compose JSON and Docker systemd drop-ins |
| Second Immich VM | 3 | Compose YAML, Caddyfile, storage drop-in |
| Media VM | 16 | ARR Compose, qBittorrent settings, application XML, Soularr, Homarr, slskd, Jellyfin settings |
| Proxmox Minecraft VM | 258 | Native server settings, mod configuration, JourneyMap settings, and user systemd service |
| Linux Mint Minecraft host | 258 | Compose, server.properties, mod `.cfg`, `.config`, `.ini`, and XML settings, JourneyMap settings |

The personal Immich deployment uses `compose.json` on the server; its format was preserved. The Proxmox Minecraft VM was retrieved through SSH after access was configured. It runs a native Minecraft server through a user systemd service and does not have Docker installed. Its files use the `minecraft-vm` prefix. The separately collected Mint files use the `minecraft-mint` prefix; that machine also had a running `forever-stranded` Docker container at collection time. Keep these two deployments separate when comparing settings.

Bundled indexer definitions, databases, photo libraries, worlds, logs, backups, and actual `.env` files are excluded. The empty [.env.example](.env.example) is a generated variable-name scaffold, not a server secret file.

## Filenames and provenance

Files are grouped in one directory for review. A prefix identifies the server role; `__` represents source-path separators. Personal usernames in paths are replaced with `example`. [manifest.json](manifest.json) records each server role, anonymized source path, and SHA-256 digest of the sanitized file. These digests verify the published copies, not the original files containing private settings.

## Sanitization

- Removed API keys, tokens, passwords, private-key values, authorization settings, session keys, and credential-related settings.
- Replaced personal usernames, email addresses, identifying hostnames, UUIDs, and private network addresses.
- Removed comments from non-YAML text configurations to avoid copying incidental personal details; YAML was parsed and rewritten without original comments.
- Blanked selected Minecraft server identity settings and removed actual environment-file contents from the collection.

`REDACTED`, `example`, `server.example.invalid`, and `192.0.2.10` are replacement values. Redaction can change value types or remove entire authentication mappings. These files are reference snapshots, not ready-to-run deployments. Supply local credentials, paths, addresses, and version-appropriate settings before use. Never replace a live server file with a sanitized copy without reviewing the differences.

YAML files were parsed after sanitization. The published copies were checked for retained personal identifiers, private addresses, personal hostnames, private-key headers, and JWT patterns. No deployment or restart was performed during collection.
