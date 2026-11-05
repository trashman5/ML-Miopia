# ML-Miopia

Machine learning project to predict myopia in third-year medical students at the University of Navarra.

## Goal

From each student's lifestyle, family history, CUVAF and eye biometry data, predict four labels for the test set:

| Label  | Type        | Classes                                                  |
|--------|-------------|----------------------------------------------------------|
| M      | Binary      | SI / NO (myopia)                                         |
| MM     | Binary      | SI / NO (myopia magna, more than 6 dioptres)             |
| Combo  | Multi-class | C (control), M (myopia), MM (myopia magna)               |
| DCombo | Multi-class | C, M1, M2, MM (the M class split in two)                 |

## Models

SVM, XGBoost, Random Forest and Logistic Regression. All four are compared with repeated nested cross-validation, and the best model is used for each label.

## Project structure

| File | Content |
|------|---------|
| `miopia_together.ipynb` | Main notebook: data analysis, features, models, comparison and predictions |
| `data/` | `X_train.csv`, `Y_train.csv`, `X_test.csv` |
| `predictions_step1_svm_xgb.csv` | Predictions from SVM / XGBoost, with the consistency step |
| `predictions_step2_rf_logreg.csv` | Predictions from Random Forest / Logistic Regression |
| `predictions_step3_best_model.csv` | Predictions from the best of the four models for each label |

> **Note:** the `predictions_*.csv` files are not uploaded to the repository. They are generated when you run the notebook.

## Setup

    python3 -m venv .ML
    .ML/bin/pip install -r requirements.txt

Then open `miopia_together.ipynb` and choose the `.ML` kernel. Use the pinned versions, because other versions (for example pandas 2.x) can change the results.
