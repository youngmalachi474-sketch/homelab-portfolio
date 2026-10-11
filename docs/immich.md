[Documentation](README.md) | [Configs](../configs/README.md) | [README](../README.md)

# Immich deployments

Two independent Immich VMs were read directly. Each has separate application configuration and photo storage. Earlier project work described migration verification, VirtioFS storage mappings, private Tailscale access for the personal deployment, and Caddy HTTPS access for the second deployment.

## Configuration map

- [Personal VM catalog](reference/immich-personal.md): active Compose JSON and Docker systemd drop-ins.
- [Second VM catalog](reference/immich-secondary.md): Compose YAML, Caddyfile, and storage drop-in.
- [Project history](projects/photo-backup.md): completed migration work and remaining checks.

## Components

The collected Compose files define `immich-server`, `immich-machine-learning`, `database`, and `redis`. The server handles application requests; the machine-learning service supports configured analysis tasks; PostgreSQL stores application records; the Redis-compatible service supports application coordination. Use the image tags or digests in the collected file when identifying this snapshot's software, and verify compatibility before changing them.

The personal server uses `/opt/immich/compose.json`. The second server uses `/opt/immich/docker-compose.yml`. A `.json` Compose definition is not a missing YAML file; it is the format found on that server.

## Read-only checks

Run on the relevant VM:

```bash
cd /opt/immich
# Personal VM:
docker compose -f compose.json ps
# Second VM:
docker compose -f docker-compose.yml ps
```

Use the matching `-f` option for logs and configuration validation. Check the photo mount with `findmnt` before making changes. Review logs locally before publishing excerpts.

## Configuration changes

Keep each instance's database credentials and storage location separate. The published files use redacted credentials and anonymized network values. Preserve the real local secrets outside Git. Check the Docker storage/network drop-ins before assuming Docker can start safely without its required storage or network dependency.

The second server's Caddyfile describes its proxy configuration. The published hostname is a replacement. Check Caddy service status and certificate/proxy logs on the server when diagnosing external access; test local and external paths separately.

## Backup and verification

Preserve both the photo files and a recoverable database backup. Test restoration in an isolated environment before claiming recovery works. Verify accounts, albums, representative files, counts, and storage references. Do not share another instance's library mount as a shortcut.

Mobile upload stalls, DHCP reservation, and cross-instance access testing remain separate checks unless newer evidence resolves them. See [backup and recovery](backup-and-recovery.md).
