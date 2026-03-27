# early-phase-clinical-biomarker-pipeline

A reproducible Python workflow for generating, integrating, and analyzing simulated early-phase oncology clinical trial data with clinical, biomarker, and pharmacokinetic endpoints. The project creates analysis-ready datasets, summary tables, exploratory visualizations, and hypothesis-generating models to demonstrate decision-support analytics relevant to early development biometrics.
<img width="1372" height="954" alt="Screenshot 2026-03-27 at 11 26 26" src="https://github.com/user-attachments/assets/1300a41d-043e-444d-b822-4a3c8e2a8c2d" />

## Overview

Early clinical development often requires flexible, exploratory analyses that integrate multiple data sources, including clinical outcomes, biomarkers, and PK measurements. This project simulates a Phase I oncology setting and shows how raw study data can be transformed into traceable, analysis-ready outputs that support early development decision-making.

The workflow is designed to reflect key expectations of an early development programming environment:
- reproducible data generation and processing,
- analysis-ready dataset creation,
- exploratory summaries and visualizations,
- fit-for-purpose statistical modeling,
- structured outputs for review and interpretation.

## Project Objectives

This repository demonstrates how to:

1. simulate realistic early-phase oncology trial data,
2. integrate clinical, biomarker, and PK sources,
3. derive analysis variables relevant to exploratory endpoints,
4. generate summary tables and standard oncology visualizations,
5. fit simple exploratory models for response and clinical benefit,
6. preserve reproducibility through modular scripts and saved outputs.

## Repository Structure

```text
early-phase-clinical-biomarker-pipeline/
│
├── data/
│   ├── raw_clinical_data.csv
│   ├── raw_biomarker_data.csv
│   └── raw_pk_data.csv
│
├── data_processed/
│   └── analysis_dataset.csv
│
├── outputs/
│   ├── figures/
│   │   ├── waterfall_plot.png
│   │   ├── km_curve_dose_group.png
│   │   ├── biomarker_vs_tumor_change.png
│   │   ├── pk_profiles.png
│   │   └── adverse_event_rate_by_dose.png
│   ├── tables/
│   │   ├── summary_table.csv
│   │   └── patient_listing.csv
│   └── models/
│       └── model_results.txt
│
├── scripts/
│   ├── 01_simulate_data.py
│   ├── 02_build_analysis_dataset.py
│   ├── 03_generate_tables.py
│   ├── 04_visualize.py
│   └── 05_modeling.py
│
├── notebook/
│   └── exploratory_trial_analysis.ipynb
│
├── README.md
├── modelcard.md
└── datasheet.md
```
## Simulated Study Design

The synthetic dataset represents a simulated early-phase oncology trial with approximately 120 patients assigned across multiple dose levels. The workflow includes three primary raw data sources:

## Clinical dataset

Contains patient-level variables such as:
	•	dose level,
	•	age,
	•	sex,
	•	ECOG performance status,
	•	baseline and Week 6 tumor measurements,
	•	survival time,
	•	event status,
	•	adverse event grade,
	•	discontinuation.

## Biomarker dataset

Contains baseline translational variables such as:
	•	LDH,
	•	CRP,
	•	glucose,
	•	lactate,
	•	ctDNA fraction,
	•	mutation status,
	•	biomarker response score.

## PK dataset

Contains longitudinal concentration data across prespecified timepoints to support exposure summaries such as:
	•	AUC,
	•	Cmax,
	•	Tmax.

## Analysis-Ready Dataset

The core output is analysis_dataset.csv, which integrates all raw sources and derives variables commonly used in exploratory oncology analyses, including:
	•	tumor percent change from baseline,
	•	responder status,
	•	clinical benefit status,
	•	high versus low biomarker indicators,
	•	PK exposure summaries.

This step is conceptually similar to creating an analysis-ready dataset for downstream exploratory review.

## Outputs

The workflow generates the following outputs.

Tables
	•	summary_table.csv, dose-group level descriptive summaries
	•	patient_listing.csv, patient-level review listing

Figures
	•	waterfall plot of tumor response
	•	Kaplan-Meier style survival curve by dose group
	•	biomarker versus tumor change plot
	•	PK profile plot by dose group
	•	Grade 3+ adverse event rate by dose group

##  Models
	•	logistic regression for responder status
	•	random forest for clinical benefit
	•	exploratory survival association summaries

## Example Workflow Logic

The simulation was designed so that:
	•	higher dose modestly improves tumor response,
	•	higher LDH, CRP, and ctDNA are associated with poorer outcomes,
	•	higher drug exposure is associated with improved response probability,
	•	toxicity increases with dose.

This structure allows the final outputs to resemble plausible early development findings.

## Why This Project Is Relevant

This repository is intended to showcase practical capabilities relevant to early development programming and translational analytics, including:
	•	handling structured and semi-structured scientific data,
	•	building traceable analysis datasets,
	•	producing fit-for-purpose outputs for decision support,
	•	applying reproducible programming workflows,
	•	documenting logic clearly for review and reuse.

## Limitations

This project uses fully simulated data and is intended for demonstration purposes only. It is not a regulatory workflow, does not implement CDISC standards, and is not meant for confirmatory statistical inference. The analyses are exploratory and hypothesis-generating.

## Future Extensions

Possible next steps include:
	•	adding CDISC-like variable naming conventions,
	•	implementing the workflow in R or SAS,
	•	creating an interactive dashboard in Shiny or Plotly,
	•	adding longitudinal biomarker modeling,
	•	including exposure-response analyses,
	•	packaging the workflow into a formal reproducible report.

## License
MIT

## Citation
**Petalcorin, M.I.R** (2026). Early-Phase Clinical Biomarker Exploratory Models. https://github.com/mpetalcorin/early-phase-clinical-biomarker-pipeline
