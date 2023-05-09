# github-release-publish

Publishes a new release on GitHub, including the release notes and artifacts.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `NCI_COMMIT_REF_TYPE == "tag" && hasPrefix(ENV["NCI_REPOSITORY_REMOTE"], "https://github.com/")`

## Configuration

| Property | Description |
|---|---|
| `GITHUB_TOKEN`* | The GitHub token to use for creating the release. |

