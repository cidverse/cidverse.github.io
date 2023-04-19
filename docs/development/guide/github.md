# GitHub

## Branch Protection

> Settings -> Branches -> Add branch protection rule

The branch name pattern should cover your main and development branches. Common values are:

- `main`
- `main|develop`

Enable the following options:

- Check `Require a pull request before merging`
- Set `Require approvals` to `1` or more depending on your project team size
- Check `Dismiss stale pull request approvals when new commits are pushed`
- Check`Require approval of the most recent reviewable push`
- Check `Require status checks to pass before merging`
- Check `Require conversation resolution before merging`
- Check `Require linear history`
- Check `Do not allow bypassing the above settings`

## Tag Protection

> Settings -> Tags -> New rule

Create a rule with the following name pattern: `v*`

This will ensure that tags can only be created by authorized users.

## Code security and analysis

> Security -> Code security and analysis

- Enable `Private vulnerability reporting`
- Set `Code scanning` -> `Pull request check failure` set to `Medium or higher / only errors` to evaluate sarif uploads from the ci pipeline.
- Enable `Secret scanning` to receive alerts on GitHub for detected secrets, keys, or other tokens that get commited into your repository accidentally.

## Dependency Updates

Select one of the following options:

- [Renovate](renovate.md)

## Static Code Analysis

Select one of the following options:

- [SonarCloud](sonarcloud.md)
