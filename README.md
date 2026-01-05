# Monitoring Stack (Prometheus + Grafana + Node Exporter)

A lightweight production-style monitoring stack you can run on any VPS using Docker Compose.

## What’s inside
- **Prometheus**: scrapes and stores metrics
- **Node Exporter**: exposes VPS-level metrics (CPU, RAM, Disk, Network)
- **Grafana**: dashboards and visualization
- **Basic alert rules**: InstanceDown, HighCPU

## Architecture
Grafana --> Prometheus --> Node Exporter

## Requirements
- Docker
- Docker Compose (plugin)

## Quick start
```
git clone https://github.com/Nodes-Astro/production-monitoring-stack
cd monitoring-stack
docker compose up -d
docker compose ps
```

## Access

Prometheus: http://<VPS_IP>:9090

Grafana: http://<VPS_IP>:3000 (default: admin / admin)

Node Exporter: http://<VPS_IP>:9100/metrics

Prometheus targets

Check Status > Targets and ensure both targets are UP.

## Alert rules

Rules live under alert-rules/ and are loaded by Prometheus:

InstanceDown: when up == 0 for 1m

HighCPU: CPU usage > 85% for 2m

## Notes (production tips)

Do not keep admin password in plain env for production.

Consider putting Grafana behind a reverse proxy + HTTPS.

Add Alertmanager for routing alerts to Slack/Telegram.

<img width="1889" height="886" alt="image" src="https://github.com/user-attachments/assets/89275b21-e3c8-41da-b374-e2f0607b0edd" />

## Why this project?
This repository demonstrates a production-style approach to infrastructure monitoring.
Rather than focusing on tooling installation only, it emphasizes observability concepts,
metric-driven visibility, and alert-based awareness.

## Possible improvements
- Add Alertmanager and route alerts to Slack or Telegram
- Put Grafana behind a reverse proxy with HTTPS
- Add application-level metrics
- Introduce retention and resource limits

