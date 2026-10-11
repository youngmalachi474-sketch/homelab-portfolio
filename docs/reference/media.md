[Documentation](../README.md) | [Configs](../../configs/README.md) | [README](../../README.md)

# Media server VM: configuration reference

This catalog covers all 16 retrieved files for this role. Source paths are anonymized. Each linked file is a sanitized snapshot, not a deployment-ready configuration.

## daemon.json

[Open configuration](../../configs/media__etc__docker__daemon.json)

**Source:** `/etc/docker/daemon.json`

Docker daemon settings. Review the active configuration and its impact on all containers before applying changes.

**Observed setting names:** `log-driver`, `log-opts`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## database.xml

[Open configuration](../../configs/media__etc__jellyfin__database.xml)

**Source:** `/etc/jellyfin/database.xml`

Jellyfin database settings. This is a native application configuration snapshot; use host paths and review restart requirements before editing.

**Observed setting names:** `DatabaseType`, `LockingBehavior`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## encoding.xml

[Open configuration](../../configs/media__etc__jellyfin__encoding.xml)

**Source:** `/etc/jellyfin/encoding.xml`

Jellyfin encoding settings. This is a native application configuration snapshot; use host paths and review restart requirements before editing.

**Observed setting names:** `EncodingThreadCount`, `EnableFallbackFont`, `EnableAudioVbr`, `DownMixAudioBoost`, `DownMixStereoAlgorithm`, `MaxMuxingQueueSize`, `EnableThrottling`, `ThrottleDelaySeconds`, `EnableSegmentDeletion`, `SegmentKeepSeconds`, `HardwareAccelerationType`, `EncoderAppPathDisplay`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## network.xml

[Open configuration](../../configs/media__etc__jellyfin__network.xml)

**Source:** `/etc/jellyfin/network.xml`

Jellyfin network settings. This is a native application configuration snapshot; use host paths and review restart requirements before editing.

**Observed setting names:** `BaseUrl`, `EnableHttps`, `RequireHttps`, `CertificatePath`, `CertificatePassword`, `InternalHttpPort`, `InternalHttpsPort`, `PublicHttpPort`, `PublicHttpsPort`, `AutoDiscovery`, `EnableIPv4`, `EnableIPv6`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## system.xml

[Open configuration](../../configs/media__etc__jellyfin__system.xml)

**Source:** `/etc/jellyfin/system.xml`

Jellyfin system settings. This is a native application configuration snapshot; use host paths and review restart requirements before editing.

**Observed setting names:** `LogFileRetentionDays`, `IsStartupWizardCompleted`, `EnableMetrics`, `EnableNormalizedItemByNameIds`, `IsPortAuthorized`, `QuickConnectAvailable`, `EnableCaseSensitiveItemIds`, `DisableLiveTvChannelUserDataName`, `MetadataPath`, `PreferredMetadataLanguage`, `MetadataCountryCode`, `SortReplaceCharacters`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## compose.yml

[Open configuration](../../configs/media__home__example__arr-stack__compose.yml)

**Source:** `/home/example/arr-stack/compose.yml`

Compose runtime definition. Services present: `lidarr`, `sonarr`, `radarr`, `prowlarr`, `seerr`, `flaresolverr`, `soularr`, `qbittorrent`, `gluetun`. Review images, mounts, networks, ports, restart policy, and local environment settings together.

**Observed setting names:** `services`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## config.xml

[Open configuration](../../configs/media__home__example__arr-stack__config__lidarr__config.xml)

**Source:** `/home/example/arr-stack/config/lidarr/config.xml`

Application settings for lidarr. API credentials are redacted; inspect ports, bind settings, and application integration locally.

**Observed setting names:** `BindAddress`, `Port`, `SslPort`, `EnableSsl`, `LaunchBrowser`, `ApiKey`, `AuthenticationMethod`, `AuthenticationRequired`, `Branch`, `LogLevel`, `SslCertPath`, `SslCertPassword`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## config.xml

[Open configuration](../../configs/media__home__example__arr-stack__config__prowlarr__config.xml)

**Source:** `/home/example/arr-stack/config/prowlarr/config.xml`

Application settings for prowlarr. API credentials are redacted; inspect ports, bind settings, and application integration locally.

