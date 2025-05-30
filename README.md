# adaptive-docker

This repository contains templates to deploy Adaptive Engine with docker compose on a single node.

To deploy, copy the `compose/sample.env` file to `compose/.env` file and replace the relevant values in `compose/.env`.

```
cp compose/sample.env compose/.env
```

`GPU_COUNT` must match the number of available GPUs in your server. Be sure to also replace your OIDC provider client id and secret, as well as root url, so that you can authenticate to the Adaptive UI.

The docker-compose.yml assumes you have a `model_registry` directory within the `compose` directory containing your models.
You can change this to another directory by altering `MODEL_REGISTRY_HOST_PATH` in `compose/.env`.

Note: all mounts defined in the docker compose are bind mounts, to guarantee no models or data are lost between restarts, and to facilitate inspecting data.

To launch Adaptive Engine, run the following commands:

```bash
cd compose
docker compose up -d
```
