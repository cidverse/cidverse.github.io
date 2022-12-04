# Overview

## What is a Action?

## SDKs

You can easily create your own actions by using one of our SDKs.

- [SDK - Go](sdk-go.md)
- [SDK - Java](sdk-java.md)
- [SDK - Kotlin](sdk-kotlin.md)

## Start from Scratch

You can easily start your action from scratch in any language of your choice.

Your actions require the following capabilities:

- implement the API (see the [openapi-spec]() to generate a client in your language of choice)
- communicate with the api using http or via unix socket

## Action Design Guidelines

### Artifacts

Generated artifacts should be placed in `<artifact_dir>/<module.slug>/<artifact_type>`

- artifact_dir can be read from the configuration using the sdk
- module.slug can be read from the module list using the sdk
- the artifact_type needs to be set appropriately, see the following table:


| TYPE        | DESC                                                                          |
|-------------|-------------------------------------------------------------------------------|
| `oci-image` | should be used to store build oci images (.tar)                               |
| `sbom`      | should be used to store generated sbom's for the software or container images |
