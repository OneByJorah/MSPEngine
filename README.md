<div align="center">

![MSPEngine banner](docs/assets/banner.svg)

# MSPEngine

Windows 10/11 provisioning and debloat utility for MSP technicians

![License](https://img.shields.io/badge/license-MIT-brightgreen)
![Language](https://img.shields.io/badge/language-PowerShell-blue)
</div>

---

<p align="center">
  <img src="docs/assets/screenshot.png" alt="MSPEngine preview" width="90%">
</p>

<br>

---

## Features

- **One-Click Setup** — Download and run the debloat script in a single step.
- **Debloat** — Remove Xbox app packages from Windows 10/11.
- **MSP Optimized** — Parameterized for technician workflows (`-ScriptUrl`, `-SkipDeploy`, `-TempPath`, `-ExecutionPolicy`).

> More modules (hardening, network, drivers, software, updates) are planned — see [ROADMAP.md](ROADMAP.md).

## Quick Start

```powershell
git clone https://github.com/OneByJorah/MSPEngine.git
cd MSPEngine

# Run as Administrator (PowerShell 5.1+)
.\install.ps1
```

Download only, without executing:

```powershell
.\install.ps1 -SkipDeploy
```

## Components

| Component | Description |
|-----------|-------------|
| **install.ps1** | Entry point — downloads and executes the debloat script |
| **debloat/MSP-Ultra-Debloat.ps1** | Debloat module — removes Xbox packages, configures services/power |

### Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `-ScriptUrl` | MSPEngine raw URL | Debloat script source |
| `-SkipDeploy` | off | Download only, skip execution |
| `-TempPath` | `$env:TEMP\debloat.ps1` | Download location |
| `-ExecutionPolicy` | `RemoteSigned` | Execution policy for the child process |

## Project Structure

```
MSPEngine/
├── install.ps1                     # Main entry point
├── debloat/
│   └── MSP-Ultra-Debloat.ps1      # Debloat module
├── docs/assets/                    # Banner & screenshot
└── README.md
```

## Security

For security concerns, see [SECURITY.md](SECURITY.md). Please report vulnerabilities to **security@jorahone.com** — do not use public issues.

## License

MIT © Jhonattan L. Jimenez (OneByJorah)

---

<p align="center">Built with 🌴 by <a href="https://github.com/OneByJorah">OneByJorah</a> · <a href="https://jorahone.com">jorahone.com</a></p>
