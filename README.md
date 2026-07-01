# Delayed Monetary Losses: Procedure and Measure Validation

[![DOI](https://img.shields.io/badge/DOI-10.1016%2Fj.beproc.2024.105101-blue)](https://doi.org/10.1016/j.beproc.2024.105101)
[![OSF](https://img.shields.io/badge/OSF-emb2q-2a6fbb)](https://osf.io/emb2q/)
[![License: MIT](https://img.shields.io/badge/code%20license-MIT-green.svg)](LICENSE)

Open data and reproducible R and Python analyses for:

> Wan, H., Green, L., & Myerson, J. (2024). Delayed monetary losses: Do different procedures and discounting measures assess the same construct? *Behavioural Processes, 222*, 105101. <https://doi.org/10.1016/j.beproc.2024.105101>

## Research question

Do the Adjusting-Amount (Adj-Amt) procedure and the 27-item Delayed Losses Questionnaire (DLQ) measure the same delayed-loss discounting construct?

The study analyzed 431 online participants and compared two scoring approaches for each procedure:

- atheoretical measures: area under the curve (Adj-Amt) and immediate-choice proportion (DLQ);
- theoretically derived measures: log-transformed *k* estimates based on a simple hyperbola.

Across the two common delayed amounts ($90 and $240), scores from the procedures were strongly correlated (all *r* > .72). The analyses also showed strong concurrent validity and alternate-forms reliability. Most participants (72.2%) displayed the same typical or always-immediate response pattern across procedures.

## Repository structure

| Path | Purpose |
| --- | --- |
| [`Analysis/analysis_R.qmd`](Analysis/analysis_R.qmd) | Executable R/Quarto analysis with published-value checks |
| [`Analysis/analysis_R.html`](Analysis/analysis_R.html) | Rendered R report |
| [`Analysis/analysis_Py.ipynb`](Analysis/analysis_Py.ipynb) | Executable Python/Jupyter analysis |
| [`Analysis/analysis_Py.qmd`](Analysis/analysis_Py.qmd) | Readable Quarto source for the Python notebook |
| [`Analysis/analysis_Py.html`](Analysis/analysis_Py.html) | Rendered Python source report |
| [`data/Data_AdjAmt_DLQ.csv`](data/Data_AdjAmt_DLQ.csv) | Anonymized analysis dataset |
| [`data/README.md`](data/README.md) | Data dictionary, provenance, and integrity information |
| [`Presentation/ABAI 2024/`](Presentation/ABAI%202024/) | Conference poster |
| [`Figure/`](Figure/) | Archived publication figures |

The R and Python workflows independently implement the same scientific decisions. Both cover the analyses that directly support the article's central measurement conclusion: Figure 1 and Tables 2-4. They do not claim to reproduce every secondary demographic or amount-effect model in the publication.

## Reproduce the analysis

Clone the repository and run commands from its root directory.

### R

Requirements: R 4.1 or later and [Quarto](https://quarto.org/).

```bash
quarto render Analysis/analysis_R.qmd
```

The R workflow uses base R and `knitr`. The included `renv.lock` records the small rendering environment; `renv::restore()` is optional.

### Python

Requirements: Python 3.11 or later, Quarto, and the packages in `requirements.txt`.

```bash
python3 -m venv .venv
source .venv/bin/activate
python3 -m pip install -r requirements.txt
quarto render Analysis/analysis_Py.ipynb --execute
```

The checked-in Python HTML is a source report because Python execution was not available in the repository-review environment. Execute the notebook locally to populate results. The R report was executed end to end and contains machine-checkable comparisons with the published values.

## Open-science practices

- The analysis dataset is included in a nonproprietary CSV format and is also archived on [OSF](https://osf.io/emb2q/).
- Data validation checks verify sample size, trial counts, amount conditions, delays, and binary choice coding before analysis.
- Reproduction checks stop execution if the primary correlations, response-pattern table, or reported consistency statistic diverge from the article beyond rounding tolerance.
- Random seeds and computational environments are reported in the rendered analyses.
- The original article is open access under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

## Citation

Please cite the article above when using the data, measures, or analysis. Machine-readable citation metadata are provided in [`CITATION.cff`](CITATION.cff).

## Licenses

The analysis code and repository documentation are released under the [MIT License](LICENSE). The article and data may have separate terms; consult the DOI and OSF records before redistribution.
