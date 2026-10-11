[Documentation](../README.md) | [Configs](../../configs/README.md) | [README](../../README.md)

# Personal Immich VM: configuration reference

This catalog covers all 3 retrieved files for this role. Source paths are anonymized. Each linked file is a sanitized snapshot, not a deployment-ready configuration.

## immich-network.conf

[Open configuration](../../configs/immich-personal__etc__systemd__system__docker.service.d__immich-network.conf)

**Source:** `/etc/systemd/system/docker.service.d/immich-network.conf`

Docker systemd drop-in. Read unit dependencies and ordering together with the Docker service before changing startup behavior.

**Observed setting names:** `After`, `ExecStartPre`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## immich-storage.conf

[Open configuration](../../configs/immich-personal__etc__systemd__system__docker.service.d__immich-storage.conf)

**Source:** `/etc/systemd/system/docker.service.d/immich-storage.conf`

Docker systemd drop-in. Read unit dependencies and ordering together with the Docker service before changing startup behavior.

**Observed setting names:** `RequiresMountsFor`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## compose.json

[Open configuration](../../configs/immich-personal__opt__immich__compose.json)

**Source:** `/opt/immich/compose.json`

Compose runtime definition. Services present: `database`, `immich-machine-learning`, `immich-server`, `redis`. Review images, mounts, networks, ports, restart policy, and local environment settings together.

**Observed setting names:** `name`, `networks`, `services`, `volumes`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

