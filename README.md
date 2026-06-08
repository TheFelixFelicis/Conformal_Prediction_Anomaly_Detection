# How Early Can We Tell? – Conformal Prediction for Per-Point Anomaly Detection at a Roundabout Junction

Code for the master's thesis *How Early Can We Tell? Conformal Prediction for
Per-Point Anomaly Detection at a Roundabout Junction* (University of Skövde, 2026).

The pipeline derives a conflict-zone polygon from trajectory density, engineers
trajectory features, builds rule-based anomaly labels, and validates two conformal
anomaly detectors (a per-row feature-based variant and a per-trajectory directed
Hausdorff variant) against a held-out test set, with a lead-time analysis and a
bias audit.

## Data

The trajectory dataset was provided by Viscando and is **not included** in this
repository under the terms of agreement. The notebooks expect a
semicolon-separated CSV named `Slottskogsgatan_tracks_extramerged.csv` with the
fields: `ID`, `Time`, `X`, `Y`, `Speed`, `Type`, `Estimated`.

## Running

Run the notebooks in order, 01 through 08. Each writes intermediate outputs that
the next step reads, so they are not independent:

1. `01_define_conflict_zone` — density-based conflict-zone polygon
2. `02_clean_and_feature_engineer` — cleaning and 39-feature engineering
3. `03_rule_based_labels` — four rule-based anomaly labels
4. `04_discriminative_power` — feature discriminative-power analysis
5. `05_train_cal_test_split` — vehicle-level stratified split
6. `06_conformal_detector` — Variant A and Variant B conformal detectors
7. `07_lead_time_analysis` — early-detection lead time
8. `08_bias_audit` — subgroup bias and fairness audit

It is also possible to download the All_Notebooks.zip file in order to get access to all 
of them in one go.
