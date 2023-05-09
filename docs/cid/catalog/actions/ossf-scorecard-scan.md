# ossf-scorecard-scan

Scorecard is an automated tool that assesses a number of important heuristics ("checks") associated with software security and assigns each check a score of 0-10.
You can use these scores to understand specific areas to improve in order to strengthen the security posture of your project.

This action will evaluate your project using the scorecard tool and store the result as sarif report.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `NCI_REPOSITORY_HOST_TYPE == "github"`

## Configuration

| Property | Description |
|---|---|
| `GITHUB_TOKEN` | The GitHub token to use when querying project information from the GitHub API. |

