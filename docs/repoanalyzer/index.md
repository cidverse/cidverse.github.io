# Overview

## Introduction

`RepoAnaylzer` is a module that scans a project directory to discover modules.

## Result

The entire project directory is scanned to return a list of all modules containing the following data:

```json
[
    {
        "project_dir": "/my-project",
        "module_dir": "/my-project/upx",
        "discovery": [
            {
                "file": "/my-project/upx/Dockerfile"
            }
        ],
        "name": "upx",
        "slug": "upx",
        "build_system": "container",
        "build_system_syntax": "containerfile",
        "language": null,
        "dependencies": null,
        "submodules": null,
        "files": [
            "/my-project/README.md",
            "/my-project/upx/Dockerfile",
        ]
    }
]
```

This information is used in `CID` to decide which workflow should run / which actions need to be executed to build a project.

## Supported Build Systems

| Build System              | Variants                      |
|---------------------------|-------------------------------|
| `gradle`                  | groovy, kotlin                |
| `maven`                   |                               |
| `gomod`                   |                               |
| `npm`                     |                               |
| `hugo`                    |                               |
| `helm`                    |                               |
| `container`               | containerfile, buildah-script |
| `python-requirements.txt` |                               |
| `pipfile`                 |                               |
| `setup.py`                |                               |
| `mkdocs`                  | default, mkdocs-techdocs      |
