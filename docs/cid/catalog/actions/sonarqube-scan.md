# sonarqube-scan

Scans the repository for security issues using SonarQube.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `ENV["SONAR_TOKEN"] != "" && NCI_COMMIT_REF_TYPE == "branch"`

## Configuration

| Property | Description |
|---|---|
| `SONAR_.*` | The SonarQube authentication properties to use for scanning. |
| `NCI_PROJECT_.*` | The project properties sonar needs to identify the repository. |
| `NCI_COMMIT_.*` | The commit properties sonar needs to identify the revision. |

