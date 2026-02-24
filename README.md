# 🏥 End-to-End Medical Triage Assistant (with Explainability)

## 📌 Project Overview
This project implements an end-to-end medical risk triage assistant that predicts **stroke risk** using structured **Electronic Medical Record (EMR)** data.  
The system classifies patients into **Low, Medium, and High risk** categories and provides **explainable predictions** to support transparent clinical decision-making.

The project demonstrates a complete **applied machine learning pipeline**, including preprocessing, class imbalance handling, model comparison, probability calibration, and explainable AI (XAI).

> ⚠️ **Disclaimer:**  
> This system is intended as a **clinical decision-support tool**, not a diagnostic replacement for healthcare professionals.

---

## 🎯 Objectives
- Predict patient stroke risk using tabular EMR data  
- Handle severe class imbalance in medical datasets  
- Compare multiple machine learning models  
- Calibrate predicted probabilities for reliable risk estimation  
- Provide explainable predictions using SHAP  
- Build a practical risk-based triage system  

---

## 🧠 Models Used
The following machine learning models were implemented and evaluated:

- Logistic Regression  
- Support Vector Machine (RBF Kernel)  
- Random Forest (**selected as best model**)  
- Gaussian Naive Bayes  

Model selection was based on **ROC-AUC** and **Precision-Recall** performance, which are more suitable for **imbalanced medical data**.

---

## 🧹 Data Preprocessing
- Removed non-informative ID column  
- Handled missing values (BMI median imputation)  
- One-Hot Encoding for categorical features  
- StandardScaler for numerical features  
- Stratified train-test split  
- SMOTE applied **only on training data**

---

## ⚖️ Class Imbalance Handling
The dataset exhibits severe class imbalance. To address this:

- **SMOTE (Synthetic Minority Oversampling Technique)** was applied to the training set only  
- Evaluation metrics beyond accuracy were emphasized  

---

## 📊 Evaluation Metrics
The following metrics were used:

- Accuracy  
- ROC-AUC Curve  
- Precision-Recall Curve  
- Confusion Matrix  

These metrics help assess model performance under **imbalanced conditions**.

---

## 🔧 Probability Calibration
- **Isotonic Regression** was applied to calibrate predicted probabilities  
- Calibration ensures predicted risk percentages better reflect real-world risk  
- Calibrated probabilities are used for final triage decisions  

---

## 🚦 Risk Triage System
Based on calibrated probabilities, patients are categorized as:

| Risk Level | Probability Range | Recommended Action |
|-----------|------------------|--------------------|
| Low | < 20% | Routine monitoring |
| Medium | 20% – 60% | Scheduled follow-up |
| High | > 60% | Immediate clinical attention |

---

## 🔍 Explainability & Interpretability (SHAP)
To ensure transparency and trust:

- **Global Explainability:** SHAP summary plots identify overall risk-driving features  
- **Local Explainability:** SHAP waterfall and force plots explain individual predictions  
- SHAP explanations are generated from the **Random Forest model**, while calibrated probabilities are used for risk communication  

---

## ⚠️ Ethical Considerations
- Patient data is assumed to be anonymized and used strictly for academic purposes  
- The model may inherit bias from the dataset and requires continuous monitoring  
- Human oversight is mandatory; clinicians make final decisions  
- Explainability supports ethical requirements such as transparency and accountability  

---

## 🗂 Project Structure
├── CCA_.ipynb # Main Jupyter notebook
├── CCA_report.docx # Project report
├── README.md # Project documentation

---

## 🛠 Setup & Installation Requirements
**Python Version:**  
- Python 3.8+

**Libraries Required:**  
- pandas  
- numpy  
- matplotlib  
- seaborn  
- scikit-learn  
- imbalanced-learn  
- shap  

### Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn shap

# ▶️ How to Run

Open the Jupyter Notebook:

jupyter notebook

# 🎓 Academic Context

Course: Machine Learning

Program: BS Artificial Intelligence

Institution: Dawood University of Engineering & Technology, Karachi

# 👩‍💻 Authors

Mehak Faheem

Arekah Taj

Javeria Iqbal

Hiba Iqbal
