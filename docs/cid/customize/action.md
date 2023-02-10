# Action

## Acquire Actions

Actions are shared in a `repository`, a `repository` contains a index file with a list of actions. Actions will be downloaded on-demand based on their configuration.

The central repository is included by default, you can add other repositories using:

TODO ...

## Run an Action

The following table illustrates some common use-cases on how actions can be executed:

| COMMAND                                               | DESCRIPTION                                              |
|-------------------------------------------------------|----------------------------------------------------------|
| `cid action run {actionRepository}/{actionName}`                     | Runs the action                     |
| `cid action run central/mkdocs-start`                     | Runs the `mkdocs-start` action of the central repository                  |
