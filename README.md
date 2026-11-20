# WinUNLOCKED Tweaks

**WinUNLOCKED 0.1 Beta — "Have freedom"**

A small PowerShell configuration script for personalising an existing Windows 11 installation with the WinUNLOCKED identity, UK regional settings and a basic privacy configuration.

> **This is a configuration script, not a Windows distribution or ISO builder.** It does not install Windows, create a bootable ISO, or activate Windows.

## What it does

When run with administrator permissions, `build-WinUNLOCKED.ps1`:

- Sets the computer name to `winunlocked`.
- Sets the time zone to `Europe/London`.
- Sets the Windows user language list to English (United Kingdom).
- Creates a WinUNLOCKED data folder at `C:\ProgramData\WinUNLOCKED`.
- Writes a `recipe.json` project metadata file and a `boot.txt` branding text file.
- Applies the Windows diagnostic-data policy value configured in the script and attempts to stop and disable the `DiagTrack` service.

Some Windows privacy settings vary by edition and version. These changes should not be taken as a guarantee that all diagnostics or data collection are disabled.

## Requirements

- An existing Windows 11 installation.
- Windows PowerShell.
- Administrator permissions.
- A backup of important files before making system-wide changes.

## Usage

1. Download or clone this repository.
2. Review `build-WinUNLOCKED.ps1` before running it.
3. Open PowerShell as an administrator.
4. Change to the folder containing the script.
5. Run:

   ```powershell
   powershell -ExecutionPolicy Bypass -File .\build-WinUNLOCKED.ps1
   ```

6. Restart Windows to apply the computer-name change.

## Files created

The script creates the following folder:

```text
C:\ProgramData\WinUNLOCKED\
├── recipe.json
└── boot.txt
```

## Important notes

- The script changes system-wide Windows settings. Read the code before running it.
- It does not currently include an automatic undo or restore function.
- The computer-name change requires a restart.
- The generated recipe is project metadata; it does not build or modify a Windows installation image.
- Windows activation is not included.

## Project status

**Version:** 0.1 Beta  
**Codename:** Have freedom  
**Architecture target in project metadata:** x86_64

WinUNLOCKED Tweaks is an early project. Features and behaviour may change as development continues.

## Disclaimer

This project is provided as-is, without warranty. Use it only on a device you own or are authorised to manage. Back up important data and make sure you understand the changes before running the script.
