# 🤖 AI-Based Hiring Prediction System

An end-to-end Machine Learning project that predicts whether a job candidate will be **Hired** or **Rejected** based on resume information — simulating a real-world AI-powered HR screening system.

---

## 📁 Project Structure

```
3Skill Internship/
│
├project── _1/
│ 
│ 
├project── _2/
│   ├── .venv/                                  ← Python virtual environment (alt)
│   ├── hiring_env/                             ← Primary virtual environment
│   │
│   ├── hiring_project/                         ← Main project folder
│   │   ├── AI_Hiring_Prediction_System.ipynb   ← Main notebook
│   │   ├── AI-Based Hiring Prediction(...).xlsx← Dataset
│   │   │
│   │   ├── hiring_prediction_model.pkl         ← Trained ML model
│   │   ├── feature_scaler.pkl                  ← StandardScaler
│   │   ├── model_metadata.pkl                  ← Encoders + feature names
│   │   │
│   │   ├── categorical_eda.png                 ← EDA chart
│   │   ├── confusion_matrices.png              ← Model evaluation
│   │   ├── correlation_heatmap.png             ← Feature correlation
│   │   ├── feature_importance.png              ← Feature importance chart
│   │   ├── model_comparison.png                ← All models compared
│   │   ├── numeric_features_eda.png            ← Numeric EDA chart
│   │   ├── projects_aiscore_eda.png            ← Projects & AI score EDA
│   │   ├── roc_curves.png                      ← ROC curves
│   │   ├── target_distribution.png             ← Class balance chart
│   │   ├── top_skills.png                      ← Top skills frequency
│   │   └── tuning_comparison.png               ← Before/after tuning
│   │
│   └──README.md                               ← You are here
├── .gitattributes
└── LICENSE
```

---

## 📌 Project Overview

| Property | Details |
|---|---|
| **Type** | Binary Classification |
| **Domain** | HR Analytics / Resume Screening |
| **Dataset** | 1,000 synthetic resumes |
| **Target** | Hired (1) / Rejected (0) |
| **Best Model** | Random Forest (Tuned) |
| **Environment** | VS Code + Jupyter |

---

## 📊 Dataset Description

| Column | Type | Description |
|---|---|---|
| `Resume_ID` | int | Unique candidate identifier |
| `Name` | str | Candidate name |
| `Skills` | str | Comma-separated technical skills |
| `Experience (Years)` | int | Total years of work experience |
| `Education` | str | B.Sc · B.Tech · MBA · M.Tech · PhD |
| `Certifications` | str | Relevant certifications held |
| `Job Role` | str | Applied job role |
| `Recruiter Decision` | str | **Target** — Hire or Reject |
| `Salary Expectation ($)` | int | Expected annual salary |
| `Projects Count` | int | Number of projects completed |
| `AI Score (0-100)` | int | AI-generated resume score |

**Class Distribution:** 81.2% Hire · 18.8% Reject

---

## ⚙️ Feature Engineering

- **Binary skill features** — Top 20 skills one-hot encoded from the Skills column
- **Total skill count** — Number of skills listed per candidate
- **Label encoding** — Education, Certifications, Job Role → numeric
- **Standard scaling** — Applied for distance-based models (LR, SVM, KNN)
- **Total features:** 28+

---

## 🧠 Models Trained

| Model | Type |
|---|---|
| Logistic Regression | Linear |
| Random Forest ⭐ | Ensemble (Best) |
| XGBoost | Gradient Boosting |
| Gradient Boosting | Ensemble |
| SVM | Kernel-based |
| K-Nearest Neighbors | Distance-based |
| Naive Bayes | Probabilistic |

---

## 📈 Results

| Model | Accuracy | F1-Score | AUC-ROC |
|---|---|---|---|
| **Random Forest (Tuned)** | ~0.96 | ~0.97 | ~0.97 |
| XGBoost | ~0.95 | ~0.96 | ~0.96 |
| Gradient Boosting | ~0.94 | ~0.96 | ~0.96 |
| Logistic Regression | ~0.91 | ~0.93 | ~0.94 |
| SVM | ~0.90 | ~0.93 | ~0.93 |

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/asfahana01/AI-Based-Hiring-Prediction-System.git
cd "3Skill-Internship/project_2"
```

### 2. Activate Virtual Environment
```bash
# Windows
hiring_env\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install jupyter pandas numpy matplotlib seaborn scikit-learn xgboost openpyxl joblib
```

### 4. Open the Notebook in VS Code
```bash
code hiring_project/AI_Hiring_Prediction_System.ipynb
```

### 5. Set Working Directory (Cell 7)
```python
import os
os.chdir(r'C:\Users\hanaa\OneDrive\Desktop\GitHub\AI-Based Hiring Prediction System\project_2\hiring_project')
df = pd.read_excel('AI-Based Hiring Prediction System1_csv.xlsx')
```

### 6. Run All Cells
Click **Run All** or press `Shift+Enter` through each cell.

---

## 🔮 Prediction Function

```python
result = predict_hiring(
    experience_years   = 5,
    education          = 'M.Tech',       # B.Sc | B.Tech | MBA | M.Tech | PhD
    certifications     = 'Google ML',    # AWS Certified | Deep Learning Specialization | Google ML
    job_role           = 'Data Scientist',
    salary_expectation = 80000,
    projects_count     = 7,
    ai_score           = 75,
    skills             = 'Python, TensorFlow, NLP, SQL'
)
# ✅ HIRE  |  Confidence: 91.4%
```

---

## 💾 Saved Model Artifacts

| File | Description |
|---|---|
| `hiring_prediction_model.pkl` | Trained Random Forest model |
| `feature_scaler.pkl` | StandardScaler for numeric features |
| `model_metadata.pkl` | Label encoders + feature column list |

---

## 📦 Dependencies

```
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
openpyxl
joblib
jupyter
```

---

## 🚨 Common Issues

| Error | Fix |
|---|---|
| `FileNotFoundError: .xlsx not found` | Add `os.chdir()` pointing to `hiring_project/` |
| `ModuleNotFoundError` | Run `pip install <module>` inside activated `hiring_env` |
| `Kernel not found` | `Ctrl+Shift+P` → Select Kernel → `hiring_env` |
| `ValueError: unseen labels` | Use only valid Education/Role values listed above |
| `move: file in use` | Shutdown kernel + deactivate venv before moving files |

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.x-orange)
![XGBoost](https://img.shields.io/badge/XGBoost-2.x-green)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Pandas](https://img.shields.io/badge/Pandas-2.x-blue)
![VS Code](https://img.shields.io/badge/VS%20Code-Editor-blue)

---

## 📄 License

This project is licensed under the terms of the LICENSE file included in this repository.

---

## 🙋 Author
**Asfa Hana**
- 🔗 [LinkedIn](https://www.linkedin.com/in/asfa-hana-a6a36a391/)
- 🐙 [GitHub](https://github.com/asfahana01)

Built as an end-to-end ML project for HR Analytics and AI Resume Screening.
Feel free to fork, star ⭐, and contribute!
