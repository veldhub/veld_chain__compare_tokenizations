# ![veld chain](https://raw.githubusercontent.com/veldhub/.github/refs/heads/main/images/symbol_V_letter.png) veld_code__jupyter_notebook_base

This repo contains [code velds](https://zenodo.org/records/13322913) encapsulating a template 
jupyter notebook setup, mainly used for quick forking.

## requirements

- git
- docker compose (note: older docker compose versions require running `docker-compose` instead of 
  `docker compose`)

## how to use

A code veld may be integrated into a chain veld, or used directly by adapting the configuration 
within its yaml file and using the template folders provided in this repo. Open the respective veld 
yaml file for more information.

**[./veld.yaml](./veld.yaml)** 

Launches a jupyter notebook

```
docker compose -f veld.yaml up
```

