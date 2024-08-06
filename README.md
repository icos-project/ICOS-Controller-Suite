# ICOS Controller

![Version: 2.0.0](https://img.shields.io/badge/Version-2.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2.0.0](https://img.shields.io/badge/AppVersion-2.0.0-informational?style=flat-square)

A Helm chart for the ICOS Controller

The ICOS Controller is responsible for managing the continuum (keeping track of the topology and availability of the current system) and the run-time (launching and monitoring the execution of services on-demand). Each ICOS Controller manages a set of Agents based on a proximity criteria; hence, ICOS Controllers are deployed on resource-rich computing facilities along the continuum to cover the whole geographical area.

This repository contains all the necessary information to install and deploy the ICOS Controller in a Kubernetes cluster.

## Requirements

| Repository | Name | Version |
|------------|------|---------|
|  | intelligence-coordination | 0.1.0 |
|  | job-manager | 0.1.0 |
|  | security-coordination-module | 0.1.0 |
|  | security-lomos-api2 | 0.1.0 |
|  | shell-backend | 0.1.0 |
| oci://harbor.res.eng.it/icos/helm | aggregator | 1.2.5 |
| oci://harbor.res.eng.it/icos/helm | dataclay | 0.1.5 |
| oci://harbor.res.eng.it/icos/helm | dynamic-policy-manager | 0.2.0 |
| oci://harbor.res.eng.it/icos/helm | matchmaker | 0.1.0 |
| oci://harbor.res.eng.it/icos/helm | telemetruum-gateway | 0.1.0 |
| oci://harbor.res.eng.it/icos/helm | telemetruum-hub | 0.4.0 |
| oci://harbor.res.eng.it/icos/helm | telemetruum-leaf | 0.9.0 |
| oci://registry-1.docker.io/bitnamicharts | job-manager-backend(mysql) | 9.14.3 |

The minimum hardware requirements are a compatible host with Kubernetes installed, 2 GB of RAM and 2 CPU cores per machine as well as 40GB of storage. The installation furthermore requires full IP network connectivity between all machines that are part of the cluster (public or private network). For details on how to reach the required state of an installed Kubernetes distribution, the user can refer to the [Kubernetes documentation](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/).

## Install Chart
This creates the release and instantiates all the Kubernetes components associated with the ICOS Controller.
```console
helm install [RELEASE_NAME] icos-controller
```

_See [values](#Values) below._

_See [helm install](https://helm.sh/docs/helm/helm_install/) for command documentation._

## Values

### Main

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| global.external.host | string | `"external-name.com"` | the public hostname or ip of this controller |
| global.icos.controllerId | string | `"my-controller"` | the id of this controller |
| global.icos.iam.baseUrl | string | `"https://replace-with-keycloak-url"` | endpoint of the IAM service |
| global.icos.iam.publicKey | string | `"replace-with-realm-public-key"` | public key of the IAM service |
| global.icos.iam.realm | string | `"icos-realm"` | realm of the IAM service |
| global.icos.lighthouse.baseUrl | string | `"http://replace-with-light-house-url"` | endponint of the Lighthouse |

### DPM

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| global.icos.dpm.iamClientId | string | `"replace"` | IAM client id for the Dynamic Policy Manager service |
| global.icos.dpm.iamClientSecret | string | `"replace"` | IAM client secret for the Dynamic Policy Manager service |

### Matchmaker

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| global.icos.matchmaker.iamClientId | string | `"replace"` | IAM client id for the Matchmaker service |
| global.icos.matchmaker.iamClientSecret | string | `"replace"` | IAM client secret for the Matchmaker service |

### Shell

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| global.icos.shellBackend.iamClientId | string | `"replace"` | IAM client id for the Shell Backend service |
| global.icos.shellBackend.iamClientSecret | string | `"replace"` | IAM client secret for the Shell Backend service |
| global.icos.shellBackend.iamPassword | string | `"password-for-registartion-at-lighthouse"` | IAM password for the Shell Backend service |
| global.icos.shellBackend.iamUser | string | `"user-for-registration-at-lightouse"` | IAM username for the Shell Backend service |

### Telemetry

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| global.icos.telemetry.iamGrafanaClientId | string | `"replace"` | IAM client id for the Grafana service |
| global.icos.telemetry.iamGrafanaClientSecret | string | `"replace"` | IAM client secret for the Grafana service |

## Uninstall Chart
This removes all the Kubernetes components associated with the ICOS Controller and deletes the release.
```console
helm uninstall [RELEASE_NAME]
```
_See [helm uninstall](https://helm.sh/docs/helm/helm_uninstall/) for command documentation._

# Legal
The ICOS controller is released under the Apache 2.0 license.
Copyright © 2022-2024 ICOS. All rights reserved.

🇪🇺 This work has received funding from the European Union's HORIZON research and innovation programme under grant agreement No. 101070177.