Jigsaw Agile Community Rules — Community Crisis Prevention System

Project outline

* Purpose: Predict subreddit rule violations to help moderators act faster.

* What’s here: End-to-end workflow, Kaggle-safe notebooks, 42 lightweight text features, TF-IDF + Logistic Regression baseline, XGBoost path, and submission scripts.

Data

* Place train.csv, test.csv, and sample\_submission.csv in data/raw/.
* Notebooks auto-detect paths locally and on Kaggle (so that there's no need to mirror Kaggle folders exactly).

Quickstart (local)

* Use Python 3.10+.
* Create a clean env and install: numpy<2, pandas, scikit-learn, scipy, xgboost, matplotlib.
* Run notebooks in numerical order.

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
