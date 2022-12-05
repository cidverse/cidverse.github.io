# Action Catalog

## Catalog Items

The action catalog is a yaml file that contains a list of available actions:

``` yaml
- repository: central
  name: techdocs-start
  type: container
  container:
    image: quay.io/cidverse/cid-actions-go:latest
    command: central run techdocs-start
  scope: module
  rules:
  - type: cel
    expression: MODULE_BUILD_SYSTEM == "mkdocs" && MODULE_BUILD_SYSTEM_SYNTAX == "mkdocs-techdocs"
```

- this configures the `techdocs-start` action
- the type is `container`, as such the specified `container.image` will be started with `container.command`
- the scope is set to module, evaluation of the rules will run for each discovered project module individually
- the rules control if the action will be executed

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
    expression: MODULE_BUILD_SYSTEM == "mkdocs" && MODULE_BUILD_SYSTEM_SYNTAX == "mkdocs-techdocs"
```
