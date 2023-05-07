# GitLab CI

## Prerequisites

- A GitLab account and repository are required to use `CID` with GitLab.

## Installation

To use `CID` with GitLab, add the following step to the beginning of each job in your pipeline:

``` yaml title=".gitlab-ci.yml"
stages:
  - build

build:
  stage: build
  script:
    - cid workflow run --stage build
```
