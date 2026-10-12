# Machine Learning Assignment 2

This repository contains all code used to complete the assignment, including the original dataset to allow everything to be easily run.

Each notebook contains code and some information about what the code does. All outputs and figures are generated upon running their respective cells.

# How to use
The order of executing the notebooks matters.
The intended order is:
1. `DataAnalysis.ipynb` - Analyze the dataset.
2. `DataSplit.ipynb` - Partially preprocess and split the data into training and test.
3. `DataPreparation.ipynb` - Preprocess the training and test sets.
4. `ModelUsage.ipynb` - Train and test ML models.

#### Note
The `train_set.csv`, `train_set_prepped.csv`, `test_set.csv`, and `test_set_prepped.csv` are all generated `.csv` files, derived from `diabetes_binary_classification_data.csv` using code.

# Dependencies
Despite it being quite easy to read, this is solely for convenience.
- numpy
- pandas
- Matplotlib
- scikit-learn
