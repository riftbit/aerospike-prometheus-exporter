# Changelog

This file documents all notable changes to Aerospike Prometheus Exporter


## [v1.1.6](https://github.com/aerospike/aerospike-prometheus-exporter/releases/tag/v1.1.6)

### Improvements
- [TOOLS-1614] - Fetch credentials and certificates via file, environment variables and in base64 encoded form.
- Added new XDR (per DC) metric - `nodes`.


## [v1.1.5](https://github.com/aerospike/aerospike-prometheus-exporter/releases/tag/v1.1.5)

### Improvements
- [TOOLS-1603] - Use latency info commands based on Aerospike build version.
- [TOOLS-1602] - Add device or file name as a label in `storage-engine` statistics.

### Fixes
- [TOOLS-1595] - Fix info commands to get address and port for TLS and non-TLS service
- [TOOLS-1601] - Add constant labels to `aerospike_node_up` metric


## [v1.1.4](https://github.com/aerospike/aerospike-prometheus-exporter/releases/tag/v1.1.4)

### Improvements
- Add new metrics and configs introduced in Aerospike 5.2
    - `device_data_bytes`
    - `xdr-bin-tombstone-ttl`
    - `ignore-migrate-fill-delay`
- Add `--version` command line option


## [v1.1.3](https://github.com/aerospike/aerospike-prometheus-exporter/releases/tag/v1.1.3)

### Improvements
- Add `/health` and `/` url endpoints
- Add some missing namespace, node and xdr statistics

### Fixes
- Fix concurrent map writes
- Add mutex to protect against concurrent collection


## [v1.1.2](https://github.com/aerospike/aerospike-prometheus-exporter/releases/tag/v1.1.2)

### Improvements
- Optimize latency data export - use only non-zero buckets.
- Use `latencies` info command against Aerospike versions 5.1 and above.

### Fixes
- Retry for connection, network or timeout errors.


## [v1.1.1](https://github.com/aerospike/aerospike-prometheus-exporter/releases/tag/v1.1.1)

### Fixes
- Tolerate older configurations - metrics' `_whitelist` and `_blacklist`


## [v1.1.0](https://github.com/aerospike/aerospike-prometheus-exporter/releases/tag/v1.1.0)

### Features
- Add support for using a `blocklist` to filter metrics.
- Export latency metrics as Prometheus histograms.

### Improvements
- Remove accumulated metric `aerospike_node_info` to prevent cardinality explosion.
- Reuse connections to aerospike node.
- Package Aerospike Prometheus Exporter as `.rpm`/`.deb`/`.tar`.
- Add `trace` level logging.

### Fixes
- Fix glob pattern regex used for metric allowlist and blocklist.

### Other Changes
- Rename configurations `_whitelist` to `_allowlist`.
- Rename `aeroprom.conf.dev` to `ape.toml`.
- Update docker image entrypoint script and config files,
    - Add `log_file` config.
    - Remove `update_interval` unused config.
    - Fix `password` config.
- Cleanup unused configurations


## [v1.0.0](https://github.com/aerospike/aerospike-prometheus-exporter/releases/tag/v1.0.0)

- Initial Release.