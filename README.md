# Network Intrusion Detection System Using Machine Learning

ML-based NIDS evaluated on NSL-KDD and UNSW-NB15 benchmarks. Compares 6 classifiers with ROS balancing and RFE feature selection.

## Datasets
Download separately and update paths in notebooks before running.
- **NSL-KDD** — `KDDTrain+.txt`, `KDDTest+.txt`
- **UNSW-NB15** — `UNSW_NB15_training-set.csv`, `UNSW_NB15_testing-set.csv`

## Pipeline
1. Data Loading + Attack Label Mapping
2. EDA — class distribution, redundant column removal
3. Feature Scaling — StandardScaler
4. Categorical Encoding — Label Encoding
5. Class Balancing — Random Oversampling (ROS)
6. Feature Selection — Random Forest importance + RFE (top 10 features)
7. Model Training — SVM, KNN, Naive Bayes, Decision Tree, Random Forest, Logistic Regression
8. Evaluation — 10-fold cross-validation, accuracy, confusion matrix

## Results

| Algorithm | NSL-KDD (CV) | UNSW-NB15 (CV) |
|---|---|---|
| Random Forest | **99.99%** | **99.78%** |
| Decision Tree | 99.98% | 99.76% |
| KNN | 99.92% | 99.33% |
| SVM | 99.74% | 98.36% |
| Logistic Regression | 99.50% | 94.44% |
| Naive Bayes | 95.58% | 77.52% |


## Demo
[Watch demo](https://drive.google.com/file/d/19OCAXg1bP6k_9TwcgD68Hi_5THzoXNxz/view?usp=sharing)

## Requirements
```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn
```
