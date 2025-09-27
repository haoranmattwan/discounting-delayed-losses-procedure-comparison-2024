# Delayed Monetary Losses: A Comparison of Two Procedures

This repository contains the analysis scripts, figures, and presentation materials for the peer-reviewed publication:

> Wan, H., Green, L., & Myerson, J. (2024). Delayed monetary losses: Do different procedures and measures assess the same construct?. *Behavioural Processes*, *105101*. https://doi.org/10.1016/j.beproc.2024.105101

---

## Project Overview

This study investigates whether two reliable methods for measuring how people discount delayed losses—the Adjusting-Amount procedure and the Delayed Losses Questionnaire (DLQ)—measure the same underlying psychological construct. While similar procedures are used to study delayed gains, less is known about their comparability when assessing attitudes toward future losses.

The analysis workflow involves processing raw experimental data to derive both theoretical (hyperbolic `k` parameter) and atheoretical (Area under the Curve) measures of discounting for each participant. We then employ a range of statistical techniques, including nonlinear regression, beta regression, and correlation analyses, to assess the reliability and construct validity of the two procedures. A secondary analysis also categorizes participants based on their choice patterns to examine the consistency of response styles across methods.

The data from this study are available at <https://osf.io/emb2q/>.

## Repository Structure

The project materials are organized into the following folders:

* **/Analysis**: Contains the primary analysis scripts that replicate the findings in the paper.
    * `analysis.qmd`: A Quarto document with the complete **R** code for the entire workflow, from data processing to final statistical tests and visualization.
    * `analysis.ipynb`: A Jupyter Notebook providing a direct **Python** translation of the R analysis, using `pandas` for data manipulation and `lmfit` and `statsmodels` for modeling.

* **/Presentation**: Contains a slide deck or poster used to present the findings of this research at an academic conference.

* **/Figure**: Contains the figures as they appear in the final publication.

---

## Methodology Snapshot

This project demonstrates proficiency in a comprehensive data analysis pipeline, including:

* **Complex Data Processing**: Custom functions in R and Python to calculate individual-participant discounting parameters from raw choice data, including Area under the Curve (atheoretical) and nonlinear least-squares estimation of the `k` parameter (theoretical).
* **Nonlinear Modeling**: Fitting hyperboloid and logistic functions to group-level data to visualize discounting curves and assess model fit (`R²`).
* **Specialized Regression**: Using beta regression to model the proportional Area under the Curve data and binomial GLMs for choice data from the DLQ, correctly accounting for the distributional properties of the dependent variables.
* **Reliability and Validity Analysis**: A full suite of correlation analyses to test within-procedure reliability (across different monetary amounts) and between-procedure construct validity.
* **Exploratory Pattern Analysis**: Classifying participants based on the consistency of their choices and using contingency table analysis to assess whether individuals exhibit similar response patterns across different measurement procedures.

---

## Software and Execution

To run the analyses, you will need the appropriate software environment and the raw data file.

### R Environment (`/Analysis/analysis.qmd`)

* **Required Packages**: `dplyr`, `tidyr`, `readr`, `ggplot2`, `minpack.lm`, `betareg`, `multcomp`, `gmodels`, and others as listed in the script.
* **Installation**:
    ```R
    install.packages(c("tidyverse", "minpack.lm", "betareg", "multcomp", "gmodels", "here", "psych"))
    ```

### Python Environment (`/Analysis/analysis.ipynb`)

* **Required Packages**: `pandas`, `numpy`, `scipy`, `lmfit`, `statsmodels`, `seaborn`, `scikit-learn`, `openpyxl`.
* **Installation**:
    ```bash
    pip install pandas numpy scipy lmfit statsmodels seaborn scikit-learn openpyxl
    ```