<img src="https://github.com/cncf/artwork/raw/master/projects/prometheus/icon/color/prometheus-icon-color.svg?sanitize=true"
    alt="cert-manager logo"
    align="right" height="128"/>


`prometheus-operator`
=====================
**Prometheus**, a [CNCF](https://cncf.io/) project, is a systems and service monitoring system. It collects metrics from configured targets at given intervals, evaluates rule expressions, displays the results, and can trigger alerts if some condition is observed to be true.

**Prometheus Operator** creates/configures/manages Prometheus clusters atop Kubernetes

## 1. Architecture
![Prometheus Architecture](https://prometheus.io/assets/architecture.png)
* [ref](https://prometheus.io/docs/introduction/overview/#architecture)

## 2. Deployment
### 2.1 Info
* Kubernetes: v1.13+
* Helm: v2.x
* Prometheus: v2.12
* Prometheus Operator: v0.32
  + Helm chart: v6.11

### 2.2 Components
