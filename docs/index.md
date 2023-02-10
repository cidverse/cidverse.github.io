# Overview

!!! tip "Quick Start"

    If you are looking to get started with CID check out [this page](/cid).

CIDVerse holds a collection of projects that aim to provide a `platform-agnostic` ci process, which is accompished using the following components:

| Project   |      Description / Use Case      |
|----------|:-------------:|
| [NormalizeCI](https://github.com/cidverse/normalizeci) | normalizes input from CI/CD systems as a base to make `platform-agnostic` pipelines possible |
| [RepoAnaylzer](https://github.com/cidverse/repoanalyzer) | scans the project to disover all build systems, languages, etc. |
| [CID](https://github.com/cidverse/cid) | uses `NormalizeCI` and `RepoAnaylzer` to provide a `platform-agnostic` interface to craft actions and workflows. |

!!! note "Benefits"

    - Platform Agnostic - You can use the same workflow that is running in CI to test/run the project locally.
    - Fast Feedback - Rather than having to commit/push/wait every time you want to test out the changes you are making to your continuous integration and deployment process, you can run your workflow locally.
    - Testing - Actions can be written in as programs with proper test coverage.
    - Containerized - All steps of your Pipeline are executed in containers with limited access to environment variables, files, ...

### [NormalizeCI](https://github.com/cidverse/normalizeci)

NormalizeCI provides a universal standard for CI/CD environment variables such as COMMIT_HASH, and the possiblity to convert CI/CD environment variables from various platforms into this standard.
Even if your platform is not officially supported ([refer to supported systems](https://github.com/cidverse/normalizeci#supported-systems)), the default Git module will still extract all necessary information by inspecting the Git repository. This also works when running locally.

### [RepoAnaylzer](https://github.com/cidverse/repoanalyzer)

By analyzing a project, RepoAnalyzer identifies all projects and build systems used in the project. This information can then be used to determine the necessary actions for building each project module.
