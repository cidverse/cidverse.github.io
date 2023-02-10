# Workflow: main

The `main` workflow is the default workflow in `CID` if no workflow name is provided.

It contains the following stages, with conditional actions based on the project type.

``` yaml title=".github/workflows/ci.yml"
build:
- id: central/go-build
- id: central/java-build
- id: central/python-build
- id: central/node-build
- id: central/hugo-build
- id: central/helm-build
- id: central/mkdocs-build
- id: central/techdocs-build

test:
- id: central/go-test
- id: central/java-test
- id: central/helm-test

package:
- id: central/upx-optimize
- id: central/buildah-build

scan:
- id: central/python-lint
- id: central/helm-lint
- id: central/semgrep-scan
- id: central/sonarqube-scan
- id: central/qodana-scan
- id: central/syft-container-sbom-generate

publish:
- id: central/buildah-publish
- id: central/java-publish
- id: central/helm-publish-nexus
- id: central/techdocs-publish
- id: central/changelog-generate
- id: central/github-release-publish
```
