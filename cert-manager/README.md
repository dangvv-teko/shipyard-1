<img src="https://github.com/jetstack/cert-manager/raw/master/logo/logo.svg?sanitize=true"
    alt="cert-manager logo"
    align="right" height="128"/>

cert-manager
============
`cert-manager` is a native Kubernetes certificate management controller. It can help with issuing certificates from a variety of sources, such as [Let’s Encrypt](https://letsencrypt.org/), [HashiCorp Vault](https://vaultproject.io/), [Venafi](https://venafi.com/), a simple signing keypair, or self signed.

## 1. Info
* Kubernetes: v1.13+
* Helm: v2.x
* cert-manager: v0.10
  + Helm release: v0.10+

## 2. Deployment
```bash
# Install the CustomResourceDefinition resources separately
kubectl apply -f https://raw.githubusercontent.com/jetstack/cert-manager/release-0.10/deploy/manifests/00-crds.yaml

# Create the namespace for cert-manager
kubectl apply -f https://raw.githubusercontent.com/jetstack/cert-manager/release-0.10/deploy/manifests/01-namespace.yaml

# Add the Jetstack Helm repository
helm repo add jetstack https://charts.jetstack.io
helm repo update

# Install the cert-manager Helm chart
helm install \
  --name cert-manager \
  --namespace cert-manager \
  --version v0.10.0 \
  --values values.yaml \
  jetstack/cert-manager
## or ##
helm update cert-manager jetstack/cert-manager \
  --values values.yaml
```

[ref](https://docs.cert-manager.io/en/latest/getting-started/install/kubernetes.html#steps)

## 3. Usage
### 3.1 Create Issuer
```bash
kubectl apply -f issuers/letsencrypt-issuer.yaml
```

ref: [Supported issuer types](https://docs.cert-manager.io/en/latest/tasks/issuers/index.html#supported-issuer-types)

### 3.2 Issuing Certificates
Certificates can be issued *manually* via `Certificate` resource ([example](examples/certificate.yaml)) or *automatically* for `Ingress` resources ([example](examples/ingress.yaml))

## 4. References
* Repo: https://github.com/jetstack/cert-manager
* Docs: https://docs.cert-manager.io
