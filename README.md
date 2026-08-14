# HomeSH applications

Public, immutable, versioned application resources intended for HomeSH releases.

This repository contains only redistributable application metadata and packages:

- a HomeSH-signed OpenWrt APK repository for qualified native applications;
- pinned Docker Compose manifests for qualified container applications;
- versioned application descriptions and upstream-sourced media.

HomeSH firmware carries the repository public key and verifies package signatures. Application catalog entries additionally pin artifact hashes and immutable Git commits. Signing private keys, device configuration, credentials, and user data are never stored here.

The current HomeSH firmware does not dynamically discover this repository. Adding
an application directory here alone does not make a card appear on existing
devices; that requires a separate, generic catalog-delivery capability. This
repository deliberately does not invent a second catalog or manifest protocol.

Current upstream releases:

- [OpenClash 0.47.133](https://github.com/vernesong/OpenClash/releases/tag/v0.47.133)
- [OpenClaw 2026.6.34](openclaw/2026.6.34/README.md)

Each upstream project remains subject to its own license.
