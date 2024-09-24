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

Grafana cloud can integrate with local prometheus server by remote_write. Add connection on web console with "Hosted Prometheus metrics".
