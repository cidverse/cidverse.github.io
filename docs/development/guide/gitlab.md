# GitLab

## Branch Protection

> Settings -> Repository -> Protected branches

Protect your main main and development branches. Common names are:

Branch:

- `main` or `master`
- `develop`

Allowed to merge: `Maintainers`
Allowed to push and merge: `No one`
Allowed to force push: `false`

## Tag Protection

> Settings -> Repository -> Protected tagse

Add a entry to protect your tags.

Tag: `v*`
Allowed to create: `Maintainers`

This will ensure that tags can only be created by authorized users.

## Merge Requests

> Settings -> Merge requests

Set following options:

Merge method: `Fast-forward merge`
Squash commits when merging: `Require`

Merge Checks:

- Check `Pipelines must succeed`
- Check `All threads must be resolved`

## Dependency Updates

Select one of the following options:

- [Renovate](renovate.md)

## Static Code Analysis

Select one of the following options:

- [SonarCloud](sonarcloud.md)
