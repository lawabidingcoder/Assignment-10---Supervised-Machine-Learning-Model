# Assignment-10---Supervised-Machine-Learning-Model

# Mini Project: Supervised Machine Learning – Fraud Detection

## Project Overview
This project applies supervised machine learning techniques to detect fraudulent financial transactions using the `fraud.csv` dataset. It involves exploring, pre-processing, modelling, and evaluating the dataset to build a system capable of identifying fraudulent behaviour with high accuracy and reliability.

---

## 🧾 Project Requirements & Description

This project follows the key requirements of the assignment brief:

1. **Data Exploration**  
   - Analysed structure and distribution of fields in `fraud.csv`
   - Identified zero and missing values
   - Detected the need for scaling and encoding due to imbalance and categorical data

2. **Data Preparation**
   - Filled zero values with medians where appropriate
   - Scaled data using `RobustScaler` to manage outliers
   - Encoded categorical features using `LabelEncoder`
   - Sampled data to address class imbalance for model fairness

3. **Model Development**
   - Trained multiple supervised ML models:
     - Logistic Regression (regular)
     - Support Vector Machines (Linear, RBF, Sigmoid)(undersampled)
     - Random Forest (regular and undersampled)
     - Neural Network (undersampled)

4. **Model Evaluation**
   - Used accuracy, precision, recall, and F1-score
   - Plotted ROC curves for all models
   - Analysed trade-offs between false positives and false negatives

---

##  Dataset Used

- **Name:** `fraud.csv`  
- **Description:** A simulation of mobile money transactions labelled as fraud or non-fraud.  
- **Source:** [Kaggle – PaySim Fraud Detection Dataset](https://www.kaggle.com/ntnu-testimon/paysim)

---

## Models & Results Summary

| Model              | Precision | Recall | F1-Score | Accuracy |
|--------------------|-----------|--------|----------|----------|
| Logistic Regression | Low       | High   | Low      | 97%      |
| SVM (Linear/RBF)    | ~72%      | ~90%   | Strong   | 98%      |
| Random Forest       | 13%       | 98%    | Moderate | 99%      |
| **RF (Undersampled)** | **99%**   | **97%** | **Best**  | **100%** |
| Neural Network      | 94%       | 88%    | High     | 98%      |

- ✅ **Best Model:** Random Forest (Undersampled)
- 🚫 **Worst Kernel:** SVM Sigmoid — struggled with precision and overall accuracy
- 📉 **Accuracy alone was misleading** due to class imbalance; precision/recall were prioritized

---

## Next Steps
- Fine-tune top models using GridSearchCV
- Add ‘is_off_hours’ feature (e.g., 0–6 AM) to allow model to flag time-based risk
- Deploy fraud detection system as an API
- Monitor performance on live or real-world data

---

## How to Run
1. Clone this repository
2. Install required packages:
   ```bash
   pip install -r requirements.txt
