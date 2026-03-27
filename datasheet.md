# Datasheet for Dataset

## Dataset Name

Simulated Early-Phase Oncology Clinical, Biomarker, and PK Dataset

## Motivation

This dataset was created to support a reproducible demonstration of an early development analytics workflow. The purpose is to show how raw trial-like datasets can be integrated into analysis-ready outputs for exploratory review, visualization, and modeling.

The dataset is intended for:
- educational demonstration, presentation,
- workflow prototyping.

It is not intended for scientific discovery or clinical use.

## Composition

The dataset consists of three linked raw tables and one processed analysis dataset.

### Raw clinical data
Contains one row per patient and includes:
- patient identifier,
- dose information,
- demographics,
- ECOG,
- tumor measurements,
- survival and event variables,
- adverse event variables.

### Raw biomarker data
Contains one row per patient and includes:
- LDH,
- CRP,
- glucose,
- lactate,
- ctDNA fraction,
- mutation status,
- biomarker response score.

### Raw PK data
Contains multiple rows per patient across timepoints and includes:
- patient identifier,
- time,
- drug concentration.

### Analysis dataset
Contains one row per patient after integration and derivation of variables such as:
- tumor percent change,
- responder status,
- clinical benefit,
- high biomarker flags,
- AUC,
- Cmax,
- Tmax.

## Instance Count

The default simulation generates approximately:
- 120 patients,
- 120 clinical rows,
- 120 biomarker rows,
- 960 PK rows, depending on the number of PK timepoints,
- 120 rows in the final analysis dataset.

## Data Generation Process

The dataset is fully synthetic and generated using scripted probabilistic rules. The data generation process was designed to produce plausible patterns commonly seen in early oncology development, including:
- heterogeneous anti-tumor response,
- biomarker-associated outcome differences,
- dose-dependent PK exposure,
- increasing toxicity with higher dose.

No patient-level data, public clinical records, or identifiable data were used.

## Preprocessing and Cleaning

The raw datasets are processed by:
- loading each source,
- summarizing PK exposure,
- merging all tables by patient identifier,
- deriving exploratory endpoint variables,
- exporting a final analysis-ready dataset.

## Derived Variables

Examples include:
- tumor percent change from baseline,
- responder status,
- clinical benefit,
- high LDH flag,
- high CRP flag,
- AUC from 0 to 72 hours,
- Cmax,
- Tmax.

## Missing Data

The starter simulation is designed to produce complete data for simplicity. In real-world extensions, missingness mechanisms could be added to better reflect operational clinical settings.

## Uses

Appropriate uses:
- demonstration of data integration workflows,
- exploratory statistical programming examples,
- practice in figure generation,
- prototype biomarker-response analyses,
- teaching reproducibility concepts.

Inappropriate uses:
- clinical decision-making,
- real drug development decisions,
- regulatory submission support,
- benchmarking real model performance.

## Distribution

The dataset is generated locally by script and does not require external download. Distribution occurs through the repository code rather than through a static source file.

## Confidentiality and Privacy

Because the dataset is simulated, it contains no real personal data, no protected health information, and no re-identifiable patient records.

## Known Limitations

Important limitations include:
- simplified biology,
- simplified PK structure,
- limited endpoint realism,
- absence of protocol deviations and operational noise,
- absence of real CDISC conventions,
- no site-level or longitudinal clinical complexity beyond the included variables.

## Maintenance and Versioning

The dataset may be regenerated whenever:
- simulation logic changes,
- variable definitions are updated,
- sample size changes,
- additional endpoints are added.

Any such changes should be documented in repository version history.

## Citation
**Mark I.R. Petalcorin** (2026). Simulated Early-Phase Oncology Clinical, Biomarker, and PK Dataset. https://github.com/mpetalcorin/early-phase-clinical-biomarker-pipeline
