# HomeSH applications

Public, immutable, versioned application resources intended for HomeSH releases.

This repository contains only redistributable application metadata and packages:

- a HomeSH-signed OpenWrt APK repository for qualified native applications;
- pinned Docker Compose manifests for qualified container applications;
- versioned application descriptions and upstream-sourced media.

HomeSH firmware carries the repository public key and verifies package signatures. Application catalog entries additionally pin artifact hashes and immutable Git commits. Signing private keys, device configuration, credentials, and user data are never stored here.

Application Center V3 consumes the signed, tagged APK index under
`openwrt/25.12.5/aarch64_cortex-a53/`. OpenWrt plugins are normal executable
APK packages. Docker applications are data-only APK packages containing only
`app.json` and `compose.yaml`; the device's standard Docker Compose CLI owns
container lifecycle. `catalog.json` is presentation-only metadata and never
replaces APK or Docker as installation authority.

Current upstream releases:

- [OpenClash 0.47.133](https://github.com/vernesong/OpenClash/releases/tag/v0.47.133)
- Tailscale 1.98.3
- [OpenClaw 2026.6.34](openclaw/2026.6.34/README.md)
- [Home Assistant Container 2026.8.1](home-assistant/2026.8.1/compose.yaml)

## Development Application Source V2

`source/v2/` is the signed, static Development Application Source consumed by
HomeSH V2 Source clients. It has the stable identity `com.homesh.development`
and publishes one fixed Catalog containing the three applications above.

The TUF metadata, not the GitHub URL or branch, authenticates each snapshot and
prevents rollback. A client must add `source/v2/source-config.json` together
with the exact `source/v2/metadata/1.root.json` bytes; downloading a Root URL
alone does not establish trust. This development Root and its signing key are
not a production trust lineage.

Market filtering is evaluated locally from the Product/SKU country code.
OpenClash is listed for `US` and not `CN`; OpenClaw and Home Assistant are
listed for both current development markets. IP geolocation is not used.

Each upstream project remains subject to its own license.
