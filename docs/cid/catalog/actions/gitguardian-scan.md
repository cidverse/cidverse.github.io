# gitguardian-scan

Scans the repository for secrets using GitGuardian.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `ENV["GITGUARDIAN_API_KEY"] != "" && NCI_COMMIT_REF_TYPE == "branch"`

## Configuration

| Property | Description |
|---|---|
| `GITGUARDIAN_.*` | The GitGuardian API key and other properties to use for scanning. |

