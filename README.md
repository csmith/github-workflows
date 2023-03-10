# Common GitHub Workflows

This repo contains some GitHub workflows I use in my projects.

## build-image.yml

Builds a container image using buildah and pushes it to the GitHub container
registry. Example usage:

```yaml
name: build image
on:
  push:
    branches:
      - master
    tags:
      - v*
jobs:
  build:
    uses: csmith/github-workflows/.github/workflows/build-image.yml@master
    secrets: inherit
```

## go-test.yml

Installs the current stable version of Go and runs all tests in a package.
Example usage:

```yaml
name: run go tests
on:
  push:
    branches:
      - master
  pull_request:
jobs:
  build:
    uses: csmith/github-workflows/.github/workflows/go-test.yml@master
```
