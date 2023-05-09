# gitlab-release-publish

Publishes a new release on GitLab, including the release notes and artifacts.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `NCI_COMMIT_REF_TYPE == "tag" && hasPrefix(ENV["NCI_REPOSITORY_REMOTE"], "https://gitlab.com/")`

## Configuration

| Property | Description |
|---|---|
| `GITLAB_TOKEN` | The GitLab token to use for creating the release when using a personal access token. |
| `GITLAB_BOT_TOKEN` | The GitLab token to use for creating the release when using a project bot account. |

