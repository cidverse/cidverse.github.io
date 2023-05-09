# helm-publish-nexus

Publishes the helm chart into a nexus repository server.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `MODULE_BUILD_SYSTEM == "helm" && ENV["HELM_NEXUS_URL"] != ""`

## Configuration

| Property | Description |
|---|---|
| `HELM_NEXUS_URL` | The url of the nexus server. |
| `HELM_NEXUS_REPOSITORY` | The name of the nexus repository. |
| `HELM_NEXUS_USERNAME` | The username to use for authentication. |
| `HELM_NEXUS_PASSWORD` | The password to use for authentication. |

