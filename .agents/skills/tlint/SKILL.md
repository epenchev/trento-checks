---
name: tlint
description: Runs a basic syntax analysis on the check DSL, run tlint tool on checks.
---

### More on the tlint tool
Validation engine for Trento Checks DSL.
https://github.com/trento-project/tlint

### How to run tlint.
```sh
docker run --rm -i -v "${PWD}":/data ghcr.io/trento-project/tlint:latest lint '/data/checks/<trento-check-file.yaml>'
```

### An example running tlint on a trento-check file with docker.
```sh
docker run --rm -i -v "${PWD}":/data ghcr.io/trento-project/tlint:latest lint /data/checks/790926.yaml
```

### An example running tlint on a trento-check file with podman.
```sh
podman run --rm -i -v "${PWD}":/data:Z ghcr.io/trento-project/tlint:latest lint /data/checks/790926.yaml
```

> [!NOTE]
> Command must be run from the repo root, otherwise /data/checks/... does not exist.
