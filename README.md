<div align="center">

# 💳 Fraud Detection using Machine Learning

### Intelligent Credit Card Fraud Detection System

Detect fraudulent financial transactions using Machine Learning with  REST API.

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?logo=plotly&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?logo=python&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?logo=python&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?logo=github&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

</div>

---

# 📑 Table of Contents

- [📖 Overview](#-overview)
- [✨ Features](#-features)
- [🏗 Project Structure](#-project-structure)
- [📊 Dataset](#-dataset)
- [🛠 Tech Stack](#-tech-stack)
- [⚙ Machine Learning Pipeline](#-machine-learning-pipeline)
- [🤖 Models](#-models)
- [📈 Model Performance](#-model-performance)
- [📈 Evaluation Metrics](#-evaluation-metrics)
- [🚀 Installation](#-installation)
- [▶ Running the API](#-running-the-api)
- [📊 Example Prediction](#-example-prediction)
- [👥 Team](#-team)
- [🤝 Contributing](#-contributing)
- [⭐ Support](#-support)
- [📄 License](#-license)

---

# 📖 Overview

Fraudulent financial transactions cause billions of dollars in losses every year.
This project builds an end-to-end Machine Learning pipeline capable of detecting fraudulent credit card transactions using historical transaction data.

The project is designed as a complete ML application including:

- Data preprocessing
- Feature engineering
- Model training
- Model evaluation
- Fast API
- Real-time prediction

---


# ✨ Features

- Binary fraud classification
- Data cleaning and preprocessing
- Feature scaling
- Handling imbalanced datasets
- Multiple machine learning models
- Model comparison
- Performance evaluation
- REST API using FastAPI
- Real-time fraud prediction

---

# 🏗 Project Structure

```text
fraud-detection-ml/

│
├── API/
|   ├── app.py
|
├── data/
|   ├── creditcard_raw_backup.csv.gz
|
├── model/
|   ├── fraud_model_final.joblib
|
├── notebooks/
|   ├── Main.ipynb
|
├── reports/
│   ├── figures/
│
├── Team_Report/
|   ├──
|
├── .dockerignore
|
├── .gitignore
|
├──Dockerfile
|
├── README.md
│
└── requirements.txt
```

---

# 📊 Dataset

This project uses the **Credit Card Fraud Detection Dataset**, a widely used benchmark for fraud detection research and machine learning.

> **Source:** Credit Card Fraud Detection Dataset (Kaggle)

📂 **View Dataset:**  
[Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

### Dataset Statistics

| Property | Value |
|-----------|--------|
| Transactions | 284,807 |
| Fraud Cases | 492 |
| Legitimate Cases | 284,315 |
| Features | 30 |
| Target | Binary Classification |

The dataset is highly imbalanced, with fraudulent transactions representing only **0.172%** of all transactions, making it a realistic and challenging classification problem.

---

# 🛠 Tech Stack

## Machine Learning

- Scikit-Learn
- XGBoost
- LightGBM
- Optuna

## Backend

- FastAPI

## Data Processing

- Pandas
- NumPy

## Visualization

- Matplotlib
- Seaborn
- Plotly

## Deployment

- Docker

## Version Control

- Git
- GitHub

---

# ⚙ Machine Learning Pipeline

```
Raw Data
     │
     ▼
Cleaning
     │
     ▼
EDA
     │
     ▼
Preprocessing
     │
     ▼
Train/Test Split
     │
     ▼
Model Training
     │
     ▼
Evaluation
     │
     ▼
Save Model
     │
     ▼
FastAPI
```

---

# 🤖 Models

The project supports comparing multiple models.

- Logistic Regression
- XGBoost
- LightGBM

---

# 📈 Model Performance

The final production model is **LightGBM (LGBMClassifier)** with a **classification threshold of 0.10**, selected to improve fraud detection recall while maintaining high precision on the highly imbalanced dataset.

| Metric | Score |
|:--------|------:|
| Model | LightGBM |
| Classification Threshold | **0.10** |
| Accuracy | **99.95%** |
| Precision | **89.29%** |
| Recall | **78.95%** |
| F1-Score | **83.80%** |
| PR-AUC (Test Set) | **0.8201** |
| PR-AUC (Cross Validation) | **0.8435** |

> **Note:** Because the dataset is highly imbalanced, model selection was primarily based on **Precision, Recall, F1-Score, and PR-AUC**, rather than Accuracy alone.

---

# 📈 Evaluation Metrics

Since fraud detection is an imbalanced classification problem, multiple metrics are used.

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- PR-AUC
- Confusion Matrix

---

# 🚀 Installation

Clone repository

```bash
git clone https://github.com/AI-Builders-Iran/fraud-detection-ml.git
```

Enter project

```bash
cd fraud-detection-ml
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# ▶ Running the API

```bash
uvicorn API.app:app --reload
```

Once the server is running, open:

### Swagger UI

```
http://127.0.0.1:8000/docs
```

### ReDoc

```
http://127.0.0.1:8000/redoc
```

---

### Example Request

```http
POST /predict
Content-Type: application/json
```

```json
{
  "Time": 406.0,
  "V1": -1.359807,
  "V2": -0.072781,
  "V3": 2.536347,
  "V4": 1.378155,
  "V5": -0.338321,
  "V6": 0.462388,
  "V7": 0.239599,
  "V8": 0.098698,
  "V9": 0.363787,
  "V10": 0.090794,
  "V11": -0.551600,
  "V12": -0.617801,
  "V13": -0.991390,
  "V14": -0.311169,
  "V15": 1.468177,
  "V16": -0.470401,
  "V17": 0.207971,
  "V18": 0.025791,
  "V19": 0.403993,
  "V20": 0.251412,
  "V21": -0.018307,
  "V22": 0.277838,
  "V23": -0.110474,
  "V24": 0.066928,
  "V25": 0.128539,
  "V26": -0.189115,
  "V27": 0.133558,
  "V28": -0.021053,
  "Amount": 149.62
}
```

### Example Response

```json
{
  "prediction": 0.0,
}
```

---

# 👥 Team

This project is developed by the **AI Builders Iran** team.

| Member | GitHub | Role |
|--------|--------|------|
| Amir Mohammad Hatamzadeh | [@hatamzadeh86](https://github.com/hatamzadeh86) | Organization Owner / Project Lead |
| Hossein Heydari | [@HosseinHeydari2004](https://github.com/HosseinHeydari2004) | Technical Operations Coordinator |
| Eyna Shabani | [@Eyna-A](https://github.com/Eyna-A) | Maintainer |
| Fatemeh Amlahi | [@FatemeAmlahi](https://github.com/FatemeAmlahi) | Contributor |
| Farshad Zargari | [@farshadz1997](https://github.com/farshadz1997) | Contributor |
| Maral Farahmandfar | [@MaralFarahmandfar](https://github.com/MaralFarahmandfar) | Contributor |
| Mohaddeseh Mohamadiha | [@Mohii722](https://github.com/Mohii722) | Contributor |
| Mohammad Zarei | [@mohammdz1997](https://github.com/mohammdz1997) | Contributor |
| Seyede Reyhane Khorashadizade | [@Seyede-Reyhane-Khorashadizade](https://github.com/Seyede-Reyhane-Khorashadizade) | Contributor |
Erfan Jenab | [@Erfanjenab](https://github.com/Erfanjenab) | Contributor
Nelisa Zarenejad | [@Nellshere](https://github.com/Nellshere) | Contributor

We collaborate to build open-source Machine Learning and AI projects while learning and growing together.

---

# 🤝 Contributing

Contributions are always welcome.

1. Fork repository

2. Create new branch

```bash
git checkout -b feature/new-feature
```

3. Commit

```bash
git commit -m "Add new feature"
```

4. Push

```bash
git push origin feature/new-feature
```

5. Open Pull Request

---

# ⭐ Support

If you found this project useful,

please consider giving it a ⭐ on GitHub.

It helps the project grow.

---

# 📄 License

This project is licensed under the MIT License.