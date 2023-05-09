# Overview

## What are actions?

A `CID action` is a small, standalone program that is designed to orchestrate a single task inside of a `CID` workflow.
The action may make use of other tools by leveraging the `CID` command-api to run tasks in separate containers.

## How are actions used?

Actions are used in `CID workflows` to orchestrate the different stages of your pipeline.


## SDKs

You can easily create your own actions by using one of our SDKs.

- [SDK - Go](sdk-go.md)
- [SDK - Java](sdk-java.md)
- [SDK - Kotlin](sdk-kotlin.md)
- [SDK - Python](sdk-python.md)
- ...

**From Scratch**

You can easily start your action from scratch in any language of your choice.

Your actions require the following capabilities:

- implement the API (see the [openapi-spec]() to generate a client in your language of choice)
- support communication with the api over http or unix socket

## Design Guidelines

### Command Execution

If your action requires other cli tools to execute commands, it is best practice to use the command-api to execute them in standalone containers.
This keeps your actions small and allows for easy updates of the cli tools independently of the action.

### Artifacts

If your action generates artifacts, use the api to upload them into the artifact store.
This allows later actions to query the artifacts and use them for further processing.
