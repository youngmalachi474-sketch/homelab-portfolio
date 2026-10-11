[Documentation](README.md) | [Configs](../configs/README.md) | [README](../README.md)

# My troubleshooting workflow

This is the workflow I am practicing for homelab work and entry-level IT support.

1. Record the symptom, exact error, time, and affected devices.
2. Determine scope: one application, one device, one network path, or the whole service.
3. Check basic connectivity and distinguish IP reachability from name resolution.
4. Check service state, recent logs, storage capacity, mounts, and permissions.
5. Form a specific hypothesis and make one reversible change.
6. Repeat the original test and compare the result.
7. Record the fix, remaining uncertainty, and a rollback path.

## Read-only Linux checks

Run these on the relevant host. Replace example units and paths with the actual service being investigated.

```bash
df -h
findmnt
systemctl status jellyfin --no-pager
journalctl -u jellyfin -n 100 --no-pager
docker compose ps
docker compose logs --tail 100
```

Docker Compose commands must run from the project directory or use the correct compose file. Logs and inventories can contain private information; review them before adding excerpts to this repository.

## Incident record

Use the GitHub issue template to record symptoms, environment, hypotheses, actions, and verification. A fix is complete when the original symptom is retested and the result is documented.
