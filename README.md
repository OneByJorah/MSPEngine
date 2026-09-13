<div align="center">

![MSPEngine banner](docs/assets/banner.svg)

# MSPEngine

**Windows 10/11 provisioning & debloat utility for MSP technicians** — one-click setup, hardening, and modular configuration.

[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](LICENSE)
[![PowerShell](https://img.shields.io/badge/PowerShell-5.1%2B-blue?logo=powershell&logoColor=fff)](https://docs.microsoft.com/en-us/powershell/)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%2F11-0078d4?logo=windows&logoColor=fff)](https://www.microsoft.com/windows)
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen)](CONTRIBUTING.md)

</div>

---

## What It Does

MSPEngine is a **production-ready Windows provisioning tool** built for Managed Service Providers. Run one script to debloat fresh Windows installs, configure services, and optimize power settings — saving hours per machine.

Instead of manually removing Xbox packages, tweaking services, and configuring power plans across dozens of workstations, MSPEngine does it all in a single parameterized PowerShell execution.

## Quick Start

```powershell
# Run as Administrator (PowerShell 5.1+)
git clone https://github.com/OneByJorah/MSPEngine.git
cd MSPEngine
.\install.ps1
```

Download only, without executing:

```powershell
.\install.ps1 -SkipDeploy
```

## Features

- **One-Click Setup** — Download and run the debloat script in a single step
- **Xbox Debloat** — Remove all Xbox app packages from Windows 10/11
- **Service Optimization** — Configure Print Spooler and other services
- **Power Config** — Set power plan to high performance
- **MSP Optimized** — Parameterized for technician workflows
- **Remote-Ready** — Script URL, temp path, and execution policy are all configurable

## Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `-ScriptUrl` | MSPEngine raw URL | Debloat script source |
| `-SkipDeploy` | off | Download only, skip execution |
| `-TempPath` | `$env:TEMP\debloat.ps1` | Download location |
| `-ExecutionPolicy` | `RemoteSigned` | Execution policy for child process |

## Architecture

```
MSPEngine/
├── install.ps1                     # Main entry point
├── debloat/
│   └── MSP-Ultra-Debloat.ps1      # Debloat module
├── docs/assets/                    # Banner & screenshot
└── README.md
```

## Use Cases

1. **MSP Technicians** — Provision fresh Windows installs for clients
2. **IT Departments** — Standardize workstation builds
3. **Home Users** — Remove bloatware from new machines

## Requirements

- Windows 10 or Windows 11
- PowerShell 5.1 or later
- Administrator privileges

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## Security

See [SECURITY.md](SECURITY.md). Report vulnerabilities to **security@jorahone.com**.

## License

MIT © Jhonattan L. Jimenez (OneByJorah)

---

<p align="center">Built with 🌴 by <a href="https://github.com/OneByJorah">OneByJorah</a> · <a href="https://jorahone.com">jorahone.com</a></p>
