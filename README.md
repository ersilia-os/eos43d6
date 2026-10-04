# Antimicrobial activity prediction against Mycobacterium tuberculosis from public ChEMBL and PubChem data

Estimates activity against Mycobacterium tuberculosis by combining 34 independent classifiers, each fitted to a distinct pool of bioactivity data drawn from ChEMBL and PubChem. Tuberculosis benefits from far more public screening data than most pathogens, which is why this panel is larger than its counterparts for other organisms, and single-point and dose-response measurements are kept apart throughout. A quality-weighted consensus summarises the panel into one score.

This model was incorporated on 2026-05-19.Last packaged on 2026-07-22.

## Information
### Identifiers
- **Ersilia Identifier:** `eos43d6`
- **Slug:** `antimicrobial-activity-mtuberculosis`

### Domain
- **Task:** `Annotation`
- **Subtask:** `Activity prediction`
- **Biomedical Area:** `Tuberculosis`, `Antimicrobial resistance`
- **Target Organism:** `Mycobacterium tuberculosis`
- **Tags:** `Antimicrobial activity`, `ChEMBL`

### Input
- **Input:** `Compound`
- **Input Dimension:** `1`

### Output
- **Output Dimension:** `35`
- **Output Consistency:** `Fixed`
- **Interpretation:** Probability of Mycobacterium tuberculosis inhibition across 34 sub-models, plus a weighted consensus.

Below are the **Output Columns** of the model:
| Name | Type | Direction | Description |
|------|------|-----------|-------------|
| consensus_score | float | high | Tanh-transformed quality-weighted consensus probability across the 34 sub-models. Recommended threshold: 0.698. |
| chembl_single_point_0 | float | high | Probability from sub-model trained on ChEMBL single-point signal-based pool of 52 assays (87159 compounds). Recommended threshold: 0.8. |
| chembl_single_point_1 | float | high | Probability from sub-model trained on ChEMBL single-point signal-based pool of 23 assays (1032 compounds; incl. 419 added negatives). Recommended threshold: 0.497. |
| chembl_single_point_2 | float | high | Probability from sub-model trained on ChEMBL single-point signal-based pool of 56 assays (918 compounds; incl. 192 added negatives). Recommended threshold: 0.514. |
| chembl_single_point_3 | float | high | Probability from sub-model trained on ChEMBL single-point signal-based pool of 35 assays (834 compounds; incl. 201 added negatives). Recommended threshold: 0.469. |
| chembl_single_point_4 | float | high | Probability from sub-model trained on ChEMBL single-point signal-based pool of 18 assays (690 compounds). Recommended threshold: 0.716. |
| chembl_single_point_5 | float | high | Probability from sub-model trained on ChEMBL single-point signal-based pool of 47 assays (565 compounds). Recommended threshold: 0.517. |
| chembl_single_point_6 | float | high | Probability from sub-model trained on ChEMBL single-point signal-based pool of 40 assays (437 compounds). Recommended threshold: 0.501. |
| chembl_single_point_7 | float | high | Probability from sub-model trained on ChEMBL single-point signal-based pool of 14 assays (328 compounds). Recommended threshold: 0.567. |
| chembl_single_point_8 | float | high | Probability from sub-model trained on ChEMBL single-point signal-based pool of 19 assays (308 compounds; incl. 15 added negatives). Recommended threshold: 0.476. |

_10 of 35 columns are shown_
### Source and Deployment
- **Source:** `Local`
- **Source Type:** `Internal`
- **DockerHub**: [https://hub.docker.com/r/ersiliaos/eos43d6](https://hub.docker.com/r/ersiliaos/eos43d6)
- **Docker Architecture:** `AMD64`, `ARM64`
- **S3 Storage**: [https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos43d6.zip](https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos43d6.zip)

### Resource Consumption
- **Model Size (Mb):** `1246`
- **Environment Size (Mb):** `7208`
- **Image Size (Mb):** `8902.6`

**Computational Performance (seconds):**
- 10 inputs: `84.28`
- 100 inputs: `87.45`
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
