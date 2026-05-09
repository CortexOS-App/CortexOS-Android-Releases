# CortexOS for Android — Official Releases

This repository hosts the official signed APK releases of the CortexOS Android app. It is the verifiable, sideloadable distribution channel for users who prefer not to install through Google Play.

The CortexOS source code is not open source. This repository exists solely so users can verify that any APK they install is genuinely the one we shipped.

## Where to download

The latest release is always available at:
**https://github.com/CortexOS-HQ/CortexOS-Android-Releases/releases/latest**

For most users, install through Google Play instead:
**https://play.google.com/store/apps/details?id=com.cortexos.app**

## Verifying your download

Every APK in this repository is signed with the same release key. The signing certificate fingerprint is published below and never changes for the lifetime of the app.

### Signing certificate fingerprint (SHA-256)

```
cb5cdf0e83061dd03db33fbd8097c87994584adea523d192a7f9e0e950650530
```

If a future APK has a different fingerprint, treat that as a signal something has changed.

### Verifying the APK signature

Using the `apksigner` tool from Android SDK Build Tools:

```
apksigner verify --print-certs CortexOS-vX.Y.Z.apk
```

Compare the SHA-256 of the certificate to the value above.

### Verifying the APK file integrity

Each release on GitHub includes the SHA-256 of the APK in the release notes. To check on your computer:

**macOS / Linux:**
```
shasum -a 256 CortexOS-vX.Y.Z.apk
```

**Windows (PowerShell):**
```
Get-FileHash CortexOS-vX.Y.Z.apk -Algorithm SHA256
```

If the value does not match the one in the release notes, do not install the APK.

## Reporting a security issue

If you believe a published APK is tampered with, or if you've found a security issue in CortexOS, email **support@cortexos.app**.

## Why we do this

CortexOS is built on a zero-knowledge architecture. Your data is encrypted on your device with keys we never see. That guarantee is only as strong as the binary you install. Publishing signed APKs with verifiable checksums means you can trust the binary, not just the marketing.

For full architecture details:

- Whitepaper: https://cortexos.app/whitepaper/
- AI disclosure: https://cortexos.app/ai-disclosure/
- Privacy policy: https://cortexos.app/privacy/

## Open-source crypto layer

The cryptographic core that protects your data is open source under MIT at:
**https://github.com/CortexOS-HQ/CortexOS-crypto-core**

## Llama 3.2 model usage

The bundled Llama 3.2 model is provided by Meta and used under the Llama 3.2 Acceptable Use Policy:
**https://www.llama.com/llama3_2/use-policy/**
