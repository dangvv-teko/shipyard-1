<img src="https://istio.io/img/istio-bluelogo-whitebackground-unframed.svg"
    alt="istio logo"
    align="right" height="128"/>

`istio`
=======
**Istio** is an open *Service Mesh* platform to Connect, secure, control, and observe services.

## 1. Architecture
![Istio Architecture](https://istio.io/docs/concepts/what-is-istio/arch.svg)
* [ref](https://istio.io/docs/concepts/what-is-istio/#architecture)

## 2. Deployment
### 2.1 Info
* Kubernetes: v1.13+
* Helm: v2.x
* Istio: 1.3

### 2.2 Components
<table>
  <tr>
    <th>Components</th>
    <th align="center">Installed</th>
    <th>Helm path</th>
    <th>Operator path</th>
  </tr>
  <tr>
    <td><b>Core components</b></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><code>istio-citadel</code></td>
    <td align="center">✓<br></td>
    <td><code>security</code></td>
    <td><code>security/citadel</code></td>
  </tr>
  <tr>
    <td><code>istio-galley</code></td>
    <td align="center">✓</td>
    <td><code>galley</code></td>
    <td><code>istio-control/istio-config</code></td>
  </tr>
  <tr>
    <td><code>istio-pilot</code></td>
    <td align="center">✓</td>
    <td><code>pilot</code></td>
    <td><code>istio-control/istio-discovery</code></td>
  </tr>
  <tr>
    <td>
        <code>istio-policy</code>
        <small>(apart of mixer)</small>
    </td>
    <td align="center">✓</td>
    <td><code>mixer</code></td>
    <td><code>istio-policy</code></td>
  </tr>
  <tr>
    <td>
        <code>istio-telemetry</code>
        <small>(apart of mixer)</small>
    </td>
    <td align="center">✓</td>
    <td><code>mixer</code></td>
    <td><code>istio-telemetry/mixer-telemetry</code></td>
  </tr>
  <tr>
    <td><code>istio-sidecar-injector</code></td>
    <td align="center">✓</td>
    <td><code>sidecarInjectorWebhook</code></td>
    <td><code>istio-control/istio-autoinject</code></td>
  </tr>
  <tr>
    <td><code>istio-nodeagent</code></td>
    <td align="center">?</td>
    <td><code>nodeagent</code></td>
    <td><code>security/nodeagent</code></td>
  </tr>
  <tr>
    <td><code>istio-ingressgateway</code></td>
    <td align="center">✓</td>
    <td><code>gateways</code></td>
    <td><code>gateways/istio-ingress</code></td>
  </tr>
  <tr>
    <td><code>istio-egressgateway</code></td>
    <td align="center">?</td>
    <td><code>gateways</code></td>
    <td><code>gateways/istio-egress</code></td>
  </tr>
  <tr>
    <td><b>Addons</b></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><code>kiali</code></td>
    <td align="center">✗</td>
    <td><code>kiali</code></td>
    <td><code>istio-telemetry/kiali</code></td>
  </tr>
  <tr>
    <td><code>cert-manager</code></td>
    <td align="center">✗</td>
    <td><code>certmanager</code></td>
    <td><code>security/certmanager</code></td>
  </tr>
  <tr>
    <td><code>prometheus</code></td>
    <td align="center">✗</td>
    <td><code>prometheus</code></td>
    <td>
        <code>istio-telemetry/prometheus</code>
        </br>
        <code>istio-telemetry/prometheus-operator</code>
    </td>
  </tr>
  <tr>
    <td><code>grafana</code></td>
    <td align="center">✗</td>
    <td><code>grafana</code></td>
    <td><code>istio-telemetry/grafana</code></td>
  </tr>
  <tr>
    <td>
        tracing (supported providers)
        <ul>
            <li><code>jaeger</code></li>
            <li><code>zipkin</code></li>
            <li><code>opencensus</code></li>
        </ul>
    </td>
    <td align="center">✗</td>
    <td><code>tracing</code></td>
    <td><code>istio-telemetry/tracing</code></td>
  </tr>
  <tr>
    <td><code>istio-cni</code></td>
    <td align="center">?</td>
    <td>// separated chart </td>
    <td><code>istio-cni</code></td>
  </tr>
  <tr>
    <td><code>istio-coredns</code></td>
    <td align="center">?</td>
    <td><code>istiocoredns</code></td>
    <td><code>istiocoredns</code></td>
  </tr>
</table>
