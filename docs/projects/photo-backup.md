[Documentation](../README.md) | [Configs](../../configs/README.md) | [README](../../README.md)

# Virtualization and photo backup

## Goal

Host photo management on Proxmox while preserving an existing library and keeping separate users' deployments isolated.

## Work reported complete

- Migrated an Immich deployment from Linux Mint to a Debian VM, preserving accounts, albums, photos, and videos.
- Checked the migration using database asset counts, file checksums, and storage references. The migration summary reported 1,362 assets and approximately 28 GB of library data.
- Created a second independent Immich deployment with its own VM, database, accounts, and photo directory.
- Used Proxmox VirtioFS mappings to expose the appropriate storage directory to each VM.
- Configured private access through Tailscale for the personal deployment.
- Configured public HTTPS for the second deployment with Caddy, Let's Encrypt, DuckDNS, and router port forwarding.
- Installed and tested a systemd timer for DuckDNS updates, with the token stored in a root-only file.

## Troubleshooting example

Some mobile uploads stalled at 0%. The later chat reported healthy services, available storage, and successful receipt of other assets. That narrowed the problem toward individual upload behavior rather than proving the entire upload path was broken. The stalled items still needed follow-up.

A separate connectivity issue involved a public hostname failing from home Wi-Fi while local access worked. Testing local, cellular, and Tailscale paths separately helped distinguish server availability from the network path. Local/external app endpoints were configured; a permanent local DNS solution was discussed.

## Remaining work

- Confirm a DHCP reservation for the second server.
- Investigate any remaining stalled uploads.
- Test backup restoration and record recovery results.
- Confirm access isolation with an explicit cross-instance test.
- Verify whether a third deployment is still wanted.

## Contribution and learning

This project was implemented with substantial AI assistance. My direct contributions included account setup, router configuration, mobile testing, and collaboration on troubleshooting. The next goal is to demonstrate migration checks, storage mapping, and network diagnosis independently.
