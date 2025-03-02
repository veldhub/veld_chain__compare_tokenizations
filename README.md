# ![veld chain](https://raw.githubusercontent.com/veldhub/.github/refs/heads/main/images/symbol_V_letter.png) veld_chain__compare_tokenizations

This repo contains [chain velds](https://zenodo.org/records/13322913) encapsulating comparison of
two tokenization tools: [teitok-tools](https://github.com/ufal/teitok-tools) and 
[xmlanntools](https://github.com/czcorpus/xmlanntools), using their veldified versions: 
[veld_code__teitok-tools](https://github.com/veldhub/veld_code__teitok-tools) and 
[veld_code__xmlanntools](https://github.com/veldhub/veld_code__xmlanntools) respectively.
Additionally, [veld_code__downloader](https://github.com/veldhub/veld_code__downloader) is reused 
and [veld_code__jupyter_notebook_base](https://github.com/veldhub/veld_code__jupyter_notebook_base)
is integrated directly into this chain repo as a git subtree.

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

### all chains in one go

**[./veld_step_all.yaml](./veld_step_all.yaml)** 

This chain reuses the individual chains described below and allows batch execution of them all in
one go.

```
docker compose -f veld_step_all.yaml up
```

### all chains sequentially

**[./veld_step_1_download.yaml](./veld_step_1_download.yaml)** 

Downloads a sample TEI XML from [the german ELTeC corpus](https://github.com/COST-ELTeC/ELTeC-deu/)

```
docker compose -f veld_step_1_download.yaml up
```

**[./veld_step_2_xmlanntools.yaml](./veld_step_2_xmlanntools.yaml)** 

Runs xmlanntools to tokenize the TEI file.

```
docker compose -f veld_step_2_xmlanntools.yaml up
```

**[./veld_step_3_teitok.yaml](./veld_step_3_teitok.yaml)** 

Runs teitok-tools to tokenize the TEI file.

```
docker compose -f veld_step_3_teitok.yaml up
```

**[./veld_step_4_jupyter_analysis.yaml](./veld_step_4_jupyter_analysis.yaml)** 

Launches a jupyter notebook that compares the two enriched TEI files. After running the following
command, the notebook can be opened at http://localhost:8888/ . The notebook is persisted at
[./code/veld_code__jupyter_analysis/src/tokenization_analysis.ipynb](./code/veld_code__jupyter_analysis/src/tokenization_analysis.ipynb)

```
docker compose -f veld_step_4_jupyter_analysis.yaml up
```

