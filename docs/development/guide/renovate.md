# Renovate

## Introduction

Renovate will scan your project and create merge request to update your dependencies.

## Installation

**GitHub**

You can enable renoavate using the github marketplace by using their official application: https://github.com/marketplace/renovate.

**GitLab**

You can follow this guide to enable renovate on gitlab: https://docs.renovatebot.com/examples/self-hosting/#gitlab-cicd-pipeline

## Configuration

You can use our preset in your repository by adding a `renovate.json` file to your project.

``` json title="renovate.json"
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "github>philippheuer/renovate-config:preset-global"
  ],
  "baseBranches": ["main"]
}
```
