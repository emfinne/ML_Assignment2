# Machine Learning Assignment 2

This repository contains all the code used to complete the assignment, including the original dataset to allow everything to be easily run.

Each notebook contains code and some information about what the code does. All outputs and figures are generated upon running their respective cells.

## How to use
The order of executing the notebooks matters.
The intended order is:
1. `DataAnalysis.ipynb` - Analyze the dataset.
2. `DataSplit.ipynb` - Partially preprocess and split the data into training and test.
3. `DataPreparation.ipynb` - Preprocess the training and test sets.
4. `ModelUsage.ipynb` - Train and test ML models.

#### Note
The `train_set.csv`, `train_set_prepped.csv`, `test_set.csv`, and `test_set_prepped.csv` are all generated `.csv` files, derived from `diabetes_binary_classification_data.csv` using code.

## Dependencies
Despite it being quite easy to read, this is solely for convenience.
- numpy
- pandas
- Matplotlib
- scikit-learn

## Questions
### Q1
Class 0 = no diabetes; class 1 = prediabetes or diabetes. The target is imbalanced: ~86% class 0, ~14% class 1. This matters because high accuracy can hide a model that never predicts class 1. Evaluation requires precision, recall, and confusion matrix to assess true performance on the minority class.

### Q2
BMI (numerical): measured Body Mass Index, 12-98.

HighBP (binary): 0 = no, 1 = has high blood pressure.

GenHlth (ordinal): 1 = excellent to 5 = poor.

Same number format, different meanings. BMI is continuous, HighBP is yes/no, GenHlth is ordered labels with no fixed distance between values. Treating them all as numbers leads to wrong preprocessing.

### Q3
You explored all input features. Which three to five findings were most informative or interesting?
What did you observe? What can you conclude from these results, and what can you not conclude?

### Q4
TEST must remain separate so that evaluation measures true performance on unseen data. If preprocessing or model fitting uses TEST information, scores become overly optimistic and do not reflect how the model would perform on new patients.

### Q5
False positive: predicted diabetes (class 1), but actually no diabetes (class 0) — unnecessary concern and potential follow-up costs. False negative: predicted no diabetes (class 0), but actually has prediabetes/diabetes (class 1) — missed opportunity for intervention.

Accuracy: overall correct predictions. Precision: of those predicted class 1, how many truly are. Recall: of actual class 1, how many were found.

Accuracy alone is not enough because with ~86% class 0, a model predicting all zeros achieves 86% accuracy while catching zero diabetes cases.
### Q6
### Q7
### G1
### G2
