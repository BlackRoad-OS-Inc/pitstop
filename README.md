<!-- BlackRoad SEO Enhanced -->

# pitstop

> Part of **[BlackRoad OS](https://blackroad.io)** — Sovereign Computing for Everyone

[![BlackRoad OS](https://img.shields.io/badge/BlackRoad-OS-ff1d6c?style=for-the-badge)](https://blackroad.io)
[![BlackRoad OS Inc](https://img.shields.io/badge/Org-BlackRoad-OS-Inc-2979ff?style=for-the-badge)](https://github.com/BlackRoad-OS-Inc)
[![License](https://img.shields.io/badge/License-Proprietary-f5a623?style=for-the-badge)](LICENSE)

**pitstop** is part of the **BlackRoad OS** ecosystem — a sovereign, distributed operating system built on edge computing, local AI, and mesh networking by **BlackRoad OS, Inc.**

## About BlackRoad OS

BlackRoad OS is a sovereign computing platform that runs AI locally on your own hardware. No cloud dependencies. No API keys. No surveillance. Built by [BlackRoad OS, Inc.](https://github.com/BlackRoad-OS-Inc), a Delaware C-Corp founded in 2025.

### Key Features
- **Local AI** — Run LLMs on Raspberry Pi, Hailo-8, and commodity hardware
- **Mesh Networking** — WireGuard VPN, NATS pub/sub, peer-to-peer communication
- **Edge Computing** — 52 TOPS of AI acceleration across a Pi fleet
- **Self-Hosted Everything** — Git, DNS, storage, CI/CD, chat — all sovereign
- **Zero Cloud Dependencies** — Your data stays on your hardware

### The BlackRoad Ecosystem
| Organization | Focus |
|---|---|
| [BlackRoad OS](https://github.com/BlackRoad-OS) | Core platform and applications |
| [BlackRoad OS, Inc.](https://github.com/BlackRoad-OS-Inc) | Corporate and enterprise |
| [BlackRoad AI](https://github.com/BlackRoad-AI) | Artificial intelligence and ML |
| [BlackRoad Hardware](https://github.com/BlackRoad-Hardware) | Edge hardware and IoT |
| [BlackRoad Security](https://github.com/BlackRoad-Security) | Cybersecurity and auditing |
| [BlackRoad Quantum](https://github.com/BlackRoad-Quantum) | Quantum computing research |
| [BlackRoad Agents](https://github.com/BlackRoad-Agents) | Autonomous AI agents |
| [BlackRoad Network](https://github.com/BlackRoad-Network) | Mesh and distributed networking |
| [BlackRoad Education](https://github.com/BlackRoad-Education) | Learning and tutoring platforms |
| [BlackRoad Labs](https://github.com/BlackRoad-Labs) | Research and experiments |
| [BlackRoad Cloud](https://github.com/BlackRoad-Cloud) | Self-hosted cloud infrastructure |
| [BlackRoad Forge](https://github.com/BlackRoad-Forge) | Developer tools and utilities |

### Links
- **Website**: [blackroad.io](https://blackroad.io)
- **Documentation**: [docs.blackroad.io](https://docs.blackroad.io)
- **Chat**: [chat.blackroad.io](https://chat.blackroad.io)
- **Search**: [search.blackroad.io](https://search.blackroad.io)

---


> PitStop — Sovereign DNS filtering. BlackRoad fork of Pi-hole. Network-wide ad blocking on Alice.

Part of the [BlackRoad OS](https://blackroad.io) ecosystem — [BlackRoad-OS-Inc](https://github.com/BlackRoad-OS-Inc)

---

# PitStop — BlackRoad Road Fleet

> **Sovereign DNS filtering and ad blocking.** Fork of [Pi-hole](https://github.com/pi-hole/pi-hole).

---

**PitStop** is BlackRoad's sovereign fork of Pi-hole — network-wide DNS filtering, ad blocking, and query logging on Alice (the gateway node).

## What's Different

- **Fleet DNS hub** — all Pi fleet DNS queries route through Alice
- **120+ blocked domains** — curated blocklist for the network
- **BlackRoad dashboard** — branded admin UI
- **Query logging** — full DNS audit trail

## Deployment

```bash
# On Alice (gateway node)
# PitStop runs as pihole-FTL on ports 53 (DNS) and 443 (admin)
pihole status
pihole -c  # chronometer
```

## Stats

- **DNS Server**: Alice (192.168.4.49:53)
- **Admin Panel**: https://alice:443/admin
- **Blocked**: 120+ domains
- **Queries/day**: ~10K

## Upstream

Forked from [pi-hole/pi-hole](https://github.com/pi-hole/pi-hole) (EUPL upstream).
All BlackRoad modifications are proprietary.

---

**BlackRoad OS, Inc.** — Pave Tomorrow.

*Proprietary. All rights reserved.*
