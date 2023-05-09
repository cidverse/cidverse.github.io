# github-sarif-upload

Uploads the SARIF file to GitHub CodeScanning.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `hasPrefix(ENV["NCI_REPOSITORY_REMOTE"], "https://github.com/")`

## Configuration

| Property | Description |
|---|---|
| `GITHUB_TOKEN` | The GitHub token to use for uploading the SARIF file. |

