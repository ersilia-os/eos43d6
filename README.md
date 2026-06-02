# Antimicrobial activity prediction against Mycobacterium tuberculosis from public ChEMBL and PubChem data

Bioactivity prediction of growth inhibition in Mycobacterium tuberculosis, trained as binary (active/inactive) classifiers from publicly available data in ChEMBL and PubChem. Independent models are trained on multiple bioactivity datasets, corresponding to single-point (percent inhibition) and dose-response (MIC) assays, among others. A ranking score is provided for each model alongside a combined consensus score.

This model was incorporated on 2026-05-19.Last packaged on 2026-06-01.

## Information
### Identifiers
- **Ersilia Identifier:** `eos43d6`
- **Slug:** `antimicrobial-activity-mtuberculosis`

### Domain
- **Task:** `Annotation`
- **Subtask:** `Activity prediction`
- **Biomedical Area:** `Tuberculosis`
- **Target Organism:** `Mycobacterium tuberculosis`
- **Tags:** `Antimicrobial activity`, `ChEMBL`

### Input
- **Input:** `Compound`
- **Input Dimension:** `1`

### Output
- **Output Dimension:** `57`
- **Output Consistency:** `Fixed`
- **Interpretation:** Probability of antimicrobial activity against Mycobacterium tuberculosis from 56 ChEMBL- and PubChem-trained sub-models, plus a quality-weighted consensus score.

Below are the **Output Columns** of the model:
| Name | Type | Direction | Description |
|------|------|-----------|-------------|
| consensus_score | float | high | Tanh-transformed quality-weighted consensus probability across the 56 sub-models. Recommended threshold: 0.956. |
| individual_percenteffect_b | float | high | Probability from sub-model trained on ChEMBL assay CHEMBL4649948 (percent effect; cutoff 50%; n=86589). Recommended threshold: 0.763. |
| individual_percenteffect_a | float | high | Probability from sub-model trained on ChEMBL assay CHEMBL4649961 (percent effect; cutoff 50%; n=53165). Recommended threshold: 0.774. |
| individual_ic50_a | float | high | Probability from sub-model trained on ChEMBL assay CHEMBL4649949 (IC50 measurements; cutoff 10 uM; n=2468). Recommended threshold: 0.736. |
| individual_ic50_b | float | high | Probability from sub-model trained on ChEMBL assay CHEMBL4649948 (IC50 measurements; cutoff 20 uM; n=2466). Recommended threshold: 0.682. |
| individual_mic90_decoys_a | float | high | Probability from sub-model trained on ChEMBL assay CHEMBL2098495 (MIC90 measurements; cutoff 10 uM; n=7760). Recommended threshold: 0.818. |
| individual_mic90_decoys_b | float | high | Probability from sub-model trained on ChEMBL assay CHEMBL2098496 (MIC90 measurements; cutoff 10 uM; n=1770). Recommended threshold: 0.786. |
| individual_mic_decoys_d | float | high | Probability from sub-model trained on ChEMBL assay CHEMBL1634496 (MIC measurements; cutoff 10 uM; n=1210). Recommended threshold: 0.9. |
| individual_mic_decoys_a | float | high | Probability from sub-model trained on ChEMBL assay CHEMBL1049617 (MIC measurements; cutoff 10 uM; n=1150). Recommended threshold: 0.899. |
| individual_mic_decoys_f | float | high | Probability from sub-model trained on ChEMBL assay CHEMBL5246903 (MIC measurements; cutoff 10 uM; n=1140). Recommended threshold: 0.899. |

_10 of 57 columns are shown_
### Source and Deployment
- **Source:** `Local`
- **Source Type:** `Internal`
- **DockerHub**: [https://hub.docker.com/r/ersiliaos/eos43d6](https://hub.docker.com/r/ersiliaos/eos43d6)
- **Docker Architecture:** `AMD64`, `ARM64`
- **S3 Storage**: [https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos43d6.zip](https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos43d6.zip)

### Resource Consumption
- **Model Size (Mb):** `1915`
- **Environment Size (Mb):** `1890`
- **Image Size (Mb):** `5157.36`

**Computational Performance (seconds):**
- 10 inputs: `115.76`
- 100 inputs: `115.69`
- 10000 inputs: `-1`

### References
- **Source Code**: [https://github.com/ersilia-os/chembl-antimicrobial-models](https://github.com/ersilia-os/chembl-antimicrobial-models)
- **Publication**: [https://github.com/ersilia-os/chembl-antimicrobial-models](https://github.com/ersilia-os/chembl-antimicrobial-models)
- **Publication Type:** `Other`
- **Publication Year:** `2026`
- **Ersilia Contributor:** [arnaucoma24](https://github.com/arnaucoma24)

### License
This package is licensed under a [GPL-3.0](https://github.com/ersilia-os/ersilia/blob/master/LICENSE) license. The model contained within this package is licensed under a [GPL-3.0-or-later](LICENSE) license.

**Notice**: Ersilia grants access to models _as is_, directly from the original authors, please refer to the original code repository and/or publication if you use the model in your research.


## Use
To use this model locally, you need to have the [Ersilia CLI](https://github.com/ersilia-os/ersilia) installed.
The model can be **fetched** using the following command:
```bash
# fetch model from the Ersilia Model Hub
ersilia fetch eos43d6
```
Then, you can **serve**, **run** and **close** the model as follows:
```bash
# serve the model
ersilia serve eos43d6
# generate an example file
ersilia example -n 3 -f my_input.csv
# run the model
ersilia run -i my_input.csv -o my_output.csv
# close the model
ersilia close
```

## About Ersilia
The [Ersilia Open Source Initiative](https://ersilia.io) is a tech non-profit organization fueling sustainable research in the Global South.
Please [cite](https://github.com/ersilia-os/ersilia/blob/master/CITATION.cff) the Ersilia Model Hub if you've found this model to be useful. Always [let us know](https://github.com/ersilia-os/ersilia/issues) if you experience any issues while trying to run it.
If you want to contribute to our mission, consider [donating](https://www.ersilia.io/donate) to Ersilia!
