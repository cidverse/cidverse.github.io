# buildah-build

Builds the oci container image (and manifest if required) using buildah.

The following comments are supported in the Dockerfile, these allow you to set the image repository and platforms to build:
- `# platforms=linux/amd64,linux/s390x,linux/ppc64le`
- `# image=quay.io/username/imagename`


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `MODULE_BUILD_SYSTEM == "container" && (MODULE_BUILD_SYSTEM_SYNTAX == "buildah-script" || MODULE_BUILD_SYSTEM_SYNTAX == "containerfile")`

## Configuration


No configuration is required.
