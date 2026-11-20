# Customer Churn Prediction — CPCS 433 Course Project

Predicting customer churn on the Iranian Churn dataset (UCI Machine Learning Repository) with two models trained and tested on the same split:

- **Pair A:** Logistic Regression
- **Pair B:** Random Forest

## Repository contents

| File | What it does |
| --- | --- |
| `01_data_preparation.ipynb` | Cleans the data, selects the ten features, and makes the 70/15/15 split |
| `02_logistic_regression.ipynb` | Trains, tunes and evaluates Logistic Regression |
| `03_random_forest.ipynb` | Trains, tunes and evaluates Random Forest |
| `04_comparison.ipynb` | Compares both models: metrics, curves, error analysis and interpretation |

## Dataset

Iranian Churn Dataset, UCI Machine Learning Repository (CC BY 4.0): https://archive.ics.uci.edu/dataset/563/iranian+churn+dataset (DOI: 10.24432/C5JW3Z). 3150 rows, 14 columns.

## How to run

The notebooks run on **Google Colab** and read and save their files in Google Drive. No installation is needed: all the libraries are already available in Colab.

1. Download the dataset, unzip it, and keep the file `Customer Churn.csv` (the name must match exactly).
2. In Google Drive, create this folder structure inside **My Drive** and upload the CSV file:
   ```
   My Drive/
   └── churn_project/
       └── data/
           └── Customer Churn.csv
   ```
3. Open `01_data_preparation.ipynb` in Google Colab (**File → Upload notebook**) and choose **Runtime → Run all**. Allow Colab to access Google Drive when asked.
4. Repeat for the other notebooks **in order: 01 → 02 → 03 → 04**. Each notebook reads the files saved by the one before it.

The notebooks create the rest automatically:

- `churn_project/data/splits/`: the train, validation and test files and the split indices
- `churn_project/results/`: all tables (CSV) and charts (PNG)

## Reproducibility

- Library versions are saved by Notebook 1 in `results/library_versions.txt`.
- Fixed random seed `433` for the split and the models.
- Duplicate rows are grouped into profiles so the same profile never appears in two splits.
- Hyperparameters and the classification threshold are selected on the validation set only; the test set is used once for the final evaluation.
