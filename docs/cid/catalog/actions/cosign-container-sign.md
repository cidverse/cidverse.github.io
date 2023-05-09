# cosign-container-sign

Cosign is a tool that enables container image signing, verification, and storage in an OCI registry.
It supports various signing methods, including keyless signing using a public good certificate authority and transparency log, hardware and KMS signing, and bring-your-own PKI.
With Cosign, you can sign your container images to ensure their authenticity and integrity, and store them in a trusted registry.
The signed images can then be verified by others to ensure that they have not been tampered with.


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

