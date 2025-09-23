Jigsaw Agile Community Rules — Community Crisis Prevention System

Project outline

* Purpose: predict subreddit rule violations to help moderators act faster.

* What’s here: end-to-end ML workflow (EDA → baseline → features → advanced), Kaggle-safe notebooks, 42 lightweight text features, TF-IDF + Logistic Regression baseline, XGBoost path, and submission scripts.

Data

* Place train.csv, test.csv, and sample\_submission.csv in data/raw/.
* Notebooks auto-detect paths locally and on Kaggle (no need to mirror Kaggle folders exactly).

Quickstart (local)

* Use Python 3.10+.
* Create a clean env and install: numpy<2, pandas, scikit-learn, scipy, xgboost, matplotlib.
* Run notebooks in order: 01\_EDA → 02\_baseline\_models → 03\_feature\_engineering → 04\_advanced\_models.

Quickstart (Kaggle)

* Duplicate the notebook, set Internet: OFF.
* Ensure the notebook writes /kaggle/working/submission.csv.
* Submit the version that produced submission.csv.

Repository structure
jigsaw-competition/
├─ data/
│  ├─ raw/                      (train.csv, test.csv, sample\_submission.csv)
│  └─ processed/                (engineered features, splits)
├─ notebooks/
│  ├─ 01\_EDA.ipynb
│  ├─ 02\_baseline\_models.ipynb
│  ├─ 03\_feature\_engineering.ipynb
│  └─ 04\_advanced\_models.ipynb
├─ models/                      (saved models, optional)
├─ submissions/                 (local CSVs)
├─ results/                     (MI ranks, error analysis, scores log)
└─ docs/                        (executive summary, technical report, datasheet, model card)

Notes

* 03\_feature\_engineering builds 42 platform/tone/structure features and can also produce a Kaggle-ready submission.csv if needed.
* 04\_advanced\_models stacks TF-IDF + features and trains XGBoost with early stopping; logs validation F1.

Troubleshooting

* Kaggle “no submission.csv”: submit the latest notebook version that writes /kaggle/working/submission.csv.
* Format errors: columns must match sample\_submission.csv; IDs in the same order; targets are 0/1 integers; no NaNs.
* Local NumPy/Pandas issues: prefer a fresh env with numpy<2 to avoid binary mismatches.
