# techdocs-publish

Publishes the generated documentation to the target location.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `MODULE_BUILD_SYSTEM == "mkdocs" && MODULE_BUILD_SYSTEM_SYNTAX == "mkdocs-techdocs"`

## Configuration

| Property | Description |
|---|---|
| `TECHDOCS_ENTITY` | The entity to publish the documentation for. |
| `TECHDOCS_PUBLISH_TARGET` | The target to publish the documentation to. (awsS3, ...) |
| `TECHDOCS_S3_ENDPOINT` | The S3 endpoint url. |
| `TECHDOCS_S3_REGION` | The S3 bucket region. |
| `TECHDOCS_S3_BUCKET` | The S3 bucket name. |
| `TECHDOCS_S3_ACCESS_KEY` | The S3 Access Key. |
| `TECHDOCS_S3_SECRET_KEY` | The S3 Secret Key. |
| `TECHDOCS_S3_FORCE_PATH_STYLE` | Use s3 path style to address the bucket, required for ie. minio. |

