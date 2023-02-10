# Local

## Prerequisites

- A container runtime, such as `docker` or `podman`, is required to execute containerized actions and commands.

## Installation

To install `CID` locally, use the following command:

```sh
curl -L -o /usr/local/bin/cid https://github.com/cidverse/cid/releases/download/latest/linux_amd64
```

## Usage

Once `CID` is installed, you can run actions or workflows using the `cid` command. For example, you can run the `mkdocs-start` action with `cid action run central/mkdocs-start`.

For more examples on how to run actions or workflows, see the following guides:

- [action](../action.md)
- [workflow](../workflow.md)

## Examples

### CLI

`CID` comes with a primary workflow that detects the project type and enables required actions on-demand. You can use the following commands to build and test your project:

``` sh
cid workflow run --stage build
cid workflow run --stage test
```

Check out the [main workflow documentation](../ready-to-use/main.md) for more details.
