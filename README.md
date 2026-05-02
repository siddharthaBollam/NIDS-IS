# Network Intrusion Detection System Using Machine Learning Algorithms
## Overview

This project implements a machine learning-based Network Intrusion Detection System (NIDS) evaluated on two benchmark datasets — NSL-KDD and UNSW-NB15. It extends the base paper by introducing a structured preprocessing pipeline and expanding the classifier comparison from three algorithms to six.

---

## Files

| File | Description |
|------|-------------|
| `NIDS_NSL-KDD` | Full pipeline implementation on the NSL-KDD dataset |
| `NIDS_UNSW-NB15` | Full pipeline implementation on the UNSW-NB15 dataset |
| `Intrusion_Detection_System_Using_machine_learning_.pdf` | Base paper |
| `Presentation` | Project presentation slides |

---

## Datasets

The notebooks require the following dataset files, which are not included in this repository and must be downloaded separately.

- **NSL-KDD** — `KDDTrain+.txt` and `KDDTest+.txt`
- 
- **UNSW-NB15** — `UNSW_NB15_training-set.csv` and `UNSW_NB15_testing-set.csv`
- 
Update the file paths in the data loading cells of each notebook to point to your local copies before running.

---

## Pipeline

Both notebooks follow the same end-to-end pipeline:

1. **Data Loading** — Load training and test splits
2. **Attack Label Mapping** — Map granular attack types to broad categories
3. **Exploratory Data Analysis** — Class distribution, descriptive statistics, redundant column removal
4. **Feature Scaling** — StandardScaler normalization on numerical attributes
5. **Categorical Encoding** — Label Encoding of categorical features
6. **Class Balancing** — Random Oversampling to address class imbalance
7. **Feature Selection** — Random Forest importance scores and RFE to select top 10 features
8. **Model Training** — Six classifiers: SVM, KNN, Naive Bayes, Decision Tree, Random Forest, Logistic Regression
9. **Evaluation** — 10-fold cross-validation, accuracy, confusion matrix, classification report

---

## Results

| Algorithm | NSL-KDD (CV Score) | UNSW-NB15 (CV Score) |
|---|---|---|
| Random Forest | **99.99%** | **99.78%** |
| Decision Tree | 99.98% | 99.76% |
| K-Nearest Neighbor | 99.92% | 99.33% |
| SVM | 99.74% | 98.36% |
| Logistic Regression | 99.50% | 94.44% |
| Naive Bayes | 95.58% | 77.52% |

Random Forest achieved the highest cross-validation score on both datasets, outperforming the base paper's best result (SVM at 97.77% on UNSW-NB15 and 97.29% on NSL-KDD).

---

## Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn
imbalanced-learn
```

Install all dependencies with:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn
```

---
