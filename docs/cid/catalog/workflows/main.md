# main

The `main` workflow is the default workflow in `CID` if no workflow name is provided.

It contains the following stages, with conditional actions based on the project type.



## Stage: build

- [go-build](../actions/go-build.md)
- [java-build](../actions/java-build.md)
- [python-build](../actions/python-build.md)
- [node-build](../actions/node-build.md)
- [hugo-build](../actions/hugo-build.md)
- [helm-build](../actions/helm-build.md)
- [mkdocs-build](../actions/mkdocs-build.md)
- [techdocs-build](../actions/techdocs-build.md)

## Stage: test

- [go-test](../actions/go-test.md)
- [java-test](../actions/java-test.md)

## Stage: package

- [upx-optimize](../actions/upx-optimize.md)
- [buildah-build](../actions/buildah-build.md)

## Stage: scan

- [helm-lint](../actions/helm-lint.md)
- [semgrep-scan](../actions/semgrep-scan.md)
- [sonarqube-scan](../actions/sonarqube-scan.md)
- [qodana-scan](../actions/qodana-scan.md)
- [syft-container-sbom-generate](../actions/syft-container-sbom-generate.md)
- [github-sarif-upload](../actions/github-sarif-upload.md)

## Stage: publish

- [buildah-publish](../actions/buildah-publish.md)
- [java-publish](../actions/java-publish.md)
- [helm-publish-nexus](../actions/helm-publish-nexus.md)
- [helm-publish-registry](../actions/helm-publish-registry.md)
- [techdocs-publish](../actions/techdocs-publish.md)
- [changelog-generate](../actions/changelog-generate.md)
- [github-release-publish](../actions/github-release-publish.md)
