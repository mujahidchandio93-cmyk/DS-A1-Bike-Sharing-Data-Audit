# Data Card

## Dataset
UCI Bike Sharing Dataset — `day.csv`

## Source
UCI Machine Learning Repository

Dataset DOI: 10.24432/C5W894

License: CC BY 4.0

## Data Period
2011–2012

## Sample
731 daily observations

## Unit of Analysis
One calendar day

## Stakeholder
Bike-sharing system operator

## Target
`cnt` — total number of daily bike rentals, including casual and registered users.

## Main Variables
The main analysis uses weather and calendar variables including:

- `temp` — normalized temperature
- `hum` — normalized humidity
- `windspeed` — normalized wind speed
- `weathersit` — weather situation category
- `yr` — year indicator
- `mnth` — month
- `weekday` — day of week
- `workingday` — working-day indicator

## Intended Use
To examine associations between observed weather conditions and daily bike-rental demand within the observed Capital Bikeshare data from 2011–2012.

## Out-of-Scope Uses

The dataset should not be used in this audit to:

- establish causal effects of weather on bike-rental demand;
- claim that weather is the sole explanation for changes in demand;
- automatically generalize the results to other cities or bike-sharing systems;
- automatically generalize the results to other time periods.

## Known Limitations

- The observations are daily system-level aggregates.
- Individual users' reasons for renting or not renting are not recorded.
- Other factors affecting demand may not be represented.
- Weather variables are normalized measurements.
- The data cover 2011–2012 and may not represent current bike-sharing behavior.
- Temporal dependence is present in the observations.
- Diagnostic checks detected heteroscedasticity and residual serial correlation.

## Leakage Variables

`casual` and `registered` were excluded from the regression predictors because:

`casual + registered = cnt`

for every observation. Including these variables as predictors would directly expose components of the target.

## Frozen Dataset

File: `day.csv`

Size: 57,569 bytes

SHA-256:

`a6bcf826782d3c0fbfdcbeead17cd0884185a0dafe8ff10cd48a874ee7ba18be`

The hash was independently recomputed and matched the recorded frozen version.
