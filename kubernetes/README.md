## requirements

install `kubectl` for each machine
install `helm` for server(control plane)
install `k9s` for workstation
install `tailscale` for server

## k3s

on server machine

```sh
curl -sfL https://get.k3s.io | sh -
sudo cat /var/lib/rancher/k3s/server/node-token
mkdir -p ~/.kube/
sudo cp -i /etc/rancher/k3s/k3s.yaml ~/.kube/config
sudo chown $(id -u):$(id -g) ~/.kube/config

kubectl get nodes
```

on workstation, copy `~/.kube/config` from server and fix server IP address

on agent machine

```sh
export K3S_TOKEN=(get token from server)
export SERVER_IP=(server ip address)
curl -sfL https://get.k3s.io | K3S_URL=https://$SERVER_IP:6443 K3S_TOKEN=$K3S_TOKEN sh -
```

`kubectl get nodes` to check if agent attached

## Rancher console

<https://ranchermanager.docs.rancher.com/v2.6/getting-started/quick-start-guides/deploy-rancher-manager/helm-cli>

Then access <https://$AGENT_MACHINE_IP.sslip.io/dashboard/home>

## Tailscale Funnel

<https://tailscale.com/kb/1223/funnel>

```sh
tailscale funnel (PortNumber)
```

## Usage

deploy k8s resource with kubectl
view and edit on Rancher web console
...
