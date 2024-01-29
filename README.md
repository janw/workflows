# GitHub Actions Workflows

<!-- markdownlint-disable MD033 MD013 -->
<div align="center">

[![Linters](https://github.com/janw/workflows/actions/workflows/.local.linters.yaml/badge.svg)](https://github.com/janw/workflows/actions/workflows/.local.linters.yaml)
[![pre-commit](https://img.shields.io/badge/-pre--commit-f8b424?logo=pre-commit&labelColor=grey)](https://github.com/pre-commit/pre-commit)

</div>

A collection of reusable but opinionated GitHub Actions Workflows.

## `commitizen-bump-version`

### Example use

```yaml
name: Bump version

on:
  push:
    branches:
      - main

jobs:
  bump-version:
    uses: janw/workflows/.github/workflows/commitizen-bump-version.yaml@main
    secrets:
      personal-access-token: ${{ secrets.PERSONAL_ACCESS_TOKEN }}
      gpg-private-key: ${{ secrets.GPG_PRIVATE_KEY }}
      gpg-passphrase: ${{ secrets.GPG_PASSPHRASE }}
```

### Required variables

None.

### Required secrets

* `PERSONAL_ACCESS_TOKEN`: [Fine-grained PAT](https://github.com/settings/tokens?type=beta) of the repo owner with `content: write` permissions
* `GPG_PRIVATE_KEY`: GPG key to sign the release
* `GPG_PASSPHRASE`: Passphrase to the GPG key

## `commitizen`

### Example use

```yaml
name: Linters

on:
  pull_request:

jobs:
  commitizen:
    uses: janw/workflows/.github/workflows/commitizen.yaml@main
```

### Required variables

None.

### Required secrets

None.
