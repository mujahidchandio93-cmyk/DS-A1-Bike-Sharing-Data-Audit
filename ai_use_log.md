# AI Use and Independent Verification Log

## AI tool used

ChatGPT was used as a methodological and writing assistant during the audit.

## Tasks supported by AI

* Clarifying assignment requirements and audit workflow.
* Helping define the research question, stakeholder, population, sample, unit, target, and estimand.
* Suggesting data-quality checks for schema, ranges, missingness, duplicates, anomalies, and leakage.
* Helping interpret statistical diagnostics and identify claim boundaries.
* Helping organize reproducibility outputs and documentation.
* Reviewing wording for clarity and avoiding causal claims from observational data.

## AI advice accepted

Suggested audit structure, leakage checks, diagnostic checks, reproducibility documentation, and cautious interpretation of associations were used where they matched the assignment requirements and actual notebook results.

## AI advice rejected or corrected

AI-generated variable names and code were not assumed to exist. When suggested variables were unavailable, tables were recreated from the actual frozen dataset. An initial model showed rank deficiency and was not treated as the final model; the model specification was revised after checking the actual output.

## Independent verification

All reported numerical results were independently verified by executing Python code in the notebook and checking the resulting tables, model output, diagnostic tests, and dataset hash. The frozen `day.csv` SHA-256 hash matched the recorded frozen version. AI was not used as a substitute for execution or verification.
