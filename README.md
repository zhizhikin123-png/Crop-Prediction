Sowing Success: How Machine Learning Helps Farmers Select the Best Crops

Overview

Measuring essential soil metrics such as nitrogen, phosphorous, potassium levels, and pH value is an important part of assessing soil condition. However, it can be expensive and time-consuming, so farmers often need to prioritize which metrics to measure based on their budget.

This project uses machine learning to predict the optimal crop for a field based on its soil measurements, and identifies the single most important feature for predicting the crop. This helps a farmer decide which soil metric is most worth measuring.

Dataset

The dataset, soil_measures.csv, contains the following columns:


N — Nitrogen content ratio in the soil
P — Phosphorous content ratio in the soil
K — Potassium content ratio in the soil
ph — pH value of the soil
crop — the optimal crop for that field (the target variable)


Each row represents the soil measurements of a particular field, and the crop column is the best crop choice for those conditions. There are 22 different crop types, making this a multi-class classification problem.

Approach


Check the data — confirmed there were no missing values and inspected the 22 unique crop types.
Split the data — separated the soil measurements (features) from the crop (target), then split into training and test sets.
Test each feature individually — trained a Logistic Regression model using one soil feature at a time (N, P, K, ph) to see how well each one predicts the crop on its own.
Compare and select — recorded each feature's accuracy and selected the one with the highest score as the best predictive feature.


Tools Used


Python
pandas
scikit-learn (LogisticRegression, train_test_split)


Result

The single most predictive feature was K (Potassium), with a test accuracy of approximately 0.29 (28.6%).

{'K': 0.2863636363636364}

While no single feature predicts the crop with high accuracy on its own (expected, since there are 22 possible crops), potassium was the most informative of the four soil measurements. This suggests that if a farmer could only afford to measure one metric, potassium would be the most useful for predicting the best crop.

What I Learned


How to handle a multi-class classification problem with scikit-learn
The difference between classification and regression, and why accuracy (not RMSE) is the right metric here
How to evaluate the predictive power of individual features
How to structure a full machine learning workflow: load → inspect → split → train → evaluate → select


How to Run


Make sure you have Python with pandas and scikit-learn installed.
Place soil_measures.csv in the same folder as the notebook.
Open notebook.ipynb and run the cells.
