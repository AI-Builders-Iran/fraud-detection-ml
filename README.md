<div align="center">

# 💳 Fraud Detection using Machine Learning

### Intelligent Credit Card Fraud Detection System

Detect fraudulent financial transactions using Machine Learning with an interactive web interface and REST API.

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?logo=plotly&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?logo=python&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?logo=python&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-005CED?logo=onnx&logoColor=white)
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
- [📈 Evaluation Metrics](#-evaluation-metrics)
- [🚀 Installation](#-installation)
- [▶ Running the API](#-running-the-api)
- [🌐 Frontend](#-frontend)
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
- Interactive Web Interface
- Real-time prediction

---


# ✨ Features

✅ Binary Fraud Classification

✅ Data Cleaning & Preprocessing

✅ Feature Scaling

✅ Handling Imbalanced Dataset

✅ Multiple Machine Learning Models

✅ Model Comparison

✅ Performance Evaluation

✅ using FastAPI

✅ Interactive HTML Frontend

✅ Real-time Fraud Prediction

---

# 🏗 Project Structure

```text
fraud-detection-ml/

│
├── reports/
│   ├── figures/
│
├── notebooks/
|   ├── Main.ipynb
│
├── models/
├── API/
|   ├── app.py
|
├──DockerFile
|
├── requirements.txt
│
└── README.md
```

---

# 📊 Dataset

This project uses the **Credit Card Fraud Detection Dataset**, a widely used benchmark for fraud detection research and machine learning.

> **Source:** Credit Card Fraud Detection Dataset (Kaggle)

📂 **View Dataset:**  
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

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

- Python
- Scikit-Learn
- Pandas
- NumPy
- FastAPI
- HTML/CSS/JavaScript
- ONNX
- Docker
- Git & GitHub

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
     │
     ▼
Frontend
```

---

# 🤖 Models

The project supports comparing multiple models.

- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost
- LightGBM
- CatBoost
- Neural Network (MLP)

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
uvicorn api.main:app --reload
```

Open

```
http://127.0.0.1:8000/docs
```

---

# 🌐 Frontend

Launch

```
frontend/index.html
```

or serve using any static web server.

The interface allows users to

- Enter transaction information
- Predict fraud probability
- View prediction result
- Display model confidence

---

# 📊 Example Prediction

| Amount | Time | Prediction |
|---------|------|------------|
| 200.5 | 53452 | Legitimate |
| 1540.8 | 78312 | Fraud |

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