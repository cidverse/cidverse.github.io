# buildah-publish

Publishes the container image or manifest using skopeo and stores the image digest for later use in image signing and attestation.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `MODULE_BUILD_SYSTEM == "container" && (MODULE_BUILD_SYSTEM_SYNTAX == "buildah-script" || MODULE_BUILD_SYSTEM_SYNTAX == "containerfile")`

## Configuration


No configuration is required.