**Observed setting names:** `BindAddress`, `Port`, `SslPort`, `EnableSsl`, `LaunchBrowser`, `ApiKey`, `AuthenticationMethod`, `AuthenticationRequired`, `Branch`, `LogLevel`, `SslCertPath`, `SslCertPassword`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## qBittorrent-data.conf

[Open configuration](../../configs/media__home__example__arr-stack__config__qbittorrent__qBittorrent__qBittorrent-data.conf)

**Source:** `/home/example/arr-stack/config/qbittorrent/qBittorrent/qBittorrent-data.conf`

qBittorrent client configuration. Authentication values are redacted; review download paths and WebUI/network settings against the actual deployment.

**Observed setting names:** `AllStats`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## qBittorrent.conf

[Open configuration](../../configs/media__home__example__arr-stack__config__qbittorrent__qBittorrent__qBittorrent.conf)

**Source:** `/home/example/arr-stack/config/qbittorrent/qBittorrent/qBittorrent.conf`

qBittorrent client configuration. Authentication values are redacted; review download paths and WebUI/network settings against the actual deployment.

**Observed setting names:** `FileLogger\Age`, `FileLogger\AgeType`, `FileLogger\Backup`, `FileLogger\DeleteOld`, `FileLogger\Enabled`, `FileLogger\MaxSizeBytes`, `FileLogger\Path`, `enabled`, `program`, `Session\DefaultSavePath`, `Session\DisableAutoTMMByDefault`, `Session\ExcludedFileNames`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## config.xml

[Open configuration](../../configs/media__home__example__arr-stack__config__radarr__config.xml)

**Source:** `/home/example/arr-stack/config/radarr/config.xml`

Application settings for radarr. API credentials are redacted; inspect ports, bind settings, and application integration locally.

**Observed setting names:** `BindAddress`, `Port`, `SslPort`, `EnableSsl`, `LaunchBrowser`, `ApiKey`, `AuthenticationMethod`, `AuthenticationRequired`, `Branch`, `LogLevel`, `SslCertPath`, `SslCertPassword`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## config.xml

[Open configuration](../../configs/media__home__example__arr-stack__config__sonarr__config.xml)

**Source:** `/home/example/arr-stack/config/sonarr/config.xml`

Application settings for sonarr. API credentials are redacted; inspect ports, bind settings, and application integration locally.

**Observed setting names:** `BindAddress`, `Port`, `SslPort`, `EnableSsl`, `LaunchBrowser`, `ApiKey`, `AuthenticationMethod`, `AuthenticationRequired`, `Branch`, `LogLevel`, `SslCertPath`, `SslCertPassword`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## config.ini

[Open configuration](../../configs/media__home__example__arr-stack__config__soularr__config.ini)

**Source:** `/home/example/arr-stack/config/soularr/config.ini`

Soularr integration settings. Review application endpoints, library paths, and locally stored credentials before using this copy.

**Observed setting names:** `api_key`, `host_url`, `download_dir`, `disable_sync`, `api_key`, `host_url`, `url_base`, `download_dir`, `delete_searches`, `stalled_timeout`, `remote_queue_timeout`, `use_selected_lidarr_release`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## compose.yml

[Open configuration](../../configs/media__home__example__homarr__compose.yml)

**Source:** `/home/example/homarr/compose.yml`

Compose runtime definition. Services present: `homarr`. Review images, mounts, networks, ports, restart policy, and local environment settings together.

**Observed setting names:** `services`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## compose.yaml

[Open configuration](../../configs/media__home__example__slskddir__compose.yaml)

**Source:** `/home/example/slskddir/compose.yaml`

Compose runtime definition. Services present: `slskd`. Review images, mounts, networks, ports, restart policy, and local environment settings together.

**Observed setting names:** `services`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

## slskd.yml

[Open configuration](../../configs/media__home__example__slskddir__slskd.yml)

**Source:** `/home/example/slskddir/slskd.yml`

slskd application settings. Authentication and private values are removed; review file paths and service endpoints on the actual host.

**Observed setting names:** `debug`, `flags`, `relay`, `directories`, `shares`, `web`, `soulseek`. Lists are abbreviated; the linked file contains the complete settings.

**Before editing:** save the original locally, preserve real credentials and paths, validate syntax, and test the affected service or mod after applying the change.

