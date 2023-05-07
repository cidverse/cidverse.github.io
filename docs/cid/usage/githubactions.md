# GitHub Actions

## Prerequisites

- A GitHub account and repository are required to use `CID` with GitHub Actions.

## Workflows

You can use one of the [prebuilt workflows](../../workflows) by using this snippet. You are able to customize the used workflow by setting the `name` in `cid-workflow: <name>`.

In addition you can add `secrets` to toggle conditional actions that require credentials.
If you want to publish github pages please include the `job-pages: true` parameter.

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
