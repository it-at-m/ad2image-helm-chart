# ad2image-helm-chart

:construction: This is a work-in-progress :construction:

## Introduction

This chart bootstraps a [ad2image](https://github.com/itatm/ad2image) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

This documentation is rendered from the `main` branch.

## Add Helm repo

```bash
helm repo add ad2image https://itatm.github.io/ad2image-helm-chart
```

## Installing the Chart

Install this chart using:

```bash
helm install ad2image ad2image --values values.yaml
```

The command deploys ad2image on the Kubernetes cluster in the default configuration. The [values](#values) section lists the parameters that can or **must** be configured during installation.

## Values

| Key                                         | Type   | Default                                               | Description                                                                     |
| ------------------------------------------- | ------ | ----------------------------------------------------- | ------------------------------------------------------------------------------- |
| image.imagePullSecrets                      | list   | `[]`                                                  | Image pull secrets specification                                                |
| image.pullPolicy                            | string | `"IfNotPresent"`                                      | Image pull policy                                                               |
| image.repository                            | string | `"docker.io/itatm/ad2image"`                          | Image to use for deploying                                                      |
| image.tag                                   | string | `""`                                                  | Image tag                                                                       |
| ingress.annotations                         | object | `{}`                                                  |                                                                                 |
| ingress.className                           | string | `""`                                                  |                                                                                 |
| ingress.enabled                             | bool   | `false`                                               | Enable ingress                                                                  |
| ingress.hosts                               | list   | `[]`                                                  |                                                                                 |
| ingress.tls                                 | list   | `[]`                                                  |                                                                                 |
| nameOverride                                | string | `""`                                                  | Override chart name                                                             |
| podSecurityContext                          | object | `{"fsGroup":1000,"runAsGroup":1000,"runAsUser":1000}` | Security Context                                                                |
| registriesCredentials                       | object | `{"existingSecret":""}`                               | Credentials for private registries Example: PRIVATE_DOCKERHUB_TOKEN: token      |
| registriesCredentials.existingSecret        | string | `""`                                                  | set a secret name here if you want to manage registries credentials on your own |
| service.annotations                         | object | `{}`                                                  | Service annotations                                                             |
| service.port                                | int    | `3000`                                                | Service pot                                                                     |
| service.type                                | string | `"ClusterIP"`                                         | Service type                                                                    |
| serviceAccount.annotations                  | object | `{}`                                                  | Service account annotations                                                     |
| serviceAccount.automountServiceAccountToken | bool   | `true`                                                | Automount service account token                                                 |
| serviceAccount.create                       | bool   | `true`                                                | Create service account                                                          |
| serviceAccount.name                         | string | `""`                                                  | Service account name                                                            |
