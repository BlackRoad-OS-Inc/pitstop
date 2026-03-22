# INTEGRATION — pitstop

> How this fork connects to the rest of BlackRoad OS

## Node Assignment

| Property | Value |
|----------|-------|
| **Primary Node** | Alice (.49) |
| **Fork Of** | Pi-hole |
| **RoundTrip Agent** | PitStop Agent |
| **NLP Intents** | 'block domain' / 'dns stats' |
| **NATS Subject** | `blackroad.pitstop.>` |
| **GuardRail Monitor** | `https://guard.blackroad.io/status/pitstop` |

## Deployment

Deploy via blackroad-operator:

```bash
# From blackroad-operator
cd ~/blackroad-operator
./scripts/deploy/deploy-pitstop.sh

# Or via fleet coordinator
./fleet-coordinator.sh deploy pitstop

# Manual deploy to Alice (.49)
ssh blackroad@$(echo "Alice (.49)" | grep -oP '[0-9.]+' || echo "Alice (.49)") \
  "cd /opt/blackroad/pitstop && git pull && sudo systemctl restart pitstop"
```

## Systemd Service

```ini
[Unit]
Description=BlackRoad pitstop (Pi-hole fork)
After=network.target
Wants=network-online.target

[Service]
Type=simple
User=blackroad
WorkingDirectory=/opt/blackroad/pitstop
ExecStart=/opt/blackroad/pitstop/start.sh
Restart=always
RestartSec=5

[Install]
WantedBy=multi-user.target
```

## NATS Integration (CarPool)

```bash
# Subscribe to pitstop events
nats sub "blackroad.pitstop.>" --server nats://192.168.4.101:4222

# Publish status
nats pub "blackroad.pitstop.status" '{"node":"Alice (.49)","status":"running"}' \
  --server nats://192.168.4.101:4222
```

## RoundTrip Agent

The **PitStop Agent** manages this service via RoundTrip:

```bash
# Check agent status
curl -s https://roundtrip.blackroad.io/api/agents | jq '.[] | select(.name=="PitStop Agent")'

# Send command to agent
curl -X POST https://roundtrip.blackroad.io/api/chat \
  -H 'Content-Type: application/json' \
  -d '{"agent":"PitStop Agent","message":"status","channel":"fleet"}'
```

## GuardRail Monitoring

Add to Uptime Kuma (Alice :3001):

| Check | URL/Command | Interval |
|-------|------------|----------|
| HTTP Health | `http://Alice (.49):PORT/health` | 30s |
| Process | `systemctl is-active pitstop` | 60s |
| NATS Heartbeat | `blackroad.pitstop.heartbeat` | 60s |

## Memory System Integration

```bash
# Log actions
~/blackroad-operator/scripts/memory/memory-system.sh log deploy pitstop "Deployed to Alice (.49)"

# Add solutions to Codex
~/blackroad-operator/scripts/memory/memory-codex.sh add-solution "pitstop" "How to restart" \
  "sudo systemctl restart pitstop"

# Broadcast learnings
~/blackroad-operator/scripts/memory/memory-til-broadcast.sh broadcast "pitstop" "Config change: ..."
```

## Related Components

| Component | Role | Connection |
|-----------|------|-----------|
| **TollBooth** (WireGuard) | VPN mesh | All traffic between nodes |
| **CarPool** (NATS) | Messaging | Event pub/sub on `blackroad.pitstop.>` |
| **GuardRail** (Uptime Kuma) | Monitoring | Health checks every 30s |
| **RoadMem** (Mem0) | Memory | Persistent agent state |
| **OneWay** (Caddy) | TLS Edge | HTTPS termination on Gematria |
| **RearView** (Qdrant) | Vector Search | Semantic search over pitstop logs |
| **BackRoad** (Portainer) | Containers | Docker management if containerized |
| **PitStop** (Pi-hole) | DNS | Internal `pitstop.blackroad.local` resolution |
