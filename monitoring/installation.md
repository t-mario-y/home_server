on prometheus server

```sh
gh release download v2.54.1 --repo prometheus/prometheus --pattern '*linux-amd64*'
tar -xvf prometheus-*linux-amd64.tar.gz
mv prometheus-*.linux-amd64/prometheus ~/.local/bin
rm -rf prometheus-*
```

on each RPI(node_exporter)

```sh
gh release download v1.8.2 --repo prometheus/node_exporter --pattern '*linux-arm64*'
tar -xvf node_exporter-*linux-arm64.tar.gz
mv node_exporter-*.linux-arm64/node_exporter ~/.local/bin
rm -rf node_exporter-*
```

