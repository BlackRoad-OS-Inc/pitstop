# PitStop — BlackRoad Road Fleet

**Proprietary Software — BlackRoad OS, Inc.**

## What is PitStop?

PitStop is BlackRoad's sovereign DNS filtering and ad blocking solution, forked from Pi-hole. It runs on BlackRoad hardware as part of the Road Fleet — our self-hosted infrastructure stack that eliminates cloud dependency.

## Why PitStop?

DNS is the first thing that loads on every request. If someone else controls your DNS, they control what you can access. PitStop runs on Alice as the network-wide DNS filter — blocking ads, trackers, and telemetry at the DNS level before packets ever leave our network.

## Part of the Road Fleet

| Road Name | Upstream | Purpose |
|-----------|----------|---------|
| RoadCode | Gitea | Git hosting |
| OneWay | Caddy | TLS edge & reverse proxy |
| TollBooth | WireGuard | Encrypted mesh VPN |
| PitStop | Pi-hole | DNS filtering |
| Passenger | Ollama | Local AI inference |
| RearView | Qdrant | Vector database |
| Curb | MinIO | Object storage |
| RoundAbout | Headscale | Mesh coordination |
| CarPool | NATS | Pub/sub messaging |
| OverPass | n8n | Workflow automation |
| BackRoad | Portainer | Container management |
| GuardRail | (custom) | AI safety guardrails |

## License

This software is proprietary to BlackRoad OS, Inc. See [LICENSE](LICENSE) for full terms.

Public code is not open source. You may view and learn from this code. Commercial use, forking, and redistribution are prohibited.

---

**BlackRoad OS — Pave Tomorrow.**

*Copyright 2024-2026 BlackRoad OS, Inc. All Rights Reserved.*
