---
title: Docker Registry
weight: 80
---

## Setup
We use the Google Container Registry as the main private docker registry for Halfpipe projects.
You can also use this registry from your local workstation, to push and pull images. To do so please use the credentials we already provided to you in vault.

Please read about [Vault](https://docs.halfpipe.io/vault) first.

### Docker login
```
$ vault read -field=private_key /springernature/[YOUR GITHUB TEAM NAME]/gcr | docker login -u _json_key --password-stdin https://eu.gcr.io
```

### Docker push
```
$ docker build . -t eu.gcr.io/halfpipe-io/[YOUR DOCKER IMAGE NAME]
$ docker push eu.gcr.io/halfpipe-io/[YOUR DOCKER IMAGE NAME]
```

### Docker pull
```
$ docker pull eu.gcr.io/halfpipe-io/[YOUR DOCKER IMAGE NAME]
```

### Example Dockerfile
```
FROM eu.gcr.io/halfpipe-io/[YOUR DOCKER IMAGE NAME]
```
