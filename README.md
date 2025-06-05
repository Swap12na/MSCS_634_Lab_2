# Lab 2: Classification Using KNN and RNN Algorithms
**Name:** *Swarna Anjani Devershetty*

**Course:** MSCS 634 - Machine Learning

**Lab Title:** Classification Using KNN and RNN Algorithms

**Repository:** `MSCS_634_Lab_2`
---
##  Lab Overview
This lab focuses on implementing and evaluating two instance-based classifiers:
- **K-Nearest Neighbors (KNN)**
- **Radius Neighbors (RNN)**
We use the **Wine dataset** from the `sklearn.datasets` module, which includes 178 samples categorized into three classes of wine based on 13 chemical attributes. The aim is to understand how model parameters—specifically **k (number of neighbors)** for KNN and **radius** for RNN—affect classification accuracy.
---
##  Implementation Steps
### Step 1: Load and Prepare the Dataset
- Loaded the Wine dataset and performed basic data exploration.
- Observed the feature names and class distributions.
- Split the dataset into **80% training** and **20% testing** using `train_test_split` with stratified sampling.
### Step 2: K-Nearest Neighbors (KNN)
- Evaluated model accuracy for `k` values: **1, 5, 11, 15, 21**.
- Trained each KNN model on training data and tested it on the test set.
- Logged the accuracy of each configuration.
### Step 3: Radius Neighbors (RNN)
- Tested `radius` values: **350, 400, 450, 500, 550, 600**.
- Used `weights='distance'` to reduce the impact of distant neighbors.
- Set `outlier_label=2` to handle test points with no neighbors in the given radius.
- Measured and recorded model accuracy for each radius value.
### Step 4: Visualize and Compare Results
- Plotted **Accuracy vs k** for KNN.
- Plotted **Accuracy vs radius** for RNN.
- Added insights comparing both models.
---
##  Results & Accuracy Trends
- **KNN Results:**
  Accuracy generally improved with increasing `k` up to a certain point (peak performance typically around `k=5–11`) and then stabilized.
- **RNN Results:**
  Accuracy fluctuated more due to sensitivity to radius choice. Extremely small or large radius values affected performance negatively.
---
##  Key Observations
- **KNN** is easier to tune with interpretable parameters and works well on structured datasets.
- **RNN** can be helpful when data density is uneven but requires careful radius tuning.
- Scaling the data may be necessary for better performance, especially in RNN.
---
##  Challenges Faced
- Choosing meaningful **radius values** was non-intuitive; required trial-and-error.
- Some radius values failed to classify test samples, requiring `outlier_label` for fallback handling.
- Model performance was sensitive to scaling and parameter granularity.
---
