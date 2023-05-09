# java-publish

Publishes the java module to the configured maven repository.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `MODULE_BUILD_SYSTEM == "gradle"`- `MODULE_BUILD_SYSTEM == "maven"`

## Configuration

| Property | Description |
|---|---|
| `MAVEN_REPO_URL` | The URL of the maven repository to publish to. |
| `MAVEN_REPO_USERNAME` | The username to use for authentication with the maven repository. |
| `MAVEN_REPO_PASSWORD` | The password to use for authentication with the maven repository. |
| `GPG_SIGN_KEYID` | The GPG key ID to use for signing the artifacts. |
| `GPG_SIGN_PRIVATEKEY` | The GPG private key to use for signing the artifacts. |
| `GPG_SIGN_PASSWORD` | The GPG password to use for signing the artifacts. |
| `GITHUB_ACTOR` | The GitHub actor to use for pushing the artifacts to a maven repository on GitHub Packages (https://maven.pkg.github.com/). |
| `GITHUB_TOKEN` | The GitHub token to use for pushing the artifacts to a maven repository on GitHub Packages (https://maven.pkg.github.com/). |

