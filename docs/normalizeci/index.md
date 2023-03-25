# NormalizeCI

## Introduction

`NormalizeCI` is a go library and specification to normalize the provided environment information from ci platforms, to provide a foundation for a platform-agnostic CI-CD workflows and actions.
`NormalizeCI` also provides a binary release to set the normlaized envirnoment locally.

!!! note "Merits"

    - *normalization* - check the env vars and the local repository to provide a common set of env vars for scripts that work with any ci platform.
    - *compatibility* - convert from the common `NCI_` spec into a specific format (ie. GitHub Actions) as a compatiblity layer to run GitHub Actions on other platforms
    - *testability* - the local git module can provide all required information to test / use your ci workflows locally

## How does it work?

- NormalizeCI defines a global standard for CI/CD variables (COMMIT_HASH, ...), as such only `NCI_` variables should be used in actions to ensure cross-platform support
- Even if your platform is not yet officialy supported (see [here](https://github.com/cidverse/normalizeci#supported-systems)), the default local module can extract almost all required information from your local repository (even when running your ci process locally)

## Usage

- [CLI](usage/cli.md)
- [Library](usage/library.md)

## Supported Platforms

| NAME                                             | SLUG             | Normalize | Denormalize | Features |
|--------------------------------------------------|------------------|-----------|-------------|----------|
| [Generic - Git](platform/generic-git.md)         | `local`          | yes       |             |          |
| [Azure DevOps Pipeline](platform/azuredevops.md) | `azure-devops`   | yes       | no          |          |
| [GitLab CI/CD](platform/gitlabci.md)             | `gitlab-ci`      | yes       | no          | inputs   |
| [GitHub Actions](platform/githubactions.md)      | `github-actions` | yes       | no          | inputs   |

Some Normalizer's can also query the API of the build system for additional information, the following features might be available:

- `inputs` - information about custom user variables set for a specific ci run

!!! note "Not Supported?"

    - NormalizeCI will fallback to the `local repository` to extract most information from the local repository on unsupported ci platforms!

## Planned Platforms

| NAME                                                                                    | SLUG            |
|-----------------------------------------------------------------------------------------|-----------------|
| [AppVeyor](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/appveyor)          | `appveyor`      |
| [AWS CodeBuild](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/awscodebuild) | `aws-codebuild` |
| [Bamboo](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/bamboo)              | `bamboo`        |
| [Bitbucket](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/bitbucket)        | `bitbucket`     |
| [Bitrise](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/bitrise)            | `bitrise`       |
| [Buddy](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/buddy)                | `buddy`         |
| [Buildkite](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/buildkite)        | `buildkite`     |
| [CircleCI](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/circleci)          | `circleci`      |
| [Cirrus CI](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/cirrusci)         | `cirrusci`      |
| [Codefresh](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/codefresh)        | `codefresh`     |
| [Codeship](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/codeship)          | `codeship`      |
| [Drone](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/drone)                | `drone`         |
| [Jenkins](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/jenkins)            | `jenkins`       |
| [Sail CI](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/sailci)             | `sailci`        |
| [Semaphore](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/semaphore)        | `semaphore`     |
| [Shippable](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/shippable)        | `shippable`     |
| [TeamCity](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/teamcity)          | `teamcity`      |
| [Travis CI](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/travisci)         | `travis-ci`     |
| [Wercker](https://github.com/cidverse/normalizeci/tree/main/pkg_wip/wercker)            | `wercker`       |

!!! note "Contribute?"

    - If you want to contribute, feel free to pick one of the planned systems to work on an implementation.
