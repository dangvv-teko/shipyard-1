<img src="https://static-www.elastic.co/v3/assets/bltefdd0b53724fa2ce/blt8781708f8f37ed16/5c11ec2edf09df047814db23/logo-elastic-kibana-lt.svg"
    alt="kibana logo"
    align="right" height="80"/>

`kibana`
========
**Kibana** is your window into the [Elastic Stack](https://elastic.co/products/). Specifically, it's a browser-based analytics and search dashboard for Elasticsearch.

## 1. Deployment
### 1.1. Info
* Kubernetes: v1.13+
* Helm: v2.x
* Kibana: v6.x, v7.x
  + Helm chart: v6.x, v7.x

### 1.2 Installation
```bash
helm repo add elastic https://helm.elastic.co
helm repo update

helm install elastic/kibana \
  --name=tivan-kibana \
  --namespace=kube-observability \
  --values=values.yaml
## or ##
helm upgrade tivan-kibana elastic/kibana \
  --values=values.yaml
```

### 1.3 Post-installation

* Setup roles
```
ROLE     logs_system
  Elasticsearch
    Cluster privileges:
    Run As privileges:
    Index privileges:
        kubernetes_cluster-* :  create_index, write

ROLE     logs_user
  Elasticsearch
    Cluster privileges: monitor
    Run As privileges:
    Index privileges:
        kubernetes_cluster-* :  read, monitor, view_index_metadata
  Kibana
    Discover:   Read
    Visualize:  Read
    Dashboard:  Read
    Dev Tools:  Read
```

* Setup users
```
USER     fluentbit
PASSWORD secure-password-for-fluetbit
ROLE     logs_system
```
