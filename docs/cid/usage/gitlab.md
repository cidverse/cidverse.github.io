# GitLab CI

## Prerequisites

- A GitLab account and repository are required to use `CID` with GitLab.

## Installation

You can use one of the [prebuilt workflows](../../catalog/workflows) by using this snippet. You are able to customize the used workflow by setting the `name` in `cid-workflow: <name>`.

TODO: provide a ci template for gitlab

``` yaml title=".gitlab-ci.yml"
stages:
  - build

build:
  stage: build
  script:
    - cid workflow run --stage build
```
