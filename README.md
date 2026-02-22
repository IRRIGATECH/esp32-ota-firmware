# ESP32 OTA Firmware Server

This repository hosts firmware binaries and version manifests for ESP32 OTA updates
via Quectel EC200 4G LTE modem.

## GitHub Pages URL

```
https://irrigatech.github.io/esp32-ota-firmware/ota/version.json
```

## How to Publish a New Firmware

1. Build your new firmware in Arduino IDE (or `arduino-cli compile`)
2. Copy the `.bin` to  `ota/firmware_X.Y.Z.bin`
3. Get SHA-256:
   ```powershell
   Get-FileHash ota\firmware_X.Y.Z.bin -Algorithm SHA256
   ```
4. Update `ota/version.json` with new version, URL, sha256 and size
5. Commit and push:
   ```bash
   git add ota/
   git commit -m "Release vX.Y.Z"
   git push
   ```
6. GitHub Pages auto-deploys within ~60 seconds

## Files

```
ota/
├── version.json         ← Manifest (version, URL, SHA-256)
└── firmware_1.0.0.bin   ← Initial firmware binary
```
