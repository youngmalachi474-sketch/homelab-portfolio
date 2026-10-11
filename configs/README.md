# Sanitized server configurations

Retrieved directly from accessible server files on October 11, 2026 through existing SSH access and Proxmox guest execution. These are sanitized copies of files read from the servers, not configurations reconstructed from chat history.

## Coverage

| Server role | Retrieved files | Configuration covered |
| --- | ---: | --- |
| Personal Immich VM | 3 | Active Compose JSON and Docker systemd drop-ins |
| Second Immich VM | 3 | Compose YAML, Caddyfile, storage drop-in |
| Media VM | 16 | ARR Compose, qBittorrent settings, application XML, Soularr, Homarr, slskd, Jellyfin settings |
| Linux Mint Minecraft host | 258 | Compose, server.properties, mod `.cfg`, `.config`, `.ini`, and XML settings, JourneyMap settings |

The personal Immich deployment uses `compose.json` on the server; its format was preserved. The Proxmox Minecraft VM has no QEMU guest agent configured and could not be read through that route. The collected Minecraft files came directly from the accessible Mint machine, which still had a running `forever-stranded` container. They do not establish the current configuration of the separate Proxmox Minecraft VM.

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
