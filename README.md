# Family E1002 signed OTA releases

This repository hosts **anonymous application firmware only**, signed version manifests and third-party notices. It does not contain household schedules, Wi-Fi credentials, diagnostics, signing private keys, or full device backups.

- Manifest: https://raw.githubusercontent.com/zhaojianycc/family-e1002-ota/main/latest.json
- Firmware: GitHub Releases (candidate / prerelease).
- Hardware: reTerminal E1002, 800x480, ESP32-S3.
- Required layout: dual 2MB OTA slots, SPIFFS at 0x410000 (dual2m-spiffs410000-v1).
- A one-time USB partition migration is required for the original single-slot firmware. Do not upload a factory image using the OTA path.
- Firmware verifies TLS, an RSA-2048/SHA256 signed manifest, size and image SHA256 before switching slots. It retains on-device rules.
- v1.2.0 is a built candidate. Real-device OTA, interrupted download, startup rollback and battery endurance have not yet been validated.

The publishing computer keeps the private signing key locally. A published release does **not** confirm that a particular device installed it. No private telemetry is collected here.

Portions of this software are copyright (c) The FreeType Project (www.freetype.org). All rights reserved. See release third-party-notices.zip. Arduino-ESP32 source/license: https://github.com/espressif/arduino-esp32/tree/2.0.17
