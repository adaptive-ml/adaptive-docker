# adaptive-docker

This repository contains templates to deploy Adaptive Engine with docker compose on a single node.

To deploy, replace the relevant values in `compose/.env`.

`GPU_COUNT` must match the number of available GPUs in your server. Be sure to also replace your OIDC provider client id and secret.

The docker-compose.yml assumes you have a `model_registry` directory within the `compose` directory containing your models.
You can change this to another directory by altering `MODEL_REGISTRY_HOST_PATH` in `compose/.env`.

To launch Adaptive Engine, run the following commands:

```bash
cd compose
mkdir -p shared workdir cache/huggingface
sudo chown -R 1002:1002 shared/ workdir/ cache/
docker compose up -d
````