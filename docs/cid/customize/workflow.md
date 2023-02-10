# Workflow

Workflows consist out of multiple stages, which in turn contain the action.

## How do Workflows work?

A workflow is a collection of actions that are split into individual stages.

- actions are *optional* unless specified otherwise
- actions are only executed if their rules match (see rules in action catalog)

## Run a Workflow

The following table illustrates some common use-cases on how workflows can be executed:

| COMMAND                                               | DESCRIPTION                                              |
|-------------------------------------------------------|----------------------------------------------------------|
| `cid workflow run {workflowName}`                     | Runs the entire workflow (all stages)                    |
| `cid workflow run {workflowName} --stage {stageName}` | Runs the action in a specific stage within a workflow    |

## Compose your own workflows

In this example we will compose a workflow called `awesome` that can be run with:

``` yaml title="cid.yaml"
workflows:
  - name: awesome
    rules: []
    stages:
      - name: build
        actions:
          - id: central/golang-build
            config:
              # cross-platform build
              platform:
                - goos: windows
                  goarch: amd64
                - goos: linux
                  goarch: amd64
                - goos: darwin
                  goarch: amd64
          - id: central/java-build
      - name: test
        actions:
          - id: central/golang-build
          - id: central/java-build
```

### Rules

...

### Config

You can pass custom configuration options to each action, check the documentation of each action to see available options.
Most configuration options can also be set / overwritten using environment variables.
