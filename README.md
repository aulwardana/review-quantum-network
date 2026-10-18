# Code and data for "Quantum Networks Still Need Watching"

Supporting code and data for the survey *Quantum Networks Still Need Watching: A Survey on Intrusion Detection Systems for Quantum Communication Infrastructures* 

## Repository layout

| Path | Content |
|---|---|
| `notebooks/01_simulation_section6.ipynb` | Simulation of the attack discrimination problem (survey Section 6.4, Figure 5). Writes JSON/CSV to `results/`. |
| `notebooks/02_literature_methodology.ipynb` | Literature search (OpenAlex, arXiv), de-duplication, tiered screening, recall check, corpus statistics, generation and verification of `ref.bib`. Writes to `outputs/`. |
| `data/curated_references.csv` | The 126 references cited in the survey with full bibliographic fields, DOI, the sections that cite each reference, and a flag for the 31 references used in the recall check. |
| `results/` | Output of notebook 01. |
| `outputs/` | Output of notebook 02. |

## Run in Colab

1. Open a notebook from GitHub in Colab (replace `<user>` and `<repo>`):
   - `https://colab.research.google.com/github/<user>/<repo>/blob/main/notebooks/01_simulation_section6.ipynb`
   - `https://colab.research.google.com/github/<user>/<repo>/blob/main/notebooks/02_literature_methodology.ipynb`
2. Notebook 02 needs `REPO_URL` (Cell 2), your e-mail for the OpenAlex and Crossref polite pools, and a free OpenAlex API key
   (<https://openalex.org/settings/api>, stored as the Colab secret `OPENALEX_API_KEY`).
3. Run all cells. Download the zip created in the last cell, or commit the `results/` and `outputs/` folders.

## Reproducibility notes

- **Notebook 01 is deterministic.** Seeds are fixed (`SEED=7`, `TRACE_SEED=11`) and Cell 8 checks the output against the numbers quoted in the paper.
- **Notebook 02 depends on live APIs.** OpenAlex and arXiv change over time, so record counts differ slightly between runs (for example 5,053 versus 5,055 records between two runs in October 2026).
  The counts reported in the paper come from the committed snapshot `outputs/`; commit your own run to keep a permanent record.
- The keyword rules in Cell 7 are a transparent first-pass screen, not a substitute for reading the papers.

## Licence

Code: MIT (see `LICENSE`). The data in `data/` are bibliographic metadata.
