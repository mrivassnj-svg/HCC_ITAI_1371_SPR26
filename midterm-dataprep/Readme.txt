# Midterm Data Preparation Project
## CTU-IoT-Malware-Capture-8 Dataset

### Technical Lead 1: Michael
Role: Data Ingestion, Cleaning, and Preprocessing Pipeline

---

# Overview

This notebook implements the **initial data preparation pipeline** for the CTU-IoT-Malware-Capture-8 dataset.  
The objective is to transform the **raw dataset into a machine learning ready format** while following the requirements outlined in the course midterm project.

All preprocessing operations were performed **programmatically** to ensure the original dataset remains unchanged.

The cleaned dataset will serve as the **foundation for Exploratory Data Analysis (EDA), feature analysis, and model development** performed by the remaining team members.

---

# Dataset Source

Original Dataset:
CTU-IoT-Malware-Capture-8

The dataset contains network traffic information collected from IoT devices infected with malware.  
The goal of this dataset is to identify **malicious network activity using machine learning techniques**.

---

# Data Processing Steps Completed

The following preprocessing operations were implemented in this notebook.

## 1. Dataset Loading

The raw dataset was loaded directly into the Python environment.


The original file was **not modified manually** to comply with assignment requirements.
/content/CTU-IoT-Malware-Capture-8-1conn_Use_this_one-1.csv
---

# 2. Removal of Problematic Features

Certain columns were removed based on dataset analysis and domain knowledge.

### Removed Columns

**id.resp_p**

Reason:
Malicious traffic consistently uses TCP port 50.  
If retained, the machine learning model could learn this shortcut rather than detecting malicious behavior from meaningful features.

**history**

Reason:
This column contains complex categorical patterns that significantly increase dimensionality while providing limited predictive value for this stage of the project.

---

# 3. Data Type Conversion

The `duration` column contained text values and missing data.

It was converted to numeric format using:
pd.to_numeric(errors="coerce")


Missing values were replaced with the **median value** of the column.

This ensures numerical consistency for machine learning algorithms.

---

# 4. Categorical Data Cleanup

The `service` column contained placeholder values represented by "-".

These placeholders were replaced with:
"Unknown"


This preserves the category while allowing it to be encoded later during the feature engineering stage.

---

# 5. Training and Testing Dataset Split

The dataset was divided into two subsets:

Training dataset: 70%  
Testing dataset: 30%

This split ensures that:

• Exploratory Data Analysis (EDA) is performed only on training data  
• The testing dataset remains untouched for future evaluation

Implementation:
train_test_split(test_size=0.30, random_state=42)


---

# 6. Handling Missing Values

All numeric columns were scanned for missing values.

Missing values were replaced using the **median of each column**, which is less sensitive to outliers than the mean.

---

# 7. Feature Engineering

Two derived features were created to provide additional behavioral insight into network traffic patterns.

### bytes_per_packet

Represents the average number of bytes transmitted per packet.
bytes_per_packet = orig_bytes / (orig_pkts + 1)


These features help capture **traffic intensity and communication behavior**, which are useful indicators of malicious activity.

---

# 8. Removal of High Cardinality Identifiers

The following identifiers were removed before encoding:
uid
id.orig_h
id.resp_h


These fields represent unique identifiers and IP addresses that would create thousands of unnecessary encoded columns.

Removing them improves model generalization.

---

# 9. Categorical Encoding

Categorical variables were transformed into machine learning compatible features using **one-hot encoding**.
pd.get_dummies()


This converts categorical labels into binary feature vectors.

---

# 10. Feature Scaling

All numeric features were standardized using:
StandardScaler()


Scaling ensures that features have:

Mean = 0  
Standard Deviation = 1

This improves performance for many machine learning algorithms.

---

# Output Files

Processed datasets are stored in the project directory structure.
ml_midterm_project/

data/
├── raw/
│
└── processed/
├── train_clean.csv
└── test_dataset.csv

figures/

notebooks/

reports/


### Training Dataset
test_dataset.csv


This dataset remains **untouched** and will be used later for **model evaluation and validation**.

---

# Next Steps for the Team

The remaining stages of the project will be completed by the other team members.

---

## Technical Lead 2

Responsibilities:

• Validate feature engineering results  
• Identify additional derived features  
• Prepare dataset for machine learning models  
• Ensure feature consistency between training and testing datasets

---

## EDA and Visualization Lead

Responsibilities:

Perform exploratory data analysis **using the training dataset only**.

Recommended analyses:

• Feature distributions  
• Correlation matrix  
• Class imbalance analysis  
• Malicious vs benign traffic patterns  
• Outlier detection

Visualizations should be saved to:
figures/


---

## Documentation and Reporting Lead

Responsibilities:

Prepare the final documentation required for submission.

Deliverables include:

• Dataset description document  
• Project proposal  
• Reflection journal describing each team member’s contribution  
• GitHub repository organization  
• README documentation

---

# Alignment with Course Requirements

This notebook satisfies the following project requirements:

✔ Filling NaN and Null values  
✔ Scaling numerical features  
✔ Encoding categorical variables  
✔ Feature engineering  
✔ Train/Test dataset split (70/30)  
✔ Dataset preparation for machine learning  
✔ Preservation of the original dataset  

---

# Author Contribution

Michael  
Technical Lead 1

Responsibilities completed:

• Data ingestion pipeline  
• Dataset cleaning  
• Feature preparation  
• Missing value handling  
• Feature engineering  
• Categorical encoding  
• Feature scaling  
• Training/testing dataset split  
• Preparation of ML-ready dataset

This pipeline establishes the foundation for all subsequent analysis and modeling tasks performed by the team.

---
