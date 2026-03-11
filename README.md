# 🔍 Fraud Detection System — Generic Multi-Domain

An intelligent, multi-signal fraud detection pipeline that works across **multiple domains** 
(insurance, banking, mobile payments) without any code changes. Combines anomaly detection, 
behavioral profiling, and explainable AI to classify transactions as APPROVE, MANUAL_REVIEW, or BLOCK.

## 🚀 Key Highlight
> **Dataset-Agnostic Design** — Same pipeline tested successfully on 4 different real-world 
> and synthetic datasets without modifying core logic.

## ⚙️ Features

- **Generic Data Adapter** — Auto-detects column names across different dataset formats
- **User Behavioral Profiling** — Detects amount spikes relative to each user's own history
- **Temporal Cluster Analysis** — Identifies suspicious clustering around same hospital/agent/village
- **Isolation Forest** — Unsupervised anomaly detection (no labeled data needed)
- **Explainability Engine** — Every decision comes with human-readable reasons
- **Belief Scoring** — Soft probabilistic scoring using sigmoid-based belief fusion

## 🧠 How It Works
```
Raw CSV → Generic Adapter → User Profiling + Cluster Analysis + Risk Engine
        → Explanation Engine → Belief Score → Final Decision (APPROVE / REVIEW / BLOCK)
```

## 📊 Decision Categories

| Decision | Meaning |
|----------|---------|
| ✅ APPROVE | Low risk, normal behavior |
| ⚠️ MANUAL_REVIEW | 2+ suspicious signals detected |
| 🚫 BLOCK | Strong fraud indicators across all signals |

## 📂 Datasets Tested

| # | Dataset | Source | Domain |
|---|---------|--------|--------|
| 1 | IEEE-CIS Fraud Detection | Kaggle | Credit card transactions |
| 2 | Credit Card Fraud Detection | Kaggle | European card transactions (PCA features) |
| 3 | PaySim Mobile Money Fraud | Kaggle | Mobile payment systems |
| 4 | Synthetic Insurance Claims | Created for this project | Village-level insurance fraud |

## 🛠️ Tech Stack

- Python, Pandas, NumPy
- Scikit-learn (Isolation Forest)
- Rule-based + ML hybrid approach

## ▶️ How to Run

1. Upload any supported CSV to Google Colab
2. Run all cells in `URT_XFraud.ipynb`
3. Output shows per-claim decisions + summary count

## 💡 Why Generic?

Most fraud detection models are trained on one specific dataset. 
This system uses a **Generic Adapter** that auto-maps column names, 
making it plug-and-play across finance, insurance, and mobile payment domains.
