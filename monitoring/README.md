## Prometheus

on each RPI(node_exporter), install and run exporters
```
node_exporter
```

on monitoring server machine, install and run prometheus with config file
```
prometheus --config.file=prometheus.yaml
```

## Grafana

on server machine

```sh
docker compose up -d
```
