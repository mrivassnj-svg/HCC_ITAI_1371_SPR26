## 1. Project Overview

A-PIG-IMPACT is a machine learning–based classification project developed to identify high-risk disease outbreaks in swine populations. The model leverages the EMPRES Global Animal Disease Surveillance dataset to detect patterns associated with outbreak severity and transmission risk.

---

## 2. Data Source

Due to file size limitations, the dataset is accessed programmatically via KaggleHub.

- **Dataset:** EMPRES Global Animal Disease Surveillance  
- **Target File:** `Outbreak_240817.csv`

This dataset contains structured records of animal disease events, including temporal, geographic, and epidemiological attributes relevant to outbreak analysis.

---

## 3. Methodology Summary

The modeling pipeline follows a structured and reproducible workflow:

- **Data Partitioning:**  
  The dataset was split into training (70%), validation (15%), and test (15%) subsets to ensure unbiased model evaluation.

- **Models Implemented:**  
  Logistic Regression, Decision Tree, Random Forest, Gradient Boosting, K-Nearest Neighbors (KNN), and Support Vector Classifier (SVC).

- **Ensemble Techniques:**  
  - A Voting Classifier constructed from the top three performing models based on validation metrics.  
  - A probabilistic baseline using Gaussian Naive Bayes to provide a Bayesian comparison framework.

---

## 4. Results Highlights

As presented in `Deliverables/Model_Comparison_Table.pdf`, ensemble and tree-based methods demonstrated superior performance, particularly in terms of F1-score. This metric was prioritized due to its ability to balance recall (sensitivity to outbreak detection) and precision (reduction of false positives), which is critical in epidemiological risk classification.

---

## 5. Student Contribution (Mandatory)

This project was completed independently. Primary contributions include:

- Development of a complete end-to-end machine learning pipeline in Python, covering data ingestion, preprocessing, model training, evaluation, and comparison.  
- Design and implementation of a custom PDF generation workflow to automate the creation of structured analytical reports and result summaries.
Implementation of geographic feature engineering for swine outbreak clusters.
