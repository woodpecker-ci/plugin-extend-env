---
name: Extend .env
author: Woodpecker Authors
description: Extend your .env file with additional variables like semver information.
tags: [env, semver]
containerImage: woodpeckerci/plugin-extend-env
containerImageUrl: https://hub.docker.com/r/woodpeckerci/plugin-extend-env
url: https://github.com/woodpecker-ci/plugin-extend-env
---

<!-- markdownlint-disable MD041 -->

The extend env plugin extends an existing or creates a new `.env` file with additional variables like semver information.

The below pipeline configuration demonstrates simple usage:

```yml
steps:
  - name: extend-env
    image: docker.io/woodpeckerci/plugin-extend-env
```

The plugin does nothing unless the pipeline is running for a tag. It then writes the following variables to `.env`:

| Variable                          | Description                                                      |
| --------------------------------- | ---------------------------------------------------------------- |
| `CI_COMMIT_TAG_IS_SEMVER`         | `true` if the tag is a valid semantic version, otherwise `false` |
| `CI_COMMIT_TAG_SEMVER`            | The normalized semantic version (only if the tag is a semver)    |
| `CI_COMMIT_TAG_SEMVER_MAJOR`      | The major version number (only if the tag is a semver)           |
| `CI_COMMIT_TAG_SEMVER_MINOR`      | The minor version number (only if the tag is a semver)           |
| `CI_COMMIT_TAG_SEMVER_PATCH`      | The patch version number (only if the tag is a semver)           |
| `CI_COMMIT_TAG_SEMVER_PRERELEASE` | The pre-release part, e.g. `rc.1` (only if the version has one)  |
| `CI_COMMIT_TAG_IS_PRERELEASE`     | `true` if the version has a pre-release part (not set otherwise) |
