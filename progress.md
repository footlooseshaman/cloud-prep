# Cloud Prep — Progress Log

Career pivot: Networking support → Azure cloud networking
Target certs: AZ-900 → AZ-104 → AZ-700
Timeline: 90 days | Min 4 hrs/day

---

## Day 1
- Environment setup: WSL2/Ubuntu, Git (Windows + WSL), VS Code Remote-WSL
- GitHub repo created: cloud-prep
- Azure free account created, portal tour

## Day 2
- AZ-900 theory: cloud definition, pricing models (PAYG/reserved/spot/free tier)
- CapEx vs OpEx, scalability/elasticity/agility
- IaaS/PaaS/SaaS, shared responsibility model
- Azure resource hierarchy: mgmt groups → subscriptions → resource groups → resources
- 2 hr deficit carried forward

## Day 3
- Cleared Git workflow, set up progress log
- AZ-900 theory: Azure global infrastructure (in progress)

## Day 4 (Jun 24) - 87 days left
- AZ-900 Domain 2 COMPLETE: compute (VM/VMSS/App Service/containers/Functions),
  networking (VNet/subnet/NSG/peering), storage (blob+tiers/files/queue/table),
  databases (Azure SQL/Cosmos), resource hierarchy, IaC (ARM/Bicep)
- Concepts: kernel, stateful/stateless, sync/async
- Python: conditionals (if/elif/else), comparison operators, first-match-wins,
  boundary trap (< vs <=)
- Built link_check.py - latency classifier, tested boundaries, committed+pushed


## Day 5

**Azure (AZ-900):**
- Completed Domain 3: cost management (TCO, CapEx vs OpEx, cost factors, Pricing Calculator, Cost Management, budgets/alerts)
- Governance: tags, Azure Policy, resource locks, Microsoft Purview
- Identity & security: Entra ID, AuthN vs AuthZ, MFA, SSO, passwordless, external identities, Conditional Access, Zero Trust, defense-in-depth, Defender for Cloud, RBAC
- Monitoring: Azure Monitor, Service Health, Azure Advisor
- Verified full syllabus against live official Microsoft Learn outline (Jan 14 2026 version)
- **AZ-900 theory: 100% complete**

**Python:**
- Functions: def, parameters vs arguments, return vs print, positional & keyword args
- Dictionaries: key-value access, .get() safe retrieval, .items() loop, list-of-dictionaries (Netmiko inventory pattern)
- **Both Netmiko blockers (functions + dictionaries) cleared**
- Committed: functions_practice.py

**Status:** 85 days left. Ahead of pace. Next: AZ-900 practice exam OR begin Netmiko.


## Day 6

**Azure (AZ-104):**
- Started AZ104

## Day 7
** AZure (AZ-104):**
- Domain 

** Netmiko **


## Day 9 — AZ-104 Storage (Domain 2 complete) + Netmiko config automation

**Time:** Day 9 / 90 · 81 days remaining

### Refresher
- 4/5 — refinements: 802.1X/NAC ↔ Conditional Access (not Entra ID broadly); user-delegation SAS security rationale (blast radius / revocable via delegation key)

### AZ-104 — Domain 2 Storage (CLOSED)
- **Network access controls**
  - Storage firewall — network-layer ACL: permit IPs/VNets, deny rest; account stays public
  - Service endpoint — subnet gets trusted backbone route; source = subnet identity; account stays public; per-subnet; free
  - Private endpoint — private IP inside VNet; public endpoint can be fully disabled; per-resource; needs private DNS zone; has cost
- **Data protection**
  - Soft delete — recover deleted blobs/containers within retention window
  - Versioning — auto-preserve prior state on overwrite/delete; roll back to any version
  - Snapshot — manual point-in-time read-only copy
  - Immutability (WORM) — platform-enforced read-only; survives even Owner; time-based or legal hold; compliance/BFSI staple
  - Key principle: first three live inside the permission model (Owner can purge); immutability is enforced above the identity layer

### Netmiko
- Added `send_config_set` — sends list of config commands, auto-enters/exits config mode (running-config only)
- Added `save_config` — persists running → startup; Netmiko picks correct per-platform command (`write mem`)
- Both verified on live Catalyst 8000v DevNet sandbox
- Mental model: `send_command` (read) → `send_config_set` (write/temp) → `save_config` (persist)

### Owed to Day 10
- Python Rung 3 (default parameters)
- Likely open AZ-104 Domain 3 — Virtual Networking

