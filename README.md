<div align="center">

# 💳 Fraud Detection using Machine Learning

### Intelligent Credit Card Fraud Detection System

Detect fraudulent financial transactions using Machine Learning with an interactive web interface and REST API.

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas)
![License](https://img.shields.io/badge/License-MIT-green)

</div>

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
|
│
├── models/
│
|
├── requirements.txt
│
└── README.md
```

---

# 📊 Dataset

This project uses the famous **Credit Card Fraud Detection Dataset**.

Dataset characteristics:

| Property | Value |
|-----------|--------|
| Transactions | 284,807 |
| Fraud Cases | 492 |
| Classes | Binary |
| Features | 30 |

Because fraud samples are extremely rare, the dataset is highly imbalanced, making it a realistic fraud detection problem.

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

Developed by

**AI Builders Iran**

We build open-source Machine Learning and AI projects to learn, collaborate, and grow together.

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