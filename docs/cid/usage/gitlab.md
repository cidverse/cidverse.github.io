# GitLab CI

## Prerequisites

- A GitLab account and repository are required to use `CID` with GitLab.
- We recommend following our [GitLab](../../../development/guide/gitlab) guide to securely configure your project. (all guides are available [here](../../../development/overview)

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
