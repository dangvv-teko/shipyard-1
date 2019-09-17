<img src="https://github.com/grafana/grafana/raw/master/public/img/grafana_icon.svg?sanitize=true"
    alt="grafana logo"
    align="right" height="128"/>

`grafana`
=========
**Grafana** is an open-source, general purpose analytics and monitoring platform. It supports [InfluxDB](https://www.influxdata.com/), [Prometheus](https://prometheus.io/), [AWS CloudWatch](https://aws.amazon.com/cloudwatch/), [GCP Stackdriver](https://cloud.google.com/stackdriver/)... as datasources, with variety of dashboard panels.

## 1. Deployment
### 1.1. Info
* Kubernetes: v1.13+
* Helm: v2.x
* Grafana: v6.3
  + Helm chart: v6.3

### 1.2 Installation
```bash
helm install stable/grafana \
  --name grafana \
  --namespace kube-monitor \
  --values values.yaml
## or ##
helm upgrade grafana stable/grafana \
  --values values.yaml
```

## 2. Well-known dashboards
* [`kubernetes-mixin`](https://github.com/kubernetes-monitoring/kubernetes-mixin/)
* [NGINX Ingress controller](https://grafana.com/grafana/dashboards/9614) | [source](https://github.com/kubernetes/ingress-nginx/tree/master/deploy/grafana/dashboards)
