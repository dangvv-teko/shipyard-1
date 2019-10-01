<img src="https://www.treasuredata.com/wp-content/uploads/2016/10/fluent-bit-01.svg"
    alt="fluent-bit logo"
    align="right" height="128"/>

`fluent-bit`
============
**Fluent Bit** is an open source and multi-platform Log Processor and Forwarder which allows you to collect data/logs from different sources, unify and send them to multiple destinations. It's fully compatible with Docker and Kubernetes environments.

## 1. Architeccture
![Fluent Bit](https://fluentbit.io/assets/img-flb/flb_002.png)


Fluent Bit Workflow:
![Fluent Bit Workflow](/fluentbit/res/workflow.png)

## 2. Deployment
### 2.1. Info
* Kubernetes: v1.13+
* Helm: v2.x
* Fluent Bit: v1.2
  + Helm chart: v2.7

### 2.2 Installation
```bash
helm install stable/fluent-bit \
  --name=tivan-fluentbit \
  --namespace=kube-observability \
  --values=values.yaml
## or ##
helm upgrade tivan-fluentbit stable/fluent-bit \
  --values=values.yaml
```
