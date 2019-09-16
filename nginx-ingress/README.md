<img src="https://raw.githubusercontent.com/nginxinc/kubernetes-ingress/v1.5.5/deployments/helm-chart/chart-icon.png"
    alt="nginx logo"
    align="right" height="128"/>

`nginx-ingress`
===============
**nginx** is a web server which used as a reverse proxy, load balancer, mail proxy and HTTP cache.


## 1. Deployment
### 1.1. Info
* Kubernetes: v1.13+
* Helm: v2.x
* nginx-ingress: v0.25
  + Helm chart: v1.20

### 1.2 Installation
```bash
helm install stable/nginx-ingress \
    --name=tinker \
    --namespace=nginx-ingress \
    --values=values/cloud-generic.yaml
## or ##
helm upgrade tinker stable/nginx-ingress \
    --values=values/cloud-generic.yaml
```
And choose additional values for your environment, e.g: [GCP](values/gcp.yaml) or [BareMetal](values/baremetal.yaml)

### 1.3 Post-installation
* [Grafana Dashboard for Prometheus metrics](https://github.com/kubernetes/ingress-nginx/blob/master/deploy/grafana/dashboards/nginx.json)

## 2. References
* `ingress-nginx` [home](https://kubernetes.github.io/ingress-nginx/) | [repo](https://github.com/kubernetes/ingress-nginx)
* [Installation Guide](https://kubernetes.github.io/ingress-nginx/deploy/)
