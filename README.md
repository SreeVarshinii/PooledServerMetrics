# 🔍 Anomaly Detection in Data Center Server Metrics (PSM Dataset)

This project focuses on detecting anomalies in multivariate time-series data collected from real-world server environments using the **Pooled Server Metrics (PSM)** dataset. The aim is to compare multiple unsupervised learning algorithms and evaluate their performance in identifying operational anomalies across 25 server features.

---

## 📁 Dataset

**Source**: [Pooled Server Metrics (PSM) Dataset on Kaggle](https://www.kaggle.com/datasets/ljolm08/pooled-server-metrics-psm)

- `psm_train.csv` — training set (normal data)
- `psm_test.csv` — test set
- `psm_test_label.csv` — binary labels for test set (1 = anomaly, 0 = normal)
- Each sample has 25 numerical features and a timestamp in minutes

---

## 🚀 Objective

- Perform **exploratory data analysis (EDA)** to understand the data
- Implement and compare **three anomaly detection models**:
  - Isolation Forest
  - One-Class SVM
  - Autoencoder (neural network)
- Evaluate models using:
  - Precision, Recall, F1-Score
  - ROC AUC
  - Visualization (ROC curves and anomaly overlays)

---

## 🧰 Technologies Used

- Python (NumPy, pandas, matplotlib, seaborn)
- Scikit-learn
- TensorFlow / Keras (for Autoencoder)
- Jupyter Notebook

---

## 📊 Workflow

### 1. Data Preprocessing
- Convert timestamp and ensure feature columns are float
- Remove duplicates and check for missing values
- Standardize feature values using `StandardScaler`

### 2. Exploratory Data Analysis (EDA)
- Summary statistics (mean, std, median)
- Correlation matrix
- Boxplots and time-series plots
- PCA for visualization

### 3. Modeling
- **Isolation Forest**: Tree-based anomaly score
- **One-Class SVM**: Distance-based anomaly boundary
- **Autoencoder**: Reconstruction error as anomaly score

### 4. Evaluation
- Confusion matrix and classification report
- ROC curve and AUC comparison
- Overlay of true vs. predicted anomalies over time

---

## 📈 Results (Example)

| Model             | AUC Score | F1 (Anomalies) | Precision (Anomalies) | Recall (Anomalies) |
|------------------|-----------|----------------|------------------------|---------------------|
| Isolation Forest | 0.2892    | 0.34           | 0.58                   | 0.24                |
| One-Class SVM    | 0.3843    | **0.41**       | 0.39                   | **0.43**            |
| Autoencoder      | **0.6471**| 0.21           | **0.70**               | 0.13                |

---

