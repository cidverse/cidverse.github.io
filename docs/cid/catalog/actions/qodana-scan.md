# qodana-scan

Scans the repository for security issues using JetBrains Qodana.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `ENV["QODANA_TOKEN"] != "" && NCI_COMMIT_REF_TYPE == "branch"`

## Configuration

| Property | Description |
|---|---|
| `QODANA_TOKEN` | The Qodana authentication token. |
| `NCI_REPOSITORY_.*` | The project properties sonar needs to identify the repository. |
| `NCI_COMMIT_.*` | The commit properties sonar needs to identify the revision. |

