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
