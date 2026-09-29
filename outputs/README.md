# DS-A1 | Data Provenance and Measurement Audit

## Dataset

This audit uses the UCI Bike Sharing Dataset, specifically the frozen `day.csv` file containing daily observations from the Capital Bikeshare system for 2011–2012.

Source: UCI Machine Learning Repository
Dataset DOI: 10.24432/C5W894
License: CC BY 4.0

## Research Question

How is daily bike-rental demand associated with observed weather conditions in the UCI Bike Sharing Dataset?

## Study Design

- Stakeholder: Bike-sharing system operator
- Population: Daily bike-sharing activity represented by Capital Bikeshare during 2011–2012
- Sample: 731 daily observations
- Unit of analysis: One calendar day
- Target: `cnt`, total daily bike rentals
- Estimand: Association between observed daily weather conditions and total daily bike-rental demand within the observed 2011–2012 data

## Data Provenance and Freeze

File: `day.csv`
Size: 57,569 bytes
SHA-256: `a6bcf826782d3c0fbfdcbeead17cd0884185a0dafe8ff10cd48a874ee7ba18be`

The hash was independently recomputed in the notebook and matched the recorded frozen version.

## Audit Scope

The audit includes:

- Schema and data-type checks
- Range and validity checks
- Missingness checks
- Duplicate-row and duplicate-date checks
- IQR-based anomaly screening
- Logical consistency checks
- Target-leakage checks
- Predictor correlation and redundancy checks
- Regression diagnostics
- Reproducibility and environment checks
- Bias and measurement limitations
- Claim boundaries

## Main Analysis

The adjusted model examines the association between daily rental demand and:

- Temperature
- Humidity
- Windspeed
- Weather situation
- Year
- Month
- Weekday
- Working-day status

The variables `casual` and `registered` were excluded as predictors because they are direct components of the target `cnt` and therefore would create target leakage.

## Main Result Boundary

The adjusted model explains 82.9% of the observed variation in daily rental demand (R² = 0.829). Within the observed dataset, normalized temperature was positively associated with daily rental demand, while normalized humidity and windspeed were negatively associated with demand.

These are associations, not causal effects. The data are observational daily aggregates from 2011–2012. Diagnostic checks also identified heteroscedasticity and residual serial correlation.

The findings should not automatically be generalized to other cities, bike-sharing systems, or time periods.

## Reproducibility

Main software environment:

- Python 3.13.15
- pandas 2.2.3
- NumPy 2.1.3
- Matplotlib 3.10.0
- statsmodels 0.15.0

The required package versions are recorded in `requirements.txt`.

## Raw Evidence

The `outputs/` directory contains the audit tables, model results, diagnostic results, environment information, and frozen-data hash verification.

## AI Use

ChatGPT was used as a methodological and writing assistant. Numerical results were verified by executing the analysis code in the notebook. AI was not treated as a substitute for execution or independent verification.
