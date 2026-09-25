Pediatric Complexity Score

This repository contains the trained XGBoost models and example code for calculating the Pediatric Complexity Score (PCS).

The PCS ranges from 0 to 100, with higher scores indicating greater predicted complexity.

Repository contents:

models/
- y_gt_0.ubj
- y_gt_1.ubj
- y_gt_2.ubj

metadata/
- predictors.csv
- complexity_icd10_codes.csv
- codelist.xlsx

R/
- preprocess_diagnoses.R
- predict_complexity.R

Model

The model uses three Frank-Hall cumulative ordinal XGBoost classifiers estimating:

P(Y > 0)
P(Y > 1)
P(Y > 2)

These probabilities are converted into four class probabilities and then into a continuous PCS ranging from 0 to 100.

PCS categories

Less than 10: Low complexity

10 to less than 55: Mild complexity

55 to less than 95: Moderate complexity

95 or greater: Severe complexity

Implementation

The required predictor names and order are contained in metadata/predictors.csv.

Diagnosis preprocessing code is provided in R/preprocess_diagnoses.R.

Model scoring code is provided in R/predict_complexity.R.

The trained models are stored in XGBoost UBJ format.

Data

Patient-level development data are not included in this repository.

License

Apache License 2.0.
