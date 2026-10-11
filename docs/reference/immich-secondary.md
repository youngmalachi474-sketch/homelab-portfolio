[Documentation](../README.md) | [Configs](../../configs/README.md) | [README](../../README.md)

# Second Immich VM: configuration reference

This catalog covers all 3 retrieved files for this role. Source paths are anonymized. Each linked file is a sanitized snapshot, not a deployment-ready configuration.

## Caddyfile

[Open configuration](../../configs/immich-secondary__etc__caddy__Caddyfile)

**Source:** `/etc/caddy/Caddyfile`

Reverse-proxy/site configuration for Caddy. The published hostname is a replacement; verify local upstream routing and HTTPS on the actual server.

**Observed groups:** `server.example.invalid`.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## immich-storage.conf

[Open configuration](../../configs/immich-secondary__etc__systemd__system__docker.service.d__immich-storage.conf)

**Source:** `/etc/systemd/system/docker.service.d/immich-storage.conf`

Docker systemd drop-in. Read unit dependencies and ordering together with the Docker service before changing startup behavior.

**Observed setting names:** `RequiresMountsFor`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## docker-compose.yml

[Open configuration](../../configs/immich-secondary__opt__immich__docker-compose.yml)

**Source:** `/opt/immich/docker-compose.yml`

Compose runtime definition. Services present: `immich-server`, `immich-machine-learning`, `redis`, `database`. Review images, mounts, networks, ports, restart policy, and local environment settings together.

**Observed setting names:** `name`, `services`, `volumes`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

