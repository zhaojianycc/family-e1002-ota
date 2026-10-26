# Family E1002 OTA

Current public application: **v1.3.0**, release sequence **1003000**.

Anonymous signed application distribution. No household names, schedules, access tokens or signing private keys are published here. Existing device Wi-Fi and rules survive OTA. Dual 2MB application layout required; do not flash factory images over user configuration.

v1.3.0 adds opt-in private rule synchronization. Configure a repository-scoped fine-grained Contents read-only token once through local management. The public firmware contains no credentials. Private rule packets are independently signed, revisioned and validated before atomic file replacement; failures retain prior rules, unchanged content avoids rewriting, local manual edits pause synchronization. Daily retrieval shares the existing 00:05 wake window. Private household data is published separately to a dedicated PRIVATE repository, never this repository.

GitHub API is the primary OTA endpoint, with raw manifest fallback. Complete image size/SHA256, RSA signature, model/layout and increasing sequence are checked; bounded HTTP Range resume supports interrupted transfers.

v1.3.0 build, ten offline protocol/signature/publishing tests and thirteen previews passed. Distribution TLS, signature and image hash were verified. Private endpoint anonymous access was denied and office authenticated read-back verified. Home installation and device token synchronization remain pending user setup. Previous v1.2.4 hardware testing confirmed OTA resume, app1 boot and TIMER deep-sleep wake. Automatic failure rollback, sleep current and endurance remain unverified.
