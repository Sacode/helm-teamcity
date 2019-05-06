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
`region` | AWS region  | `nil` | only if using AWS
`apitimeout` | Api Timeout  | `nil` | only if using Azure
`credentials` | Credentials  | `nil` | Yes (not required for kube2iam)
`backupSyncPeriod` | How frequently Ark queries the object storage to make sure that the appropriate Backup resources have been created for existing backup files. | `60m` | yes
`gcSyncPeriod` | How frequently Ark queries the object storage to delete backup files that have passed their TTL.  | `60m` | yes
`scheduleSyncPeriod` | How frequently Ark checks its Schedule resource objects to see if a backup needs to be initiated  | `1m` | yes
`restoreOnlyMode` | When RestoreOnly mode is on, functionality for backups, schedules, and expired backup deletion is turned off. Restores are made from existing backup files in object storage.  | `false` | yes

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
