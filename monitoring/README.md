## Prometheus

on each RPI(node_exporter), install and run exporters
```
node_exporter
```

on monitoring server machine
- install prometheus
- add Grafana integration
- run prometheus with config file with merging
```
MERGED_CONFIG=$(mktemp $HOME/tmp/merged_config-XXXXX.yaml) && \
yq '. *=load("prometheus_remote_write_grafana_cloud.yaml")' prometheus_base.yaml > $MERGED_CONFIG && \
prometheus --config.file=$MERGED_CONFIG && \
rm $MERGED_CONFIG
```

## Grafana

Grafana cloud can integrate with local prometheus server by remote_write. Add connection on web console with "Hosted Prometheus metrics".
