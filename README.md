# Family E1002 OTA

Current version: **v1.2.5**, release sequence 1002005.

v1.2.5 adds optional per-weekday school arrival/dismissal reminder captions, cancellation suppression and local management previews. Existing device rules remain unchanged by OTA; private rule edits must be saved separately through local management after upgrade. v1.2.5 has host and preview validation; hardware results below refer to v1.2.4.

Signed anonymous application distribution for reTerminal E1002. Existing household rules and Wi-Fi stay on the device. This repository contains no private rules, credentials, device logs or signing private key.

The device reads `contents/latest.json` through the GitHub API (raw URL is a fallback), validates HTTPS and RSA-2048/SHA-256 signed metadata, then checks model, partition layout, sequence, size and complete binary SHA-256. Versioned application binaries are in `firmware/`; downloads support bounded HTTP Range resume. Requires the dual-2MB application layout; factory images must not overwrite existing user configuration.

On 2026-10-22, actual hardware downloaded v1.2.4, resumed a broken transfer with HTTP 206, validated all 1,250,336 bytes and booted app1. ADC voltage and a 60-second deep-sleep TIMER wake were observed; scheduling returned to 00:05 Asia/Shanghai. Automatic failure rollback, overnight operation, sleep current and endurance remain unverified. Voltage percentage is an uncalibrated estimate. Production OTA minimum voltage is 3.70V.

Normal devices wake daily near 00:05, synchronize time, check for updates, refresh and sleep. GPIO3 wakes local management. There is no always-on remote diagnostic channel. A laptop publishes signed artifacts; the device fetches them at its next online window.
