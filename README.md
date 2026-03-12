# Comparative Analysis of Anomaly Detection in High-Imbalance Financial Data

## 📌 Project Overview
This research project focuses on the detection of fraudulent financial activity within a synthetic dataset of over 6.3 million transactions (PaySim). The primary objective was to evaluate the trade-offs between **unsupervised anomaly detection** and **supervised machine learning** in a highly imbalanced environment where fraud represents only 0.12% of the total volume.

## 🛠️ Technical Stack
* **Language:** Python 3.x
* **Libraries:** Pandas, NumPy, Scikit-Learn, XGBoost
* **Visualization:** Seaborn, Matplotlib
* **Version Control:** Git / GitHub

## 🔬 Methodology

### 1. Data Acquisition & Preprocessing
* **Source:** PaySim (Synthetic Financial Datasets for Fraud Detection).
* **Feature Engineering:** Developed "Balance Error" metrics to capture discrepancies between transaction amounts and account balances, a key indicator of fraudulent transfers.
* **Encoding:** Implemented One-Hot Encoding for categorical transaction types and Standard Scaling for numeric features to ensure algorithmic convergence.

### 2. Exploratory Data Analysis (EDA)
* Analyzed class distribution using logarithmic scaling to visualize the extreme rarity of fraudulent events.
* Conducted correlation analysis to identify multi-collinearity between transaction amounts and balance updates.

### 3. Model Implementation
I implemented a **Challenger-Baseline** framework:
* **Baseline (Unsupervised):** **Isolation Forest** was used to detect anomalies without labeled data, simulating a "cold-start" scenario in banking.
* **Challenger (Supervised):** **XGBoost (Extreme Gradient Boosting)** was implemented with `scale_pos_weight` adjustments to handle heavy class imbalance.

## 📊 Evaluation Metrics
In financial crime detection, **Accuracy is a misleading metric**. This project prioritizes:
* **AUPRC (Area Under Precision-Recall Curve):** To measure the trade-off between capturing all fraud (Recall) and minimizing false alarms (Precision).
* **F1-Score:** To find the optimal balance for operational efficiency.

## 📈 Key Findings
* The Supervised XGBoost model significantly outperformed the unsupervised baseline, proving that historical fraud labels drastically improve detection precision.
* Engineering the `errorBalance` features was the most significant factor in reducing False Positives.

---
*This project was completed as part of a Master's level study into Financial Decision Science and Algorithmic Fraud Detection.*
