# TICK Stack + Grafana via Docker Compose

This repo contains a full monitoring stack:
- Telegraf (collect metrics)
- InfluxDB (store metrics)
- Kapacitor (alerting engine)
- Grafana (visualize metrics)

## Usage

```bash
git clone https://github.com/ZdravecPanov/tick-stack-docker.git
cd tick-stack-docker
docker-compose up -d
