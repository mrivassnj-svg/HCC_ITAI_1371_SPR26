1. Project Overview
A-PIG-IMPACT is a machine learning classification project designed to identify high-risk disease outbreaks in swine populations using the EMPRES Global Animal Disease Surveillance dataset.  

2. Data Source
Due to file size constraints, the raw dataset is accessed via KaggleHub:

Dataset URL: EMPRES Global Animal Disease Surveillance

  

Target File: Outbreak_240817.csv

  

3. Methodology Summary
Data Split: Strictly adhered to the 70% Train, 15% Validation, and 15% Test requirement.  

Models Trained: Logistic Regression, Decision Tree, Random Forest, Gradient Boosting, KNN, and SVC.  

Ensembles: Included a Voting Classifier (incorporating the top 3 performers) and a Bayesian Model (Gaussian Naive Bayes).  

4. Results Highlights
As documented in the Deliverables/Model_Comparison_Table.pdf, the ensemble and tree-based models achieved the highest F1-Scores, which was the primary metric for balancing outbreak detection (Recall) and diagnostic accuracy (Precision).  

5. Student Contribution (MANDATORY)
This project was completed individually. Key contributions include:  

End-to-end Python pipeline development.  

Custom PDF generation engine for automated reporting.  

Implementation of geographic feature engineering for swine outbreak clusters.
