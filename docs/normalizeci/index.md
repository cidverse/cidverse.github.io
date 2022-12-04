# Overview

## Introduction

`NormalizeCI` is a cli tool (and go library) which can normalize the provided env variables from ci platforms as a foundation for a platform-agnostic CICD processes.

!!! note "What benefits does this have?"

    - *normalization* - check the env vars and the local repository to provide a common set of env vars for scripts that work with any ci platform.
    - *compatibility* - convert the common env vars into a specific format (ie. gitlab) to run a script made for gitlab on any ci provider.

## How does it work?

- NormalizeCI defines a global standard for CI/CD variables (COMMIT_HASH, ...), as such only `NCI_` variables should be used in actions to ensure cross-platform support.
- Even if your platform is not yet officialy supported (see [here](https://github.com/cidverse/normalizeci#supported-systems)) the default git module will still provide all required information (also when running your ci process locally)

## Supported Platforms

| NAME                                                                                       | SLUG             |
|--------------------------------------------------------------------------------------------|------------------|
| [Azure DevOps Pipeline](https://github.com/cidverse/normalizeci/tree/main/pkg/azuredevops) | `azure-devops`   |
| [GitLab CI/CD](https://github.com/cidverse/normalizeci/tree/main/pkg/gitlabci)             | `gitlab-ci`      |
| [GitHub Actions](https://github.com/cidverse/normalizeci/tree/main/pkg/githubactions)      | `github-actions` |
| [Local Git Repository](https://github.com/cidverse/normalizeci/tree/main/pkg/localgit)     | `local`          |

!!! note "Not Supported?"

    - the `Local Git Repository` can also provide all required information on unsupported / planned ci platforms!

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

    - If you want to contribute, feel free to pick one of the following services and add a package to normalize their variables.
