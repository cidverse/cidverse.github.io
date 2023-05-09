# helm-publish-registry

Publishes the helm chart into a OCI registry.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `MODULE_BUILD_SYSTEM == "helm" && ENV["HELM_OCI_REPOSITORY"] != ""`

## Configuration

| Property | Description |
|---|---|
| `HELM_OCI_REPOSITORY` | The url of the OCI registry for the chart publication. |

