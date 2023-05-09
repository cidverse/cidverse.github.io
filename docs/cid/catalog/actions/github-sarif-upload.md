# github-sarif-upload

Uploads all SARIF reports to GitHub CodeScanning. Supports merge requests.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `hasPrefix(ENV["NCI_REPOSITORY_REMOTE"], "https://github.com/")`

## Configuration

| Property | Description |
|---|---|
| `GITHUB_TOKEN`* | The GitHub token to use for uploading the SARIF file. |

