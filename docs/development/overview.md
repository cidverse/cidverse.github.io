# Overview

## General

> This document is currently a draft and subject to revision. Please note that the information contained herein may be incomplete or in the process of being refined.

In this document, you will find recommendations for safeguarding the security and integrity of your project. If you would like to learn more about potential threats, take a look at the [sources](#credits).

!!! note "Quick Start"

    - The [guides](#guides) will guide you through the necessary steps to secure your repository. This combines repository settings, conventions and our [prebuilt CI workflows](/cid/workflows).

## Guides

We have provided guides on how to configure your repository. Follow the links below to learn more:

- :material-github: [GitHub](guide/github.md)
- :material-gitlab: [GitLab](guide/gitlab.md)

In addition, we recommend following these conventions for your project:

- :material-source-commit: [Commit Messages](convention/commits.md)
- :material-git: [Versioning](convention/versioning.md)
- :octicons-git-pull-request-24: [Pull Request](pullrequest.md)

## Threats

``` mermaid
graph LR;
    Developer{{Developer}}
    subgraph Source Threats
        Developer --> Source
    end
    subgraph Build Threats
        Source --> Build
        Build --> Package
        Package --> Consumer
    end
    subgraph Dependency Threats
        Dep(Dependencies)
        Dep-->Build
    end
    Consumer{{Consumer}}
```

### Code Review

1. Configure branch protection to require pull request reviews for the main branch.
1. Configure branch protection to dismiss stale approvals when new changes are pushed.
1. Pull requests require approval from two different, trusted persons. If the proposer is trusted, only one approval is needed; otherwise two approvals are needed.
1. There are no exceptions to the review requirement, even for Robot Accounts and Administrators.
1. A constributor may only contribute on one account to prevent puppet approvals.
1. Only the version that is actually reviewed is the one that is approved. Any intermediate revisions don’t count as being reviewed.

### Code quality

1. All code *MUST* be checked by a static code analysis tool.
1. Feedback from static code analysis *MUST* be published in the pull request.

### Repository

1. All contributors *MUST* be subject to same controls, whether or not they have administrator privileges or not.
1. Administrators *MUST* use 2FA with a hardware token to prevent tempering with the settings, thereby mitigating the risk of a compromised administrator account bypassing security controls.

### Dependencies

1. To apply security patches as soon as possible, you *SHOULD* automate dependency updates.

### Build Process

1. Builds *MUST* run on a build service
1. The build service *MUST* ensure that the build steps are executed in an ephemeral and isolated environment provisioned solely for this build, free of influence from other build instances, whether prior or concurrent
1. The builds *MUST* be reproducible, ensuring that the output of the build process remains consistent regardless of when or where it is built.

### Packages and Artifacts

Output from the build process *MUST* implement measures to ensure the integrity and security of generated artifacts.

1. The build system *MUST* generate a Software Bill of Materials (SBOM) and attest the generated artifacts with a signed version of the SBOM
1. The build *MUST* provide verifiable information about software artifacts describing where, when and how something was produced (`SLSA V1.0`)

## Terminology

> The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in <a href="https://www.rfc-editor.org/rfc/rfc2119">RFC 2119</a>.

## Credits

The following sources were used to create this document:

- [SLSA](https://slsa.dev) is a initative of the [OpenSSF](https://openssf.org/) to improve supply chains security.
