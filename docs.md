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
