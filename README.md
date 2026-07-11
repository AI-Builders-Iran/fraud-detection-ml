<p align="center">
  <img src="https://img.shields.io/badge/Domain-Financial%20Risk%20ML-1f6feb?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Framework-FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" />
  <img src="https://img.shields.io/badge/Deployment-Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" />
</p>

<h1 align="center">🛡️ fraud-detection-ml</h1>

<p align="center">
  <b>An end-to-end Machine Learning project for credit card fraud detection, covering data analysis, preprocessing, model training, evaluation, and deployment.</b><br/>
  Built collaboratively by <a href="#-team--contributors"><b>AI Builders Iran</b></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-active--development-brightgreen?style=flat-square" />
  <img src="https://img.shields.io/badge/dataset-Zenodo-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/best%20model-XGBoost-orange?style=flat-square" />
</p>

---

## 📖 Table of Contents

- [Project Overview](#-project-overview)
- [Workflow Lifecycle](#-workflow-lifecycle)
- [Dataset](#-dataset)
- [Exploratory Data Analysis](#-exploratory-data-analysis-eda)
- [Preprocessing & Feature Engineering](#-preprocessing--feature-engineering)
- [Modeling](#-modeling)
- [Evaluation — Why Accuracy is a Trap](#-evaluation--why-accuracy-is-a-trap)
- [Results Comparison](#-results-comparison)
- [Deployment (FastAPI + Docker)](#-deployment-fastapi--docker)
- [Project Structure](#-project-structure)
- [Installation & Quick Start](#-installation--quick-start)
- [Team & Contributors](#-team--contributors)
- [Roadmap](#-roadmap)
- [License](#-license)

---

## 🎯 Project Overview

Financial fraud costs institutions billions of dollars annually, and the transactions that matter most are the rarest ones in the dataset. This project delivers a **complete, production-oriented machine learning system** that identifies fraudulent credit card transactions from anonymized transactional data — covering the entire lifecycle from raw data to a deployable API.

This isn't just a notebook exercise. The goal of **AI Builders Iran** was to simulate a real-world ML product cycle: research, experimentation, rigorous evaluation, and deployment — fully documented and reproducible on GitHub.

---

## 🔄 Workflow Lifecycle

```
Dataset → EDA → Data Cleaning → Feature Engineering → Model Training → Evaluation → Deployment
```

Each stage was owned by a dedicated sub-team, with hand-off checkpoints to ensure data integrity and reproducibility across the pipeline.

---

## 📊 Dataset

| | |
|---|---|
| **Source** | [Credit Card Fraud Detection Dataset — Zenodo](https://zenodo.org/records/7395559) |
| **Records** | Real-world anonymized card transactions |
| **Features** | `Time`, `Amount`, `V1`–`V28` (PCA-transformed), `Class` (target) |
| **Target** | `Class` → `0` = Legitimate, `1` = Fraudulent |

> **Note on features:** `V1`–`V28` are the result of a PCA transformation applied by the original data provider to protect sensitive cardholder information. Their real-world meaning is intentionally undisclosed — only `Time` and `Amount` remain in their raw form.

---

## 🔍 Exploratory Data Analysis (EDA)

Key insight from the analysis phase: **this dataset is extremely imbalanced.** Fraudulent transactions make up less than **0.2%** of all records — a critical factor that shaped every downstream decision, from preprocessing strategy to model evaluation metrics.

### Class Distribution

<p align="center"><img src="assets/images/class_distribution.png" alt="Class Distribution" width="600"/></p>

### Feature Correlation Matrix

<p align="center"><img src="assets/images/correlation_matrix.png" alt="Correlation Matrix" width="700"/></p>

Since `V1`–`V28` are orthogonal PCA components, inter-feature correlation is minimal by design — the analysis instead focused on each feature's individual correlation with the `Class` target to identify the strongest fraud indicators.

---

## 🧹 Preprocessing & Feature Engineering

- **Missing value & duplicate audit** across all columns
- **Scaling** applied to `Time` and `Amount` (V1–V28 are already normalized via PCA)
- **Class imbalance handling** via a combination of:
  - **SMOTE** (Synthetic Minority Over-sampling Technique)
  - **Under-sampling** of the majority class
  - `scale_pos_weight` / `class_weight='balanced'` for tree-based and boosting models
- **Stratified train/test split** to preserve the original class ratio in both sets

---

## 🤖 Modeling

Four algorithms were trained and benchmarked, spanning linear, ensemble, and gradient-boosting approaches:

| Category | Algorithm | Role |
|---|---|---|
| Linear (Baseline) | **Logistic Regression** | Fast, interpretable reference point |
| Ensemble (Bagging) | **Random Forest** | Robust to noise, handles non-linearity |
| Gradient Boosting | **XGBoost** | High-performance boosting with regularization |
| Gradient Boosting | **LightGBM** | Fast, leaf-wise boosting for large datasets |

All models were validated using **Stratified K-Fold Cross-Validation** to ensure consistent class representation across folds.

---

## ⚖️ Evaluation — Why "Accuracy is a Trap"

In a dataset where **99.8% of transactions are legitimate**, a naive model that predicts *"not fraud"* every single time would achieve **>99% accuracy** — while catching **zero fraud cases**. In financial fraud detection, that's not a good model; it's a broken one.

For this reason, the team deliberately optimized for:

- 🎯 **Recall** — the ability to catch as many actual fraud cases as possible (minimizing missed fraud)
- ⚡ **F1-Score** — the balance between Recall and Precision, avoiding excessive false alarms
- 📈 **ROC-AUC / PR-AUC** — better indicators of model discrimination power on imbalanced data than raw accuracy

Accuracy is reported for completeness, but it was **never** the metric used to select the final model.

### Confusion Matrix (Best Model)

<p align="center"><img src="assets/images/confusion_matrix.png" alt="Confusion Matrix" width="500"/></p>

### ROC-AUC Curve Comparison

<p align="center"><img src="assets/images/roc_auc_curve.png" alt="ROC-AUC Curve" width="600"/></p>

---

## 📈 Results Comparison

> ⚠️ Replace placeholder values (`XX.X%`) with your team's final measured results before publishing.

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|:---:|:---:|:---:|:---:|:---:|
| Logistic Regression (Baseline) | XX.X% | XX.X% | XX.X% | XX.X% | XX.X% |
| Random Forest | XX.X% | XX.X% | XX.X% | XX.X% | XX.X% |
| **XGBoost** 🏆 | **XX.X%** | **XX.X%** | **85.0%** | **82.0%** | **XX.X%** |
| LightGBM | XX.X% | XX.X% | XX.X% | XX.X% | XX.X% |

### 🏆 Best Performing Model: **XGBoost**

XGBoost was selected as the production model based on its superior **Recall** and **F1-Score**, striking the strongest balance between catching fraudulent transactions and minimizing false positives — the metric priority that matters most in a real financial risk system.

---

## 🚀 Deployment (FastAPI + Docker)

The final model is served through a lightweight **FastAPI** backend, containerized with **Docker** for consistent, portable deployment.

Unlike a simple binary classifier, the API returns **both**:

1. The **predicted class** (`0` = Legitimate, `1` = Fraud)
2. A **dynamic Fraud Probability Score** (`predict_proba`) — enabling downstream systems to apply custom risk thresholds instead of relying on a fixed cutoff

### Example Request

```bash
curl -X POST "http://localhost:8000/predict" \
  -H "Content-Type: application/json" \
  -d '{
        "Time": 406,
        "V1": -2.3122,
        "V2": 1.9519,
        "...": "...",
        "V28": 0.0134,
        "Amount": 149.62
      }'
```

### Example Response

```json
{
  "prediction": 1,
  "prediction_label": "Fraud",
  "fraud_probability": 0.9421
}
```

### Run with Docker

```bash
docker build -t fraud-detection-api .
docker run -p 8000:8000 fraud-detection-api
```

---

## 📁 Project Structure

```
fraud-detection-system/
├── assets/
│   └── images/                # EDA & evaluation visuals
├── data/
│   ├── raw/                   # Original dataset
│   └── processed/             # Cleaned & feature-engineered data
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_preprocessing.ipynb
│   └── 03_modeling.ipynb
├── src/
│   ├── preprocessing/
│   ├── models/
│   └── evaluation/
├── api/
│   ├── main.py                 # FastAPI application
│   └── model/                  # Serialized model artifact
├── Dockerfile
├── requirements.txt
└── README.md
```

---

## ⚙️ Installation & Quick Start

```bash
# Clone the repository
git clone https://github.com/AI-Builders-Iran/fraud-detection-system.git
cd fraud-detection-system

# Create a virtual environment
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the API locally
uvicorn api.main:app --reload
```

The API will be available at `http://localhost:8000/docs` (interactive Swagger UI).

---

## 👥 Team & Contributors

| Team | Responsibility | Members |
|---|---|---|
| 📥 **Data Collection & Analysis** | Dataset sourcing, EDA, feature relationship analysis | [@nelisazarenejad](https://github.com/nelisazarenejad), [@mohammadz1997](https://github.com/mohammadz1997), [@Mohii_Mhmdi](https://github.com/Mohii_Mhmdi), [@Faye_Am02](https://github.com/Faye_Am02) |
| 🧹 **Preprocessing & Feature Engineering** | Data cleaning, imbalance handling, feature transformation | [@FarshadZ1997](https://github.com/FarshadZ1997), [@Hossein_h8304](https://github.com/Hossein_h8304), [@nelisazarenejad](https://github.com/nelisazarenejad) |
| 🤖 **ML Modeling** | Algorithm selection, training, hyperparameter tuning | [@Erfanjenab86](https://github.com/Erfanjenab86), [@fr_maral](https://github.com/fr_maral), [@EYNA_SN](https://github.com/EYNA_SN) |
| 📊 **Evaluation & Research** | Metric selection, model comparison, literature review | [@nelisazarenejad](https://github.com/nelisazarenejad), Reyhane, **me** |
| 🚀 **Backend & Deployment** | FastAPI service, Dockerization, demo delivery | *TBD* |

---

## 🗺️ Roadmap

- [ ] Finalize and publish measured model metrics
- [ ] Add SHAP-based model explainability dashboard
- [ ] Implement real-time streaming inference endpoint
- [ ] Deploy to a public cloud environment (e.g., Render / AWS / Azure)
- [ ] Add automated CI/CD pipeline for model retraining

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<p align="center">
  Built with 🧠 and ☕ by <b>AI Builders Iran</b>
</p>
