# FullRecorder - Windows Installer

A lightweight Windows recorder for your **screen, a window or an area, everything you hear and your microphone**, saved together in one MP4. Start, pause and stop from anywhere with a shortcut; nothing appears on screen while you record. A Windows 11-style window browses, trims and recovers recordings. Optional: instant replay, camera bubble, click highlights.

| File | Size | SHA-256 |
|---|---|---|
| `FullRecorder.msi` (4.0.0) | 692,224 bytes | `3BF66440CFD27354A638130E2FEED0C64F06AAFB5614795D9351D127E6B421BD` |
| `FullRecorder-4.0.0-portable.zip` | 885,554 bytes | `49BEC7A4F85EDE1FEB7FADEA8CF3801C1212D6635FD0E3967EC1EDE55082D577` |

## Requirements

- Windows 10 version 2004 or newer, or Windows 11 (x64)
- **.NET 8 Desktop Runtime**: https://dotnet.microsoft.com/download/dotnet/8.0
- **ffmpeg 8 or newer** - `winget install Gyan.FFmpeg`, or press the *Install FFmpeg* button FullRecorder shows when it cannot find it
- Microsoft Edge **WebView2 Runtime** (already included with Windows 11)

## Install with the MSI

1. Download `FullRecorder.msi`.
2. Double-click it. Windows SmartScreen warns because the package is not Authenticode-signed - choose **More info -> Run anyway**.
3. Accept the UAC prompt (the MSI installs to `C:\Program Files\FullRecorder`).
4. Start **FullRecorder** from the Start Menu.
5. Uninstall any time from *Settings > Apps > Installed apps*. **Your recordings are never deleted.**

## Run the portable build

1. Download `FullRecorder-4.0.0-portable.zip` and extract it anywhere.
2. Double-click `FullRecorder.exe`.

No administrator rights and nothing written to Program Files.

## Shortcuts

| Keys | Action |
|---|---|
| `Ctrl+Alt+R` | start / stop and save |
| `Ctrl+Alt+P` | pause / resume (parts are joined into one video) |
| `Ctrl+Alt+F10` | save the last minutes (instant replay) |

## Verify a download

```powershell
Get-FileHash .\FullRecorder.msi -Algorithm SHA256
Get-FileHash .\FullRecorder-4.0.0-portable.zip -Algorithm SHA256
```

Compare against the table above.

## Notes

- Neither artifact is Authenticode-signed, so SmartScreen warns on first run; the hash table is the integrity check.
- The picture is captured and encoded on the graphics card (~0.4 % CPU for the encoder on the development laptop); NVIDIA is used when present, Intel Quick Sync and the CPU are fallbacks.
- Recordings are written crash-proof and can be recovered after a crash or power cut.

## Source

The application source is not published in this repository. This repository carries the installers only.

## License

All rights reserved. This is **not** an MIT-licensed project and no open-source license is granted for the application, the MSI or the portable build. You may download and install them for personal use. Redistribution, modification or republishing is not permitted.