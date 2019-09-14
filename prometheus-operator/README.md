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
The default installation is intended to suit monitoring a kubernetes cluster the chart is deployed onto. It closely matches the kube-prometheus project. With the installation, the chart also includes dashboards and alerts.

<table>
  <tr>
    <th>Components</th>
    <th>Installed</th>
    <th>Note</th>
  </tr>
  <tr>
    <td><code>prometheus-operator</code></td>
    <td align="center">✓</td>
    <td></td>
  </tr>
  <tr>
    <td><code>prometheus</code></td>
    <td align="center">✓</td>
    <td></td>
  </tr>
  <tr>
    <td><code>alertmanager</code></td>
    <td align="center">✓</td>
    <td></td>
  </tr>
  <tr>
    <td><code>node-exporter</code></td>
    <td align="center">✓</td>
    <td></td>
  </tr>
  <tr>
    <td><code>kube-state-metrics</code></td>
    <td align="center">✓</td>
    <td></td>
  </tr>
  <tr>
    <td><code>grafana</code></td>
    <td align="center">✗</td>
    <td>via <code>Grafana Operator</code> instead</td>
  </tr>
  <tr>
    <td>
        <b>ServiceMonitors</b> to scrape internal kubernetes components
        <ul>
            <li><code>kube-apiserver</code></li>
            <li><code>kube-scheduler</code></li>
            <li><code>kube-controller-manager</code></li>
            <li><code>etcd</code></li>
            <li><code>kube-dns</code> / <code>coredns</code></li>
            <li><code>kube-proxy</code></li>
            <li><code>kubelet</code></li>
            </br>
            <li><code>kube-state-metrics</code></li>
            <li><code>node-exporter</code></li>
            </br>
            <li><code>prometheus-operator</code></li>
            <li><code>prometheus</code></li>
            <li><code>alertmanager</code></li>
            <li><code>grafana</code></li>
        </ul>
    </td>
    <td align="center">✓</td>
    <td></td>
  </tr>
  <tr>
    <td>default <b>Grafana Dashboards</b></td>
    <td align="center">✗</td>
    <td>install <a href="https://github.com/helm/charts/tree/master/stable/prometheus-operator/templates/grafana/dashboards-1.14">manually</a></td>
  </tr>
</table>

### 2.2 Installation
```bash
helm install stable/prometheus-operator \
    --name=argus \
    --namespace=kube-monitor \
    --values=values.yaml
### or ###
helm upgrade argus stable/prometheus-operator \
    --values=values.yaml
```
