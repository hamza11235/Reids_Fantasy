# Reid's Fantasy: Data Extraction Pipeline

This repository branch contains a cleaned and generalized data-extraction workflow for Reid's Fantasy style conifold-transition data.

## What This Project Does

The notebook builds structured, machine-usable data from Kreuzer-style text files (`Y.v06.txt` ... `Y.v27.txt`) and computes geometry on the small-resolution side with CYTools.

Main tasks:
- Parse raw records (`pic`, `h12`, `E`, `H^3`, `c2H`, `sing`, toric headers, vertices)
- Filter records (default: `sing=0`)
- Recompute BK invariants (`dp`, `rk`, `sq`, `Lambda`)
- Compute CY data (`h11`, `h21`, `chi`, intersection tensor, `c2` pairings)
- Construct wall data in a rank-agnostic way for arbitrary Picard number
- Export cleaned outputs and diagnostics

## Key File

- `/Users/hamzaahmed/Reids_Fantasy/Data_Extraction_cleaned.ipynb`

## Included Artifacts

- `/Users/hamzaahmed/Reids_Fantasy/Example_Files/wall_data_sing0_pic1_to_2_cleaned_summary.csv`
- `/Users/hamzaahmed/Reids_Fantasy/Example_Files/wall_data_sing0_pic1_to_2_cleaned_errors_errors.jsonl`

## How To Run

1. Open `/Users/hamzaahmed/Reids_Fantasy/Data_Extraction_cleaned.ipynb`.
2. In the config cell (`CFG`), set your range, especially:
   - `min_picard`
   - `max_picard`
3. Run all cells top-to-bottom.
4. Check summary/error outputs under `Example_Files/`.

## Config Notes

Important knobs in `CFG`:
- `max_picard`: highest Picard number to process
- `require_sing0`: if `True`, only smoothable subset (`sing=0`)
- `sample_size`: optional downsample for quick tests
- `saturation_primes`: primes used for lattice saturation checks/fixes

## Output Schema (High Level)

Each output record has:
- `meta`: source and header metadata
- `xhat`: small-resolution side data (`h11`, `h21`, BK invariants, full `kappa`, full `c2` pairings)
- `y`: restricted wall-side data in `Pic(Y)` basis (`kappa` and `c2` in reduced basis)
- `checks`: consistency diagnostics

## Dependencies

Expected in your runtime environment:
- Python 3
- `cytools`
- `numpy`
- `sympy`
- `pandas`
- Jupyter (`ipykernel`)

## Branch Scope

This branch is intentionally focused on the cleaned data-extraction workflow and selected outputs, not all local notebooks/artifacts.
