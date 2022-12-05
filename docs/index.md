# Overview

## Introduction

`CrossAction` allows you to compose your CI/CD workflow using platform-agnostic reusable actions.

!!! note "What benefits does this have?"

    - Platform Agnostic - You can use the same workflow that is running in CI to test/run the project locally.
    - Fast Feedback - Rather than having to commit/push/wait every time you want to test out the changes you are making to your continuous integration and deployment process, you can run your workflow locally.
    - Testing - Actions can be written in programming languages with test coverage.

## How does it work?

`CrossAction` contains the following modules to make creating actions or workflows easy:

### WorkflowEngine

``` mermaid
sequenceDiagram
  User->>CrossAction: Run
  CrossAction->>YourAction: start
  YourAction->>CrossAction: request `npm install`
  CrossAction-->>YourAction: send result
```

### [NormalizeCI](https://github.com/cidverse/normalizeci)

- NormalizeCI defines a global standard for CI/CD variables (COMMIT_HASH, ...), as such only `NCI_` variables should be used in actions to ensure cross-platform support.
- Even if your platform is not yet officialy supported (see [here](https://github.com/cidverse/normalizeci#supported-systems)) the default git module will still provide all required information (also when running your ci process locally)

### [RepoAnaylzer](https://github.com/cidverse/repoanalyzer)

- scans / detects all modules of your project, which allows you to properly work with repositories that for example contain a backend, a frontend and your documentation. 

RepoAnalyzer is a library that will analyze a directory to detect all projects / build-systems used in your project.
This information can later be used to decide which actions need to run to build each of your project modules.
