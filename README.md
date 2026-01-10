# Network-Intrusion-Detection-System-IDS-

This project implements a machine learning-based Intrusion Detection System (IDS) with the primary objective of developing a practical understanding of basic network security concepts and how supervised learning models can assist in detecting malicious behavior. Rather than focusing on complex models, the project emphasizes security-oriented problem formulation, including the difference between multi-class intrusion detection and binary intrusion detection (normal vs attack).

The system analyzes network traffic records and classifies them either as normal or attack traffic, as well as into specific attack categories in a multi-class setting. This project was developed as part of the Minor Project requirement for the Bachelor of Computer Applications (BCA) program. 

# Dataset 

The project uses the NSL-KDD dataset (filtered, not original version) obtained from Kaggle, and it's divided into two csv files one for training and one for test( KDDTrain_filtered.csv ,
KDDTest_filtered.csv ).
Dataset link ( https://www.kaggle.com/datasets/harmannahal/nsl-kdd-dataset ) 

This version is a cleaned and reduced variant of the original KDDCup’99 dataset, commonly used in academic research for benchmarking IDS models.

# Dataset Description
Each dataset record represents a network connection, described using:
- Numerical features: duration, number of bytes, error rates, etc. 
- Categorical features: protocol type, service, connection flag 

## Labels are :
- normal
- Multiple attack types (e.g., neptune, smurf, satan, guess_passwd, etc.)

To align the project with practical IDS objectives, the dataset was transformed from multi-class labels to binary labels:
- 0 -> Normal traffic
- 1 ->Attack traffic (any type of attack)

In real-world IDS deployments, the primary objective is often to detect whether a connection is malicious or not, rather than identifying the exact attack category.
Multi-class intrusion detection suffers from:
- Severe class imbalance
- Poor detection of rare attack types
- Increased model complexity without proportional security benefits
  
So, the uses of binary classification provides:
- Clearer interpretation of results
- Better detection performance
- A more realistic IDS formulation

# Project structure 
the dataset is divided into two files in the NSL-KDD Dataset(filtered, not original version) folder:
- KDDTrain_filtered.csv
- KDDTest_filtered.csv

For notebooks, there are four code files :
- ids1.ipynb for the multi-class Decision Tree model
- LR_ids2.ipynb for the multiclass Logistic Regression model
- binary_ids1.ipynb for the binary Decision Tree model
- binary_LR_ids.ipynb for the binary Logistic Regression model

# Methodology
Data Preprocessing
- Separation of features and labels
- Standardization of numerical features
- One-Hot Encoding of categorical features

Problem Formulations
- Multi-class classification (original labels)
- Binary classification (normal vs attack)

Models Implemented
- Decision Tree Classifier adn 
- Logistic Regression

Evaluation Metrics used in are : 
- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

# Results Summary

Multi-class classification shows limited performance due to class imbalance.

Binary classification significantly improves IDS effectiveness.

Logistic Regression in binary mode provides a better balance between attack detection and false alarms.

Binary IDS formulation offers clear and more actionable security insights.

# Visualization
Confusion matrix visualizations were generated for both binary classification models. These visual results highlight the trade-off between false positives and false negatives, which is a critical consideration in IDS design.

# Requirements : 
Ensures that Python 3.8 or high is installed.
All required Python dependencies for this project are listed in the requirements.txt file included in this repository. To set up the project environment, install the required dependencies using the command : 
- pip install -r requirements.txt

This ensures that all libraries and versions used during development and experimentation are correctly installed.
