# HomeSH applications

Public, immutable installation artifacts consumed by HomeSH devices.

This repository contains only redistributable application metadata and packages:

- a HomeSH-signed OpenWrt APK repository for qualified native applications;
- pinned Docker Compose manifests for qualified container applications.

HomeSH firmware carries the repository public key and verifies package signatures. Application catalog entries additionally pin artifact hashes and immutable Git commits. Signing private keys, device configuration, credentials, and user data are never stored here.

Current upstream releases:

- [OpenClash 0.47.133](https://github.com/vernesong/OpenClash/releases/tag/v0.47.133)
- [OpenClaw 2026.6.34](https://github.com/openclaw/openclaw/releases/tag/v2026.6.34)

Each upstream project remains subject to its own license.
