# GitHub Actions

## Prerequisites

- A GitHub account and repository are required to use `CID` with GitHub Actions.

## Workflows

You can use one of the [prebuilt workflows](../../workflows) by using this snippet. You are able to customize the used workflow by setting the name in `cid-workflow: <name>`.
In addition you can add `secrets` to toggle conditional actions.

``` yaml title=".github/workflows/ci.yml"
# name
name: ci

# triggers
on:
  workflow_dispatch:
  push:
    branches:
      - 'main'
    tags:
      - 'v*.*.*'
    paths-ignore:
      - ".gitignore"
      - ".editorconfig"

jobs:
  check:
    uses: cidverse/catalog/.github/workflows/shared-ci.yml@main
    with:
      cid-workflow: main
      cid-version: latest
    secrets:
      QODANA_TOKEN: ${{ secrets.QODANA_TOKEN }}
      SONAR_HOST_URL: ${{ secrets.SONAR_HOST_URL }}
      SONAR_ORGANIZATION: ${{ secrets.SONAR_ORGANIZATION }}
      SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}
```

## Examples

### GitHub Pages

The following is an example workflow that demonstrates how to use `CrossAction` to build and publish a GitHub Pages site:

``` yaml title=".github/workflows/main.yml"
# name
name: CI

# triggers
on:
  workflow_dispatch:
  push:
    branches: [ main ]
    paths-ignore:
      - "**.md"
      - ".gitignore"
      - ".editorconfig"

# default permissions
permissions:
  contents: read

# jobs
jobs:
  # build
  build:
    name: Build
    runs-on: ubuntu-latest
    steps:
      - name: prepare environment
        uses: cidverse/ghact-cid-setup@main
        with:
          version: experimental
      - name: checkout
        uses: actions/checkout@v3
        with:
          fetch-depth: 0
      - name: build
        run: |
          cid workflow run --stage build
      - uses: actions/upload-pages-artifact@v1
        with:
          path: .dist/cidverse-github-io/html
  # publish
  publish:
    name: Publish
    runs-on: ubuntu-latest
    needs: build
    permissions:
      pages: write
      id-token: write
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v1
```
