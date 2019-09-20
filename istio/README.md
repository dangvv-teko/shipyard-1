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
    <th>Feature</th>
    <th>Components</th>
    <th align="center">Installed</th>
    <th>Helm path</th>
    <th>Operator path</th>
  </tr>
  <tr>
    <td>Base</td>
    <td>CRDs</td>
    <td align="center">✓<br></td>
    <td>// separated chart</br><code>istio-init</code></td>
    <td><code>crds</code></td>
  </tr>
  <tr>
    <td colspan="2" align="center"><b>Core components</b></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Security</td>
    <td><code>istio-citadel</code></td>
    <td align="center">✓<br></td>
    <td><code>security</code></td>
    <td><code>security/citadel</code></td>
  </tr>
  <tr>
    <td width="128">Configuration Management</td>
    <td><code>istio-galley</code></td>
    <td align="center">✓</td>
    <td><code>galley</code></td>
    <td><code>istio-control/istio-config</code></td>
  </tr>
  <tr>
    <td width="128">Traffic Management</td>
    <td><code>istio-pilot</code></td>
    <td align="center">✓</td>
    <td><code>pilot</code></td>
    <td><code>istio-control/istio-discovery</code></td>
  </tr>
  <tr>
    <td>Policy</td>
    <td>
        <code>istio-policy</code>
        </br>
        <sup> (apart of mixer)</sup>
    </td>
    <td align="center">✓</td>
    <td><code>mixer</code></td>
    <td><code>istio-policy</code></td>
  </tr>
  <tr>
    <td>Telemetry</td>
    <td>
        <code>istio-telemetry</code>
        </br>
        <sup> (apart of mixer)</sup>
    </td>
    <td align="center">✓</td>
    <td><code>mixer</code></td>
    <td><code>istio-telemetry/mixer-telemetry</code></td>
  </tr>
  <tr>
    <td>AutoInjection</td>
    <td><code>istio-sidecar-injector</code></td>
    <td align="center">✓</td>
    <td><code>sidecarInjectorWebhook</code></td>
    <td><code>istio-control/istio-autoinject</code></td>
  </tr>
  <tr>
    <td>Security</td>
    <td><code>istio-nodeagent</code></td>
    <td align="center">?</td>
    <td><code>nodeagent</code></td>
    <td><code>security/nodeagent</code></td>
  </tr>
  <tr>
    <td>Gateways</td>
    <td><code>istio-ingressgateway</code></td>
    <td align="center">✓</td>
    <td><code>gateways</code></td>
    <td><code>gateways/istio-ingress</code></td>
  </tr>
  <tr>
    <td>Gateways</td>
    <td><code>istio-egressgateway</code></td>
    <td align="center">?</td>
    <td><code>gateways</code></td>
    <td><code>gateways/istio-egress</code></td>
  </tr>
  <tr>
    <td>Gateways</td>
    <td>
        <code>istio-ilbgateway</code>
        </br>
        <sup> (Mesh InternalLoadBalancer gateway)</sup>
    </td>
    <td align="center">?</td>
    <td><code>gateways</code></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2" align="center"><b>Addons</b></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Telemetry</td>
    <td><code>kiali</code></td>
    <td align="center">✗</td>
    <td><code>kiali</code></td>
    <td><code>istio-telemetry/kiali</code></td>
  </tr>
  <tr>
    <td>Security</td>
    <td><code>cert-manager</code></td>
    <td align="center">✗</td>
    <td><code>certmanager</code></td>
    <td><code>security/certmanager</code></td>
  </tr>
  <tr>
    <td>Telemetry</td>
    <td><code>prometheus</code></td>
    <td align="center">✗</td>
    <td><code>prometheus</code></td>
    <td>
      * <code>istio-telemetry/prometheus</code>
      </br>
      * <code>istio-telemetry/prometheus-operator</code>
    </td>
  </tr>
  <tr>
    <td>Telemetry</td>
    <td><code>grafana</code></td>
    <td align="center">✗</td>
    <td><code>grafana</code></td>
    <td><code>istio-telemetry/grafana</code></td>
  </tr>
  <tr>
    <td>Telemetry</td>
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
    <td>3rd Party</td>
    <td><code>istio-cni</code></td>
    <td align="center">?</td>
    <td>// separated chart</br><code>istio-cni</code></td>
    <td><code>istio-cni</code></td>
  </tr>
  <tr>
    <td>3rd Party</td>
    <td><code>istio-coredns</code></td>
    <td align="center">?</td>
    <td><code>istiocoredns</code></td>
    <td><code>istiocoredns</code></td>
  </tr>
</table>

**Referenes**:
* [config-profiles](https://istio.io/docs/setup/additional-setup/config-profiles/)*
* [in-tree Helm charts](https://github.com/istio/istio/tree/1.3.0/install/kubernetes/helm)
* [istio/installer](https://github.com/istio/installer/tree/release-1.3)
* [istio-operator Architecture](https://github.com/istio/operator/blob/master/ARCHITECTURE.md)*

**Note**: The following components are install in seperated releases:
* `kiali`
* `cert-manager`
* `prometheus`
* `grafana`
* `jaeger`

### 2.3 Installation methods
Istio support multiple install methods:
* [Quick Start Evaluation Install](https://istio.io/docs/setup/install/kubernetes/) using pre-generated kubernetes manifest files
* [Customizable Install with Helm](https://istio.io/docs/setup/install/helm/)
  * Option 1: using `helm template` to generate manifests then `kubectl apply`
  * Option 2: Install with Helm and Tiller via `helm install`
* The [Istio Operator](https://istio.io/docs/setup/install/operator/) offers a new method of installing Istio using a one-line command.
  * Option 1: Using `istioctl experimental manifest apply`
  * Option 2: Using CRD `install.istio.io/IstioControlPlane`

### 2.4 Installation
```bash
helm repo add istio.io https://storage.googleapis.com/istio-release/releases/1.3.0/charts/
helm repo update

# Install CRDs
kubectl apply -f https://github.com/istio/istio/raw/1.3.0/install/kubernetes/helm/istio-init/files/crd-10.yaml
kubectl apply -f https://github.com/istio/istio/raw/1.3.0/install/kubernetes/helm/istio-init/files/crd-11.yaml
kubectl apply -f https://github.com/istio/istio/raw/1.3.0/install/kubernetes/helm/istio-init/files/crd-12.yaml

# Create istio-system namespace
kubectl apply -f https://github.com/istio/istio/raw/1.3.0/install/kubernetes/namespace.yaml

# Install Istio ControlPlan
helm install istio.io/istio \
    --name=istio \
    --namespace=istio-system \
    --values=values.yaml
```
