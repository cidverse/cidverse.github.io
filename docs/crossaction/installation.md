# Installation

## Local

``` sh
curl -L -o /usr/local/bin/cid https://github.com/cidverse/cid/releases/download/experimental/linux_amd64
```

## GitHub Actions

Add the following as first step in each of your jobs in your workflow:

``` yaml
- name: prepare environment
  uses: cidverse/ghact-cid-setup@main
```
