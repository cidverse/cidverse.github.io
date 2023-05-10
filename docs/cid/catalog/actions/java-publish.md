# java-publish

This action publishes maven artifacts.

**Publication**

Username and password are not required when publishing to GitHub Packages. (`https://maven.pkg.github.com/<your_username>/<your_repository>`)

**Signing**

To sign the artifacts, `MAVEN_GPG_SIGN_PRIVATEKEY` and `MAVEN_GPG_SIGN_PASSWORD` must be set.
You can generate a private key using the gpg command line tools:

``` bash
gpg --full-generate-key
// When asked for the key type, select `RSA (sign only)`.
// For the key size, select `4096`.
// For the expiration date, select `0` to make the key never expire.
// The Key-ID will appear in the output, it will look something like this `A1B2C3D4E5F6G7H8`.
// Use a strong password to protect the key, store it in the `MAVEN_GPG_SIGN_PASSWORD` secret.
gpg --armor --export-secret-keys A1B2C3D4E5F6G7H8 | base64 -w0
// Now store the secret key in the `MAVEN_GPG_SIGN_PRIVATEKEY`
```


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `MODULE_BUILD_SYSTEM == "gradle" && getMapValue(ENV, "MAVEN_REPO_URL") != ""`
- `MODULE_BUILD_SYSTEM == "maven" && getMapValue(ENV, "MAVEN_REPO_URL") != ""`

## Configuration

| Property | Description |
|---|---|
| `MAVEN_VERSION` | Overwrites the version of the maven artifact to publish, defaults to the git tag or branch name. |
| `MAVEN_REPO_URL`* | The URL of the maven repository to publish to. |
| `MAVEN_REPO_USERNAME` | The username to use for authentication with the maven repository. |
| `MAVEN_REPO_PASSWORD` | The password to use for authentication with the maven repository. |
| `MAVEN_GPG_SIGN_PRIVATEKEY` | The ASCII-armored private key (base64 encoded). |
| `MAVEN_GPG_SIGN_PASSWORD` | The password for the private key. |
| `MAVEN_GPG_SIGN_KEYID` | The GPG key ID, only required when using sub keys. |
| `GITHUB_ACTOR` | The GitHub actor to use for pushing the artifacts to a maven repository on GitHub Packages (https://maven.pkg.github.com/). |
| `GITHUB_TOKEN` | The GitHub token to use for pushing the artifacts to a maven repository on GitHub Packages (https://maven.pkg.github.com/). |

