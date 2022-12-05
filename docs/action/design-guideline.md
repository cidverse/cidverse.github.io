# Design Guidelines

## Command Execution

If your action requires other cli tools to execute commands, it is best practice to use the command-api to execute them in standalone containers.

## Artifacts

Generated artifacts should be placed in `<artifact_dir>/<module.slug>/<artifact_type>`

- `artifact_dir` can be read from the configuration using the sdk
- `module.slug` can be read from the module list using the sdk
- `artifact_type` needs to be set according to the following table:

| TYPE        | DESC                                                                          |
|-------------|-------------------------------------------------------------------------------|
| `oci-image` | should be used to store build oci images (.tar)                               |
| `sbom`      | should be used to store generated sbom's for the software or container images |
