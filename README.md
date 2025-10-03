Jigsaw Agile Community Rules — Community Crisis Prevention System

Project Overview:

- Predict subreddit rule violations to help moderators act faster.
- Includes end-to-end ML pipeline: data → features → baseline → advanced models → submission.
- Notebooks are Kaggle-safe and work both locally and on Kaggle.
- Features include ~42 handcrafted text/structural/platform features.
- Models include TF-IDF + Logistic Regression, XGBoost, and ensemble/calibration options.

Repository Structure:

- data/raw/              (train.csv, test.csv, sample_submission.csv)
- data/processed/        (engineered features, splits)
- notebooks/             (01_EDA, 02_baseline, 03_features, 04_advanced, 05_calibration, etc)
- models/                (saved models, checkpoints)
- submissions/           (submission CSVs)
- results/               (logs, error analysis, metrics)
- docs/                  (executive summary, data & model cards)

Setup and Quickstart

Local:

* Python 3.10+
* Install numpy<2, pandas, scikit-learn, scipy, xgboost, matplotlib
* Place data in data/raw/
* Run notebooks in order

Kaggle:

* Internet OFF
* Ensure notebook writes /kaggle/working/submission.csv
* Submit the generated file

Notes

* Feature engineering builds 42 features and can produce submission.csv
* Advanced models stack TF-IDF + features with XGBoost and log validation F1
* Calibration/ensemble improves probability estimates and final performance

Workflow Tips

* Keep raw vs processed data separate
* Version submissions and log results
* Store plots and error analysis in results/
* Ensure the full pipeline runs cleanly and within Kaggle limits

Goals

* Achieve strong validation F1 and fair, interpretable models
* Deliver both course and competition submissions plus documentation: executive summary, technical report, datasheet, model card, visuals
