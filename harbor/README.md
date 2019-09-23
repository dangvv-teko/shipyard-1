<img src="https://github.com/cncf/artwork/raw/master/projects/harbor/icon/color/harbor-icon-color.svg?sanitize=true"
    alt="harbor logo"
    align="right" height="128"/>

`harbor`
========
**Harbor** is an open-source cloud-native container registry that stores, signs, and scans container images for vulnerabilities

## 1. Architeccture
![Harbor Architecture](/harbor/res/harbor-architecture.png)

[ref](https://youtu.be/hG1YSlfVTqY)

## 2. Deployment
### 2.1. Info
* Kubernetes: v1.14+
* Helm: v2.x
* Harbor: v1.9
  + Helm chart: v1.2

### 2.2 Installation
```bash
helm repo add harbor https://helm.goharbor.io
helm repo update

helm install harbor/harbor \
  --name=pearl \
  --namespace=harbor-registry \
  --values=values.yaml
## or ##
helm upgrade pearl harbor/harbor \
  --values=values.yaml
```

### 2.3 Post-Installation

ref: [User Guide](https://github.com/goharbor/harbor/blob/master/docs/user_guide.md)

#### 2.3.1. Setup Authentication
* Using LDAP
![Harbor LDAP](https://github.com/goharbor/harbor/raw/master/docs/img/ldap_auth.png)

* Using OIDC
![Harbor OIDC](https://github.com/goharbor/harbor/raw/master/docs/img/oidc_auth_setting.png)

    Docker/Helm login using CLI secret
    ![OIDC CLI secret](https://github.com/goharbor/harbor/raw/master/docs/img/profile_dlg.png)

#### 2.3.2. Setup Email
![Harbor email setting](https://github.com/goharbor/harbor/raw/master/docs/img/new_config_email.png)

#### 2.3.3. Project Quota
* Set default Project Quotas

    Go to Configuration > Project Quotas.

    ![Default Project Quotas](https://github.com/goharbor/harbor/raw/master/docs/img/project-quota2.png)

    * Default artifact count per project: 2048
    * Default disk space per project:     256 GB

* Set Project Quotas for existed projects

    ![Project Quotas](https://github.com/goharbor/harbor/raw/master/docs/img/project-quota4.png)

#### 2.3.4. Tag Retention
For each projects, define tag retention like:
//TODO
