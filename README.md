# Machine Learning Assignment 2

This repository contains all the code used to complete the assignment, including the original dataset to allow everything to be easily run.

Each notebook contains code and some information about what the code does. All outputs and figures are generated upon running their respective cells.

## How to use
The order of executing the notebooks matters.
The intended order is:
1. [S1-UnderstandData.ipynb](S1-UnderstandData.ipynb) - Understand the dataset; what it contains and the meaning.
2. [S2-ExploreData.ipynb](S2-ExploreData.ipynb) - Analyze the various features.
3. [S3-TrainTestSplit.ipynb](S3-TrainTestSplit.ipynb) - Generates a train and test dataset into the `generated/` directory.
4. [S4S5S6S7.ipynb](S4S5S6S7.ipynb) - Uses a single pipeline to represent and later analyze a **Logistic Regression** model with a few different pipelines. This is 4 steps in 1 as it is difficult to share the same pipeline across multiple files. 
5. [S8-Conclusion.md](S8-Conclusion.md) - Contains no code, just a conclusion.

#### Note
Everything (except the `readme.md`) in the `generated/` directory contains files created by scripts.

## Dependencies
Despite it being quite easy to read, this is solely for convenience.
- numpy
- pandas
- Matplotlib
- scikit-learn

<br/><br/>

## Results & Answers to Assignment Questions
### Q1
Class 0 = no diabetes; class 1 = prediabetes or diabetes. The target is imbalanced: ~86% class 0, ~14% class 1. This matters because high accuracy can hide a model that never predicts class 1. Evaluation requires precision, recall, and a confusion matrix to assess the true performance on the minority class.

### Q2
BMI (numerical): measured Body Mass Index, 12-98.

HighBP (binary): 0 = no, 1 = has high blood pressure.

GenHlth (ordinal): 1 = excellent to 5 = poor.

Same number formats with different meanings. BMI is continuous, HighBP is a binary yes/no, and GenHlth is ordered labels with no fixed distance between values. Treating them all as numbers leads to wrong preprocessing.

### Q3
You explored all input features. Which three to five findings were most informative or interesting?
What did you observe? What can you conclude from these results, and what can you not conclude?

### Q4
TEST must remain separate so that evaluation measures true performance on unseen data. If preprocessing or model fitting uses TEST information, scores become overly optimistic and do not reflect how the model would perform on new patients.

### Q5

False positive: predicted diabetes (class 1), but actually no diabetes (class 0), which causes unnecessary concern and potential follow-up costs. False negative: predicted no diabetes (class 0), but actually has prediabetes/diabetes (class 1) which is a missed opportunity for intervention.

- Accuracy: overall correct predictions. 

- Precision: of those predicted class 1, how many truly are. 

- Recall: of actual class 1, how many were found.

Accuracy alone is not enough because with ~86% class 0, a model predicting all zeros achieves 86% accuracy while catching zero diabetes cases.

---

### Q6

Lowering the threshold from 0.50 to 0.40 means more predictions become class 1. This increases recall (more actual diabetes cases found) but decreases precision (more false positives among predicted positives). False negatives decrease while false positives increase. What does not change is the fitted model coefficients, predicted probabilities, accuracy of the underlying model, or the ROC AUC. Only the classification threshold changes.

| Threshold | Accuracy | Precision | Recall | F1 | False positives | False negatives |
|:---|:---|:---|:---|:---|:---|:---|
| 0.50 | 0.8632	| 0.5310 | 0.1573 | 0.2427 | 1473 | 8936 |
| 0.40 | 0.8578	| 0.4819 | 0.2703 | 0.3463 | 3081 | 7738 |

At 0.50 the model is more conservative, catching fewer diabetes cases but with higher confidence. At 0.40 the model is more sensitive, flagging more potential cases for follow-up at the cost of more false alarms.

---

### Q7

From the data and Logistic Regression model we learned that diabetes presence is associated with features such as BMI, high blood pressure, and general health rating. The model can identify patterns in survey responses that correlate with diabetes risk. However, this is association not causation.

Limitations
1. Survey data is self-reported and may contain bias or inaccuracies.
2. The target combines prediabetes and diabetes into a single class, so the model cannot distinguish between these two conditions.
3. The dataset lacks temporal information, so we cannot determine whether features changed before or after diabetes onset.

---

### G1

| Member | Contribution |
|:---|:---|
| Oscar | S1 and questions |
| Wiktor | Data splitting and encoding |
| Wiktor | Model usage and testing |
| Wiktor | Merge Conflict Resolver |
| Emil | Implementation of data preparation |
| Emil | Exploratory Data Analysis |
| Group effort | Decision regarding data preparation |

---

### G2

We worked together in the same room, making it possible to follow what others were working on and to explain the reasoning behind each part. Since every member depended on code written by others, we had to learn how those parts worked in order to use them. The most important decisions made as a group concerned which features to use and which type of encoding to apply.

We aimed to distribute the work as evenly as possible, but there was overlap between tasks. The distribution was not entirely equal, although each member contributed meaningfully to the final solution.

 
