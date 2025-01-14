# Grafana Alloy  Modules

This repository contains Grafana Alloy  modules for collecting and forwarding metrics to Grafana Cloud.

## Modules

### Node Exporter (`modules/node_exporter.alloy`)
Collects system metrics using the Node Exporter and forwards them to Grafana Cloud.

- Exports Unix/Linux system metrics
- Scrapes Node Exporter targets
- Forwards metrics to Grafana Cloud using remote write

### Self Exporter (`modules/self_exporter.alloy`)
Collects metrics about the Grafana Alloy itself and forwards them to Grafana Cloud.

- Exports Grafana Alloy metrics
- Scrapes self-monitoring targets
- Forwards metrics to Grafana Cloud using remote write

## Configuration

The modules require the following environment variables:

- `GRAFANA_PROM_URL`: Your Grafana Cloud Prometheus endpoint URL
- `GRAFANA_PROM_ID`: Your Grafana Cloud Prometheus ID
- `GRAFANA_CLOUD_TOKEN`: Your Grafana Cloud API token

Each module adds a `collector_id` label using the hostname to identify the source of metrics.

## Usage

1. Set up the required environment variables
2. Import the desired module in your Grafana Alloy configuration:
