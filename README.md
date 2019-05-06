TEAMCITY SERVER
===============


This helm chart installs TeamCity server version 2018.1.5
https://www.jetbrains.com/teamcity/

### Configuration
Please change the values.yaml according to your setup

Parameter | Description | Default | Required
--- | --- | --- | ---
`serviceAccount.create` | Whether to create a service account or not | true | no
`serviceAccount.name` | The name of the service account  | `nil` | no

Parameter | Description | Default
--- | --- | ---
`rbac.create` | If true, create and use RBAC resources | `true`
`rbac.role.rules` | A list of rules to create | `[]`
`image.repository` | Image repository | `jetbrains/teamcity-server`
`image.pullPolicy` | Image pull policy | `IfNotPresent`


## How to
```
helm install --name teamcity ./helm-teamcity
```
