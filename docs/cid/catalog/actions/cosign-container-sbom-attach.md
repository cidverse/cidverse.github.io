# cosign-container-sbom-attach

Cosign allows to attach SBOMs to a container image.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `MODULE_BUILD_SYSTEM == "container" && getMapValue(ENV, "COSIGN_KEY") != "" && getMapValue(ENV, "COSIGN_PASSWORD") != ""`

## Configuration

| Property | Description |
|---|---|
| `COSIGN_MODE` | The cosign mode, either "KEYLESS" or "PRIVATEKEY". |
| `COSIGN_KEY` | The cosign key, base64 encoded. |
| `COSIGN_PASSWORD` | The password for the cosign key. |
| `COSIGN_TLOG_DISABLE` | Disable using the public rekor transparency log. |

