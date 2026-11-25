# Heart disease prediction: decision tree and logistic regression from scratch

Machine Learning project (instructor: Alassane Diallo). Authors: Adarsh, Sean and Saathvika.

We predict whether a patient has heart disease from routine clinical measurements. A **decision tree** (Gini impurity) and a **logistic regression** (batch gradient descent) are implemented from scratch with NumPy and compared with the scikit-learn versions on identical data and folds, using 5-fold cross-validation and a held-out test set.

## Files
| File | Purpose |
|---|---|
| `heart_disease_ml.ipynb` | The whole project: data, preprocessing, both scratch models, tuning, results, figures |
| `Heart_Disease_ML_Report.pdf` | Written report (source: `report.html`) |
| `figures/` | Figures 1-11 used in the report, written by the notebook |
| `requirements.txt` | Python packages |

## Dataset
Heart Failure Prediction Dataset (fedesoriano, Kaggle): <https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction>
Download `heart.csv` and place it next to the notebook (the file is already in this repository for convenience; check the dataset's licence before redistributing it).

## How to reproduce
1. Create an environment with Python 3.10 or newer and install the packages: `pip install -r requirements.txt`
   (the results were produced with Python 3.13, numpy 2.4.6, pandas 3.1.1, matplotlib 3.11.2, seaborn 0.13.2, scikit-learn 1.9.1).
2. Open `heart_disease_ml.ipynb` and run all cells from top to bottom (about two minutes).
   Or from a terminal: `jupyter nbconvert --to notebook --execute --inplace heart_disease_ml.ipynb`
3. The figures are written to `figures/`.

The random seed is 42 everywhere (train/test split, cross-validation folds, scikit-learn baselines); the scratch models are deterministic. Every number in the report is printed by the notebook; only the fit times in the timing table change slightly between runs.

## Evaluation design in one paragraph
15 % of the patients (138) are kept aside as a test set and used once, at the end. The other 780 patients are used for stratified 5-fold cross-validation to choose hyperparameters and compare models. All preprocessing statistics (imputation medians, means and standard deviations) are fitted on the training part of each fold only.
