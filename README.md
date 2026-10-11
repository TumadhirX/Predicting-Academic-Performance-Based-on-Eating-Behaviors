# Predicting Academic Performance Based on Eating Behaviors

A machine learning project exploring university students’ eating behaviors and lifestyle habits to classify academic performance into low, medium, and high GPA categories. Developed for **DS323: Machine Learning** at Princess Nourah University.

## Overview

The project follows the CRISP-DM framework and compares **Logistic Regression**, **Support Vector Machine (SVM)**, and **Random Forest** using pandas and scikit-learn.

The notebook includes exploratory visualizations, missing-value handling, a correlation heatmap, a stratified 70/30 train/test split, confusion matrices, classification reports, a scaling experiment, and manual hyperparameter grid searches with five-fold cross-validation.

## Repository contents

| File | Description |
| --- | --- |
| [DS323_ProjectFinal.ipynb](DS323_ProjectFinal.ipynb) | Original analysis, training code, and recorded outputs |
| [Students outcome based on eating behaviors.csv](Students%20outcome%20based%20on%20eating%20behaviors.csv) | Survey dataset with 200 rows and 15 columns |
| [Academic_Performance_Report.pdf](docs/Academic_Performance_Report.pdf) | Project methodology, results, and survey questions |
| [requirements.txt](requirements.txt) | Python dependencies |

The notebook and CSV are kept together to preserve the notebook’s relative input path.

## Data and preprocessing

According to the report, data was collected through an online university-student survey and responses were manually encoded numerically. Features cover meal frequency, breakfast, fast food, caffeine, late-night eating, fruit and vegetable consumption, sleep, exercise, study habits, academic year, and working status.

The notebook removes the `ID` column and drops rows missing selected eating-behavior values. GPA classes are encoded as **0 = Low**, **1 = Medium**, and **2 = High**. Original column spelling, trailing spaces, and embedded newlines are retained because the notebook depends on them.

## Run locally

Use Python 3.11 or 3.12:

```bash
git clone https://github.com/TumadhirX/Predicting-Academic-Performance-Based-on-Eating-Behaviors.git
cd Predicting-Academic-Performance-Based-on-Eating-Behaviors
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter lab DS323_ProjectFinal.ipynb
```

On Windows, activate with `.venv\Scripts\activate`. Open the notebook and run cells in order from the repository directory. Dependencies are suggested ranges, since the original files contain no environment lockfile.

## Results recorded in the original notebook

| Model | Default test accuracy | Tuned test accuracy |
| --- | ---: | ---: |
| Logistic Regression | 52.54% | 47.46% |
| SVM | 49.15% | 40.68% |
| Random Forest | 45.76% | 49.15% |

Default Logistic Regression achieved the highest test accuracy. Tuning improved Random Forest but reduced held-out accuracy for Logistic Regression and SVM. The small sample and gaps between training and test performance limit generalization.

The original scaling experiment fits `StandardScaler` before splitting the data, exposing the preprocessing step to test-set information. For future experiments, fit preprocessing on training data within a scikit-learn pipeline. The original notebook is preserved. The analysis identifies associations and does not establish that eating behaviors cause academic outcomes.

## Contributors

Natali Ahmed Shaat, AlShaima Saeed Alotaibi, Lena Ahmed Alghamdi, Tumadhir Alyahya, and Dana Almkhlafi.

## Usage rights

No project or dataset license has been specified. Survey collection and participant consent terms should be considered before reusing the data.
