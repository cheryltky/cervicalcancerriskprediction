# Setup

The original work ran on Python 3.7 with XGBoost 1.3.0; the notebook metadata
records a Python 3.10 kernel. Any recent Python 3 with the packages in
`requirements.txt` should work.

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab notebooks/01-xgboost-risk-model.ipynb
```

## Known limitation

The committed notebook keeps its printed outputs and charts, but many code
cells contain only comments or are empty (for example the CSV load, the
train/test split and the model definition). It therefore cannot be run from
top to bottom as it stands, and no CSV read path appears in its source. When
restoring the load step, read the file from `data/cervical-cancer-risk.csv`
with `na_values="?"` or replace `?` with missing values afterwards.

The notebook also contains `!pip install` lines and a `jupyterthemes` dark
theme; neither is needed to reproduce the results.

## Repository layout

```
cervicalcancerriskprediction/
  README.md            the case study
  assets/              charts used by the README
  data/                CSV and source note
  notebooks/           01-xgboost-risk-model.ipynb
  docs/                SETUP.md, METHODOLOGY.md
  requirements.txt
```
