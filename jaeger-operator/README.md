<img src="https://github.com/cncf/artwork/raw/master/projects/jaeger/icon/color/jaeger-icon-color.svg?sanitize=true"
    alt="jaeger logo"
    align="right" height="128"/>

`jaeger-operator`
=================
**Jaeger**, inspired by [Dapper](https://research.google.com/pubs/pub36356.html) and [OpenZipkin](https://zipkin.io/), is open source, end-to-end distributed tracing.

The **Jaeger Operator** is an implementation of a Kubernetes Operator that used to install/configure/update Jaeger.

## 1. Architecture
![Jaeger Architecture](https://jaegertracing.io/img/architecture-v1.png)
* [ref](https://jaegertracing.io/docs/architecture/)

## 2. Deployment
### 2.1 Info
* Kubernetes: v1.13+
* Helm: v2.x
* Jaeger: v1.13
* Jaeger Operator: v1.13
  + Helm chart: v2.9

### 2.2 Installation
#### 2.2.1 Install `jaeger-operator`
```bash
helm install stable/jaeger-operator \
    --name=theseus \
    --namespace=kube-tracing \
    --values=values.yaml
### or ###
helm upgrade theseus stable/jaeger-operator \
    --values=values.yaml
```

#### 2.2.2 Install `jaeger`
Jaeger support multiple deployment strategies. The strategy is defined in the custom resource file, and determines the architecture to be used for the Jaeger backend.
* `allInOne` strategy: use example in `jaeger/simplest.yaml`
* `production` strategy: use example in `jaeger/production.yaml`
* `streaming` strategy: //TODO

For more information, see [docs here](https://jaegertracing.io/docs/1.14/deployment/)

## 3. References
* `Jaeger` [home](https://jaegertracing.io) | [repo](https://github.com/jaegertracing/jaeger)
* `jaeger-operator` [repo](https://github.com/jaegertracing/jaeger-operator)
