# Data Dictionary

| Variable | Type | Description | Role / Notes |
|---|---|---|---|
| `instant` | Integer | Record index | Identifier; not used as an analysis predictor |
| `dteday` | Date/string | Calendar date | Date identifier; one unique date per observation |
| `season` | Integer | Season category coded 1–4 according to the dataset documentation | Calendar variable |
| `yr` | Integer | Year indicator: 0 = 2011, 1 = 2012 | Calendar variable |
| `mnth` | Integer | Month, coded 1–12 | Calendar variable |
| `holiday` | Integer | Holiday indicator | Calendar variable |
| `weekday` | Integer | Day-of-week category, coded 0–6 | Calendar variable |
| `workingday` | Integer | 1 if neither weekend nor holiday; otherwise 0 | Calendar variable |
| `weathersit` | Integer | Weather situation category | Weather variable; frozen daily data contain observed categories 1–3 |
| `temp` | Float | Normalized temperature measurement | Weather predictor |
| `atemp` | Float | Normalized feeling-temperature measurement | Weather variable; highly correlated with `temp` |
| `hum` | Float | Normalized humidity measurement | Weather predictor |
| `windspeed` | Float | Normalized wind-speed measurement | Weather predictor |
| `casual` | Integer | Count of casual users | Component of `cnt`; excluded as predictor to prevent target leakage |
| `registered` | Integer | Count of registered users | Component of `cnt`; excluded as predictor to prevent target leakage |
| `cnt` | Integer | Total number of rental bikes, including casual and registered users | Target variable |

## Notes

The frozen `day.csv` file contains 731 daily observations and 16 variables.

The README for the dataset defines additional weather-category information for `weathersit`; however, the frozen daily file used in this audit contains only categories 1, 2, and 3.

The hourly variable `hr` is not present in `day.csv` and was therefore not included in this analysis.

The weather variables are normalized measurements rather than direct physical-unit values in the analysis file. Therefore, regression coefficients for `temp`, `hum`, and `windspeed` are interpreted per unit of the normalized variable rather than directly as degrees Celsius, percentage humidity, or physical wind-speed units.
