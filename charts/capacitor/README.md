# capacitor

![Version: 0.2.1](https://img.shields.io/badge/Version-0.2.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v0.4.8](https://img.shields.io/badge/AppVersion-v0.4.8-informational?style=flat-square)

A Helm chart for deploying capacitor, a general purpose UI for FluxCD

## Network policies
Currently only Kubernetes native `NetworkPolicy` is supported.
Check the values how to configure the flavor.

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinities |
| capacitor.readonly | bool | `true` |  |
| capacitor.showEvents | bool | `true` |  |
| capacitor.showPodLogs | bool | `true` |  |
| capacitor.showSecrets | bool | `true` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"ghcr.io/gimlet-io/capacitor"` |  |
| imagePullSecrets | list | `[]` |  |
| ingress | object | `{"annotations":{},"className":"","enabled":false,"hosts":[{"host":"capacitor.example.com","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | Ingress |
| livenessProbe | object | `{}` | Liveness probe |
| nameOverride | string | `""` |  |
| namespaceOverride | string | `""` |  |
| networkPolicy | object | `{"enabled":true,"flavor":"kubernetes"}` | Network Policy |
| networkPolicy.flavor | string | `"kubernetes"` | kubernetes |
| nodeSelector | object | `{}` | Node selectors |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` | Pod security context |
| readinessProbe | object | `{"failureThreshold":3,"httpGet":{"path":"/","port":9000,"scheme":"HTTP"},"initialDelaySeconds":0,"periodSeconds":10,"successThreshold":1,"timeoutSeconds":3}` | Readiness probe |
| replicaCount | int | `1` |  |
| resources | object | `{"requests":{"cpu":"200m","memory":"200Mi"}}` | Resources |
| securityContext | object | `{}` | Security context |
| service | object | `{"annotations":{},"labels":{},"port":9000,"type":"ClusterIP"}` | Service |
| serviceAccount | object | `{"annotations":{},"create":true}` | ServiceAccount |
| tolerations | list | `[]` | Toleration's |

## Upgrading

A major chart version change indicates that there is an incompatible breaking change and needs manual action.
