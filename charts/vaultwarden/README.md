# vaultwarden

A Helm chart for deploying Vaultwarden to Kubernetes

## Source Code

* <https://github.com/dani-garcia/vaultwarden>
* <https://github.com/sebastiangaiser/helm-charts/>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| additionalVolumeMounts | list | `[]` | Additional volume mounts |
| additionalVolumes | object | `{}` | Additional volumes |
| affinity | object | `{}` | Affinities |
| cnpg.enabled | bool | `false` |  |
| deploymentStrategy.type | string | `"Recreate"` |  |
| fullnameOverride | string | `""` |  |
| horizontalAutoscaling | object | `{"enabled":false,"maxReplicas":3,"minReplicas":1,"targetCPUUtilizationPercentage":75,"targetMemoryUtilizationPercentage":75}` | HPA configuration |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"ghcr.io/dani-garcia/vaultwarden"` |  |
| imagePullSecrets | list | `[]` |  |
| ingress | object | `{"annotations":{},"className":"","enabled":false,"hosts":[{"host":"vaultwarden.example.com","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | Ingress |
| initContainers | object | `{}` | Init-containers |
| livenessProbe | object | `{"httpGet":{"path":"/api/alive","port":"http"}}` | Liveness probe |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` | Node selectors |
| persistence | object | `{"accessMode":"ReadWriteOnce","enabled":false,"size":"1Gi"}` | Persistent volume |
| podAnnotations | object | `{}` |  |
| podDisruptionBudget | object | `{"enabled":false}` | PodDisruptionBudget configuration |
| podSecurityContext | object | `{}` |  |
| readinessProbe | object | `{"httpGet":{"path":"/api/alive","port":"http"}}` | Readiness probe |
| replicaCount | int | `1` |  |
| resources | object | `{}` | Resources |
| securityContext.capabilities.drop[0] | string | `"ALL"` |  |
| service | object | `{"port":80,"type":"ClusterIP"}` | Service |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| tolerations | list | `[]` | Toleration's |
| vaultwarden | object | `{"adminToken":{"value":"disabled"},"envFromSecrets":[],"environment":"production","extraEnvironmentVars":{},"rocketPort":8080}` | Vaultwarden specific configuration |
| vaultwarden.adminToken.value | string | `"disabled"` | Possible values are 'generated', 'disabled' or any specific value |
| vaultwarden.envFromSecrets | list | `[]` | Additional environment variables from secrets |
| vaultwarden.extraEnvironmentVars | object | `{}` | Additional environment variables |
| verticalAutoscaling | object | `{"enabled":false,"updateMode":"Off"}` | VPA configuration |
| zalandoPostgresql.additionalConfiguration | object | `{}` |  |
| zalandoPostgresql.enabled | bool | `false` |  |
| zalandoPostgresql.instances | int | `1` |  |
| zalandoPostgresql.resources.limits.cpu | string | `"500m"` |  |
| zalandoPostgresql.resources.limits.memory | string | `"500Mi"` |  |
| zalandoPostgresql.resources.requests.cpu | string | `"250m"` |  |
| zalandoPostgresql.resources.requests.memory | string | `"250Mi"` |  |
| zalandoPostgresql.size | string | `"1Gi"` |  |
| zalandoPostgresql.version | string | `"16"` |  |

## Upgrading

A major chart version change indicates that there is an incompatible breaking change and needs manual action.
