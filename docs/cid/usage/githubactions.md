# GitHub Actions

## Prerequisites

- A GitHub account and repository are required to use `CID` with GitHub Actions.
- We recommend following our [GitHub](../../development/guide/github) guide to securely configure your project. (all guides are available [here](../../development/overview)

## Setup

Add the following file to your project:

``` yaml title=".github/workflows/ci.yml"
# name
name: ci

# triggers
on:
  # allow manual execution
  workflow_dispatch:
  # build main branch and tags
  push:
    branches:
      - main
    tags:
      - v*.*.*
    paths-ignore:
      - README.md
      - LICENSE
      - .github/**
      - .gitignore
      - .editorconfig
      - renovate.json
  # build pull requests against main branch
  pull_request:
    branches:
      - main
    paths-ignore:
      - README.md
      - LICENSE
      - .github/**
      - .gitignore
      - .editorconfig
      - renovate.json

jobs:
  check:
    uses: cidverse/catalog/.github/workflows/shared-ci.yml@main
    with:
      cid-workflow: main
      cid-version: latest
      # job-pages: true
    secrets:
      QODANA_TOKEN: ${{ secrets.QODANA_TOKEN }}
      SONAR_HOST_URL: ${{ secrets.SONAR_HOST_URL }}
      SONAR_ORGANIZATION: ${{ secrets.SONAR_ORGANIZATION }}
      SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}
```

## Workflow

CID offers multiple workflows to build and test your project, in addition to the default workflow, `main`, which is used in the example above. 
To use a different workflow, replace `main` with the name of the workflow you want to use. (`cid-workflow: <name>`.)

A list of available workflows can be found [here](../../catalog/workflows).

## Secrets

You can view the actions that are part of a workflow by opening the workflow file in the [catalog](../../catalog/workflows).
Some actions are conditinal and require secrets to be set, these are documented in the action page.

## Deployment Environments

By default version tags (`v*`) are built in the `production` environment, while the main branch is built in the `development` environment. You can use `environments` to use different deployment targets per environment.

## Pages

Due to GitHub API limitations, you need to set the `job-pages: true` parameter to toggle conditinal jobs that publish github pages.
