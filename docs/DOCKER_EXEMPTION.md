# Docker exemption — MSPEngine

**Status:** Documented exemption from the "every active repository must support containers" requirement.

**Reason:** Windows PowerShell provisioning script (install.ps1) targeting Windows 10/11 technician workstations. There is no server-side service to containerize; the script is executed on the target Windows machine.

**Conclusion:** A Dockerfile and docker-compose.yml are not applicable to this repository.
This file records the exemption so the fleet audit has a written exception on file,
as required by the OneByJorah modernization directive "Definition of Done" clause:

> A repository is complete only when every checklist item passes OR a written exception
> exists explaining why a requirement does not apply.

**Exemption owner:** @OneByJorah
**Last reviewed:** 2026-10-12
