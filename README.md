# Reid's Fantasy

This project is a computational program around **conifold transitions of Calabi-Yau threefolds**.

## Big Picture

The goal is to build a practical, data-driven view of the Reid's Fantasy network:
- Start from toric/combinatorial descriptions of Calabi-Yau candidates.
- Compute small-resolution-side and deformation-side invariants.
- Assemble transition-aware datasets.
- Train and test predictive models for geometric quantities and transition behavior.

In short: connect explicit geometry computations with statistical/ML modeling at scale.

## Core Objectives

1. Build reliable extraction pipelines from Kreuzer-style input files.
2. Compute and validate key invariants (`h11`, `h21`, `dp`, `rk`, `sq`, intersection data, `c2` pairings).
3. Construct wall/deformation-side data across varying Picard numbers.
4. Produce reproducible datasets for downstream experiments.
5. Evaluate predictive models (classification/regression) on extracted geometry features.

## Project Components

The broader workspace includes three layers:

1. **Geometry & extraction notebooks**
- Parse source files and construct structured records.
- Compute CY data with CYTools and symbolic checks.
- Export compact artifacts for modeling.

2. **Transition/invariant analysis**
- Compare small-resolution and deformation-side descriptions.
- Verify lattice/basis consistency and rank/saturation properties.
- Study conifold-transition constraints empirically.

3. **Modeling & experiments**
- Build features from extracted geometry.
- Train models (e.g. CatBoost-based workflows).
- Track metrics and experiment outputs.

## Typical Workflow

1. Run data extraction / validation notebooks.
2. Export cleaned records and summaries.
3. Train and evaluate prediction models.
4. Iterate on feature engineering and geometric constraints.

## Current Branch Scope

This branch (`codex/data-extraction-cleaned`) focuses on the cleaned, generalized extraction pipeline and selected outputs:
- `Data_Extraction_cleaned.ipynb`
- `Example_Files/wall_data_sing0_pic1_to_2_cleaned_summary.csv`
- `Example_Files/wall_data_sing0_pic1_to_2_cleaned_errors_errors.jsonl`

## Dependencies

Common runtime requirements:
- Python 3
- Jupyter / ipykernel
- `cytools`
- `numpy`
- `sympy`
- `pandas`

## Notes

- The repository contains active research notebooks and generated artifacts.
- Not every local experiment artifact is intended for version control.
- Branches may focus on specific pipeline stages (extraction, validation, modeling) rather than the full workspace snapshot.
