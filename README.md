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

