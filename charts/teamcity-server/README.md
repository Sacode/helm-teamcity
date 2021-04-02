# TeamCity server Helm chart

This helm chart installs [TeamCity](https://www.jetbrains.com/teamcity/) server.

## Configuration

Please change the values.yaml according to your setup

|         Parameter         |           Description             |                         Default                          |
|---------------------------|-----------------------------------|----------------------------------------------------------|
| `serviceAccount.create` | Specifies whether a ServiceAccount should be created | `true` |
| `serviceAccount.name` | The name of the ServiceAccount to create             | Generated using the fullname template |
| `rbac.create` | Specifies whether RBAC resources should be created   | `false` |
| `rbac.role.rules` | Rules to create                                      | `[]` |
| `replicaCount` | Replica count for TeamCity server deployment        | `1` |
| `image.pullPolicy` | Container pull policy                               | `IfNotPresent` |
| `image.repository` | Container image                                     | `jetbrains/teamcity-server` |
| `image.tag` | Container tag                                       | `2020.2.3` |
| `resources.limits.cpu` | TeamCity cpu limit                          | `800m` |
| `resources.limits.memory` | TeamCity memory limit                       | `968Mi` |
| `resources.requests.cpu` | TeamCity initial cpu request                | `600m` |
| `resources.requests.memory` | TeamCity initial memory request             | `968Mi` |
| `livenessProbe.enabled` | Enable liveness probe                     | `true` |
| `readinessProbe.enabled` | would you like a readinessProbe to be enabled | `true` |
| `service.type` | TeamCity service type                      | `ClusterIP` |
| `service.loadBalancerIP` | TeamCity service load balancer IP address  | ``                            |
| `service.port` | TeamCity service external port             | `8111` |
| `service.annotations` | TeamCity service annotations               | `{}` |
| `ingress.enabled` | If true, TeamCity Ingress will be created  | `false` |
| `ingress.annotations` | TeamCity Ingress annotations               | `{}` |
| `ingress.hosts` | TeamCity Ingress hostnames                 | `[]` |
| `ingress.tls` | TeamCity Ingress TLS configuration (YAML)  | `[]` |

## How to

``` bash
helm install --name teamcity ./helm-teamcity
```

## Author

Dmitriy Safonov <dmitriy@safonov.name>
