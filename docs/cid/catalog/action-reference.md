# Action Reference

The catalog contains a list of actions that can be used in workflows.

## Overview

``` yaml
actions:
- name: mkdocs-build
  category: build
  description: |
    Build the mkdocs documentation.
  type: container
  container:
    image: quay.io/cidverse/cid-actions-go:latest
    command: central run mkdocs-build
  scope: module
  rules:
  - type: cel
    expression: MODULE_BUILD_SYSTEM == "mkdocs"
```

- this configures the `mkdocs-build` action
- the `category` and `description` are used for documentation purposes
- the type is `container`, as such the specified `container.image` will be started with `container.command`
- `container.image` is the image the action is executed in
- `container.command` is the cli command used to start the action, this can be used to start the right action if multiple are shipped in one image
- the scope is set to module, evaluation of the rules will run for each discovered project module individually
- the rules control if the action will be executed

## Types

Supported Types:

- `container`
- ...

### Type: Container

If the requirements are met, then the container specified in the `container` field will be started with the provided `image` and `command`.

## Rules

Supported Types:

- [Common Expression Language (CEL)](https://github.com/google/cel-spec)

### Common Expression Language

| SCOPE  | VARIABLE                   | EXAMPLE | DESCRIPTION                    |
|--------|----------------------------|---------|--------------------------------|
| all    | ENV["VAR"]                 | value   | allows to access env variables |
| module | MODULE_BUILD_SYSTEM        | gradle  | detected build system          |
| module | MODULE_BUILD_SYSTEM_SYNTAX | kotlin  | detected build system syntax   |

!!! note "Notes"

    - depending on the action `scope` only a subset of variables are available
    - possible scopes are `project` or `module`

Example:

``` yaml
  rules:
  - type: cel
    expression: MODULE_BUILD_SYSTEM == "mkdocs"
```
