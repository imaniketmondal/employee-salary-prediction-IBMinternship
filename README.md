# 🧠 Employee Salary Prediction using Machine Learning

This project predicts whether an individual's annual salary exceeds **$50K** based on demographic and employment-related features using the **UCI Adult Dataset**. It includes a comparison of multiple machine learning models, data preprocessing, outlier handling, and deployment via **Streamlit** and **ngrok**.

---

## 📂 Table of Contents

- [Overview](#-overview)
- [Tech Stack](#-tech-stack)
- [Dataset](#-dataset)
- [System Workflow](#-system-workflow)
- [Deployment](#-deployment)

---

## 📌 Overview

The goal of this project is to build a machine learning model that can predict whether a person earns **>50K** or **<=50K** annually based on features like age, education, occupation, gender, workclass, and more.  
This is a classic binary classification problem.

---

## 🛠️ Tech Stack

- **Language:** Python
- **ML Models:** Logistic Regression, K-Nearest Neighbors (KNN), Decision Tree
- **Libraries:** `pandas`, `matplotlib`, `scikit-learn`, `streamlit`
- **Deployment:** Streamlit + ngrok (for public access)
- **IDE:** Jupyter Notebook

---

## 📊 Dataset

- **Name:** Adult Income Dataset (`adult.csv`)
- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/adult)
- **Features:**  
  `age`, `workclass`, `education`, `marital-status`, `occupation`,  
  `relationship`, `race`, `gender`, `hours-per-week`, `capital-gain`, `capital-loss`, etc.
- **Target Variable:** `Salary` (`>50K` or `<=50K`)

---

## 🔄 System Workflow

1. **Data Collection:** Loaded UCI Adult dataset.
2. **Data Cleaning:**
   - Replaced missing values (`?`) with `'Others'`.
   - Dropped rows with `workclass` as `'Without-pay'` or `'Never-worked'`.
3. **Outlier Detection:**  
   - Removed outliers in `age`, `capital-gain`, etc. using boxplots.
4. **Feature Encoding:**  
   - Applied Label Encoding and OneHotEncoding to convert categorical variables.
5. **Model Training & Evaluation:**
   - Trained Logistic Regression, KNN, and Decision Tree classifiers.
   - Evaluated using accuracy and confusion matrix.
6. **Deployment:**
   - Created a Streamlit web app.
   - Exposed locally using ngrok for public access.

---

## 🚀 Deployment

### 🌐 Streamlit + ngrok Setup:

Before using ngrok for the first time, you'll need to log in and set up your **auth token**:

1. **Login or sign up** at [https://ngrok.com](https://ngrok.com)
2. **Copy your auth token** from your [ngrok dashboard](https://dashboard.ngrok.com/get-started/setup)
3. **Authenticate ngrok** in your terminal:

```bash
ngrok config add-authtoken <your-auth-token>
```bash
# Run Streamlit app
streamlit run app.py

# In a new terminal, expose via ngrok
ngrok http 8501
