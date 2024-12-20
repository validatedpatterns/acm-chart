# acm

![Version: 0.1.5](https://img.shields.io/badge/Version-0.1.5-informational?style=flat-square)

A Helm chart to configure Advanced Cluster Manager for OpenShift.

This chart is used by the Validated Patterns to configure ACM and manage remote clusters

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| acm.mce_operator | object | Uses the official redhat sources | Just used for IIB testing, drives the source and channel for the MCE subscription triggered by ACM |
| clusterGroup | object | depends on the individual settings | Dictionary of all the clustergroups of the pattern |
| clusterGroup.managedClusterGroups | object | `{}` | The set of cluters managed by ACM which is running inside this clusterGroup |
| clusterGroup.subscriptions | object | `{"acm":{"source":"redhat-operators"}}` | Dictionary of subscriptions for this specific clusterGroup |
| clusterGroup.subscriptions.acm | object | `{"source":"redhat-operators"}` | Name of the subscription |
| clusterGroup.subscriptions.acm.source | string | `"redhat-operators"` | The catalog source for this subscription |
| global.extraValueFiles | list | `[]` | List of additional value files to be passed to the pattern |
| global.options.applicationRetryLimit | int | `20` |  |
| global.pattern | string | `"none"` |  |
| global.repoURL | string | `"none"` | Repository URL pointing to the pattern |
| global.secretStore.backend | string | `"vault"` |  |
| global.targetRevision | string | `"main"` | The branch or Git reference to use to deploy the pattern |
| main.gitops.channel | string | `"gitops-1.15"` | Default gitops channel to install on remote clusters |
| secretStore | object | depends on the individual settings | Default secretstore configuration variables |
| secretStore.name | string | `"vault-backend"` | Name of the clustersecretstore to be used for secrets |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)

