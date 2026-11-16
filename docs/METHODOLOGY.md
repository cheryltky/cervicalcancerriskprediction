# Methodology

All figures below are taken from the notebook's printed outputs.

## Preparation

1. Load the CSV: 858 rows, 36 columns, all columns reporting 858 non-null
   values because missing entries are stored as the string `?`.
2. Replace `?` with missing values. Non-null counts then range from 71 to 858.
3. Drop `STDs: Time since first diagnosis` and `STDs: Time since last
   diagnosis` (71 non-null each, more than 80% missing). 34 columns remain.
4. Convert all columns to numeric (24 float, 10 integer).
5. Fill remaining missing values with the column mean.
6. Separate the target `Biopsy` from 33 input columns, giving an input shape
   of (858, 33) and a target shape of (858,).
7. Standardise inputs with `StandardScaler`.

The 33 input columns include the Hinselmann, Schiller and Citology results,
which are themselves screening tests. This is the main design concern and is
discussed in the README recommendations.

## Model

`XGBClassifier` with the binary logistic objective. The first run printed
these settings: learning rate 0.1, maximum depth 5, 10 trees, default
regularisation. The notebook does not print the settings of the second run.

## Two runs

| Run | Test patients | Positives in test | Train accuracy | Test accuracy |
|---|---|---|---|---|
| First | 86 | 4 | 0.9752 | 0.9419 |
| Second (reported in README) | 215 | 13 | 0.9984 | 0.9581 |

The second run is the one in the README because it has the larger test set
and matches the figures in the original README.

## Second run, classification report

| Class | Precision | Recall | F1 | Support |
|---|---|---|---|---|
| 0 (negative) | 0.99 | 0.97 | 0.98 | 202 |
| 1 (positive) | 0.61 | 0.85 | 0.71 | 13 |
| Macro average | 0.80 | 0.91 | 0.84 | 215 |

Confusion matrix (rows predicted, columns actual): 195 true negatives, 2
false negatives, 7 false positives, 11 true positives.

First run, for comparison: precision 0.44 and recall 1.00 for the positive
class on 4 positives, with 5 false positives. The small support makes the
perfect recall unreliable.

## Not done

Cross-validation, hyperparameter search, feature importance output, a
history-only model, and any external validation. The original README listed
cross-validation, feature engineering and tuning as future work, and a
feature importance chart that does not exist in the notebook outputs.
