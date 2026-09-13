# MSPEngine

> A single-parameterized PowerShell installer that downloads and executes the MSP Ultra-Debloat payload to standardize fresh Windows 10/11 workstation builds.

[![License](https://img.shields.io/github/license/OneByJorah/MSPEngine?style=for-the-badge&color=FFB300&labelColor=0a0a09)](https://github.com/OneByJorah/MSPEngine)
[![Top Language](https://img.shields.io/github/languages/top/OneByJorah/MSPEngine?style=for-the-badge&color=FFB300&labelColor=0a0a09)](https://github.com/OneByJorah/MSPEngine)
[![Stars](https://img.shields.io/github/stars/OneByJorah/MSPEngine?style=for-the-badge&color=FFB300&labelColor=0a0a09)](https://github.com/OneByJorah/MSPEngine/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/OneByJorah/MSPEngine?style=for-the-badge&color=FFB300&labelColor=0a0a09)](https://github.com/OneByJorah/MSPEngine/commits)
[![CodeQL](https://img.shields.io/github/actions/workflow/status/OneByJorah/MSPEngine/codeql.yml?style=for-the-badge&color=FFB300&labelColor=0a0a09&label=codeql)](https://github.com/OneByJorah/MSPEngine/actions/workflows/codeql.yml)

## What This Is

MSPEngine is a Windows 10/11 provisioning and debloat utility for MSP technicians. `install.ps1` verifies the host OS, PowerShell version, and elevation, enables TLS 1.2 for the download, fetches the `debloat/MSP-Ultra-Debloat.ps1` payload to a temp path, and executes it in a child process — removing bundled Appx packages, configuring services, and applying the high-performance power scheme in one step.

Windows-only, PowerShell 5.1+, and must run from an elevated prompt. There is no container or headless mode; review `debloat/MSP-Ultra-Debloat.ps1` before running against client machines.

## Quick Start

```powershell
# From an elevated PowerShell prompt
git clone https://github.com/OneByJorah/MSPEngine.git
cd MSPEngine
.\install.ps1
```

Download only, without executing the payload:

```powershell
.\install.ps1 -SkipDeploy
```

## Features

- One-step download-and-execute from a parameterized entrypoint.
- Xbox and bundled Appx debloat for Windows 10/11.
- Service optimization, including Print Spooler configuration.
- High-performance power plan activation.
- Remote-ready parameters: script URL, temp path, execution policy.
- `-SkipDeploy` dry-run path to stage the payload for review.

## Architecture

```
MSPEngine/
├── install.ps1                     # Entry point: download + execute
├── debloat/
│   └── MSP-Ultra-Debloat.ps1       # Payload (Appx, services, power)
└── install.sh                      # Bootstrap helper
```

| Parameter | Default | Description |
|---|---|---|
| `-ScriptUrl` | MSPEngine raw GitHub URL | Debloat script source |
| `-SkipDeploy` | off | Download only, skip execution |
| `-TempPath` | `$env:TEMP\debloat.ps1` | Download location |
| `-ExecutionPolicy` | `RemoteSigned` | Child-process execution policy |

## Stack

PowerShell 5.1+, Windows 10/11, Appx package management.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). [Open an issue](https://github.com/OneByJorah/MSPEngine/issues) for bugs or ideas.

## License

MIT — see [LICENSE](LICENSE).
