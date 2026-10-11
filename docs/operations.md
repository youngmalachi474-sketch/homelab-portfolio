[Documentation](README.md) | [Configs](../configs/README.md) | [README](../README.md)

# Operations and configuration changes

## Find the active configuration

Use the role-specific guide first. The personal Immich deployment uses Compose JSON; the second Immich and media services use Compose YAML; the Minecraft VM uses a user systemd unit; Mint Minecraft uses Docker. Do not assume a single command manages all hosts.

The [manifest](../configs/manifest.json) maps published filenames to server roles and anonymized source paths. `__` in a published filename represents a source path separator. Placeholder paths and credentials must be replaced with the actual local settings before validation or deployment.

## Change workflow

1. Identify the host, service, actual active file, and dependencies.
2. Save a local backup of configuration and required persistent state.
3. Record the change and rollback method.
4. Edit the active file or supported application setting; preserve local secrets.
5. Validate the format and relevant runtime configuration.
6. Apply the smallest required restart or reload.
7. Repeat the original user-facing test and inspect service health.
8. Document results and remaining uncertainty.

## Read-only checks

```bash
df -h
findmnt
systemctl status SERVICE --no-pager
journalctl -u SERVICE -n 100 --no-pager
```

Replace `SERVICE` with the real unit. For user services, use `systemctl --user` and `journalctl --user` in the owning user's session. For Compose, select the actual project directory and file before running `ps`, `config --quiet`, or `logs`.

## Secrets and published copies

The repository contains sanitized reference snapshots. `REDACTED`, `example`, `server.example.invalid`, and documentation addresses are replacements. Some authentication mappings or setting types were changed to remove secrets. Do not run these snapshots unchanged or copy them over working server configuration.

The empty [environment scaffold](../configs/.env.example) contains variable names only. Actual `.env` files, credentials, databases, worlds, photo libraries, and logs were not published.

## Refreshing the documentation

Retrieve active files through authorized read-only access, sanitize locally, validate formats, update the manifest checksums, and review the diff before publishing. Catalog setting lists describe the October 11, 2026 snapshots and should be regenerated when snapshots change.
