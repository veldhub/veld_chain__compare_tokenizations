# ![veld chain](https://raw.githubusercontent.com/veldhub/.github/refs/heads/main/images/symbol_V_letter.png) veld_chain__compare_tokenizations

This repo contains [chain velds](https://zenodo.org/records/13322913) encapsulating comparison of
two tokenization tools: [teitok-tools](https://github.com/ufal/teitok-tools) and 
[xmlanntools](https://github.com/czcorpus/xmlanntools), using their veldified versions: 
[veld_code__teitok-tools](https://github.com/veldhub/veld_code__teitok-tools) and 
[veld_code__xmlanntools](https://github.com/veldhub/veld_code__xmlanntools) respectively.

## requirements

- git
- docker compose (note: older docker compose versions require running `docker-compose` instead of 
  `docker compose`)

Clone this repo with all its submodules
```
git clone --recurse-submodules https://github.com/veldhub/veld_chain__compare_tokenizations.git
```

## how to reproduce

The following chain velds were used. Open the respective veld yaml file for more information.

**[./veld_step_1_download.yaml](./veld_step_1_download.yaml)** 

Downloads a sample txt file from [Project Gutenberg](https://www.gutenberg.org/).

```
docker compose -f veld_step_1_download.yaml up
```

**[./veld_step_2_xmlanntools.yaml](./veld_step_2_xmlanntools.yaml)** 

Runs xmlanntools to tokenize the text and persist it as TEI XML.

```
docker compose -f veld_step_2_xmlanntools.yaml up
```

**[./veld_step_3_teitook.yaml](./veld_step_3_teitook.yaml)** 

Runs teitok-tools to tokenize the text and persist it as TEI XML.

```
docker compose -f veld_step_3_teitook.yaml up
```

