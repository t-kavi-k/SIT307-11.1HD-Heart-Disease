# SIT307 11.1HD Machine Learning Mini Research

## Project Title

Reproduction and Leakage-Aware Evaluation of a Stacking Ensemble for Heart Disease Prediction

## Selected Research Paper

Bhagat, Sharma and Agarwal  
"An efficient stacking-based ensemble technique for early heart attack prediction"

## Project Overview

This project reproduces the machine learning approach presented in the selected research paper for heart disease prediction.

The study uses six machine learning classifiers:

- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost
- Naive Bayes
- K-Nearest Neighbours

These models are also combined using a stacking ensemble.

During my reproduction, I found that the dataset contained a large number of duplicate records. This caused duplicate data leakage between the training and testing sets.

To improve the evaluation, I removed duplicate records before splitting the data and then used repeated stratified cross-validation to obtain a more reliable estimate of model performance.

## Files Included

- `SIT307_11.1HD_Heart_Disease.ipynb` - Main Jupyter Notebook containing all code, experiments, results and graphs
- `heart.csv` - Heart disease dataset used in the experiment
- `README.md` - Instructions for installing, running and reproducing the project

## Software Requirements

The project requires:

- Python 3
- Jupyter Notebook or JupyterLab

The following Python libraries are used:

- pandas
- numpy
- matplotlib
- scikit-learn
- xgboost

## Installation

Install the required Python libraries using the following command:

```bash
pip install pandas numpy matplotlib scikit-learn xgboost
```

## How to Run the Project

1. Download all project files.
2. Keep `SIT307_11.1HD_Heart_Disease.ipynb`, `heart.csv`, and `README.md` in the same folder.
3. Open Jupyter Notebook or JupyterLab.
4. Open `SIT307_11.1HD_Heart_Disease.ipynb`.
5. Make sure that `heart.csv` is in the same folder as the notebook.
6. Restart the kernel if necessary.
7. Select **Run All Cells**.
8. Wait until all cells finish running.

All tables, graphs and evaluation results should then be reproduced in the notebook.

## Experiment Workflow

The notebook follows these main steps:

1. Load and inspect the heart disease dataset.
2. Check the dataset shape, missing values, target distribution and duplicate records.
3. Prepare and preprocess the data.
4. Train the six individual machine learning classifiers.
5. Evaluate the models using Accuracy, Precision, Recall, F1-score and AUC.
6. Build the stacking ensemble.
7. Compare the reproduced results with the results reported in the selected paper.
8. Investigate the unusually high reproduction results.
9. Check for duplicate data leakage between the training and testing sets.
10. Remove duplicate records before splitting the data.
11. Create a new duplicate-free train-test split.
12. Verify that there is no duplicate overlap between the new training and testing sets.
13. Retrain the models on the duplicate-free data.
14. Use repeated stratified 5-fold cross-validation with five repeats.
15. Compare the published results, Part 1 reproduction results and duplicate-free repeated cross-validation results.
16. Perform Random Forest feature importance analysis.

## Main Findings

The original dataset contained 1,025 records.

A total of 723 duplicate rows were found.

During the Part 1 leakage check:

- Test set size: 205 records
- Test records also represented in the training set: 202
- Training-test overlap: 98.54%

This showed that duplicate data leakage strongly affected the original reproduction results.

After removing duplicates:

- Original dataset size: 1,025 records
- Duplicate-free dataset size: 302 unique records
- Duplicate overlap between clean training and testing sets: 0 records

The stacking ensemble achieved 100% accuracy in the Part 1 reproduction.

On the single duplicate-free train-test split, the stacking ensemble achieved approximately 75.4% accuracy.

For the final evaluation, repeated stratified 5-fold cross-validation with five repeats was used.

This produced 25 validation runs for each model.

The stacking ensemble achieved:

- Mean Accuracy: approximately 82.9%
- Standard Deviation: approximately 3.6%
- Precision: approximately 82.5%
- Recall: approximately 87.7%
- F1-score: approximately 84.8%
- AUC: approximately 90.4%

The results show that the extremely high Part 1 performance decreased after duplicate leakage was removed.

## Reproducibility

Fixed random states are used where possible to make the experiment reproducible.

For models that are sensitive to feature scale, `StandardScaler` is fitted only to the training data or used inside the cross-validation pipeline.

The same dataset, model types and evaluation methods used in the submitted report are included in the notebook.

## Main Conclusion

The main finding from this project is that very high machine learning accuracy does not always mean that a model will perform well on unseen data.

Duplicate records and data leakage can produce overly optimistic results.

Removing duplicate records and using repeated cross-validation provides a more realistic and stable estimate of model performance.

## Author

Thamasha Kavindhi Kothalawala

SIT307 - Machine Learning

Deakin University
