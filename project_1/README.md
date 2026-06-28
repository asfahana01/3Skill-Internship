# 🍷 Wine Quality: Machine Learning Project

A complete end-to-end Machine Learning project that predicts whether a red wine is **GOOD** or **BAD** based on its physicochemical properties.

---

## 📌 Problem Statement

Given a set of chemical features (acidity, alcohol, pH, etc.), classify a wine as:
- **GOOD (1)** → quality score ≥ 7
- **BAD (0)**  → quality score < 7

---

## 📂 Project Structure

```
3Skill Internship/
├project_1/
│     ├── .venv/                    # Virtual environment (not tracked by git)
│     ├── wine_quality_ml.ipynb     # Main notebook
│     ├── winequality.csv           # Dataset (Red Wine Quality)
│     ├── README.md                 <-- you are here
│     └── .gitignore
│
│
├project_2/
│
│
│
├── README.md 
├── .gitattributes
└── LICENSE
```

---

## 📊 Dataset

| Property        | Detail                          |
|-----------------|---------------------------------|
| Source          | UCI Machine Learning Repository |
| Rows            | 1,599                           |
| Features        | 11 physicochemical inputs       |
| Target          | `quality` (score 3–8)           |
| Task            | Binary Classification           |

**Features:** `fixed acidity`, `volatile acidity`, `citric acid`, `residual sugar`,
`chlorides`, `free sulfur dioxide`, `total sulfur dioxide`, `density`, `pH`,
`sulphates`, `alcohol`

---

## 🔧 Setup & Installation

### 1. Clone the repository
```bash
git clone https://github.com/asfahana01/wine-quality-ml.git
cd wine-quality-ml
```

### 2. Create & activate virtual environment
```bash
# Create
python -m venv venv

# Activate (Windows)
venv\Scripts\activate

# Activate (Mac/Linux)
source venv/bin/activate
```

### 3. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn notebook ipykernel
```

### 4. Register kernel & open notebook
```bash
python -m ipykernel install --user --name=wine-venv --display-name "Python (wine-venv)"
```
Open `wine_quality_ml.ipynb` in VS Code and select **Python (wine-venv)** as the kernel.

---

## 🚀 Workflow

```
Load Data → EDA → Missing Value Check → Correlation Analysis
    → Binary Target → Train-Test Split
        → Logistic Regression (no scaling)
        → Logistic Regression (StandardScaler)
        → Model Comparison (LR vs KNN vs Decision Tree)
        → Hyperparameter Tuning (GridSearchCV)
        → Feature Importance Analysis
        → Final Summary
```

---

## 📈 Models Used

| Model                | Library                        |
|----------------------|--------------------------------|
| Logistic Regression  | `sklearn.linear_model`         |
| K-Nearest Neighbours | `sklearn.neighbors`            |
| Decision Tree        | `sklearn.tree`                 |

---

## 📉 Evaluation Metrics

- **Accuracy** – overall correctness
- **Precision** – of all predicted GOOD, how many were actually GOOD
- **Recall** – of all actual GOOD wines, how many did we catch
- **F1-Score** – harmonic mean of Precision & Recall
- **Confusion Matrix** – breakdown of TP, TN, FP, FN

---

## 🏆 Key Findings

- `alcohol` is the strongest **positive** predictor of wine quality
- `volatile acidity` is the strongest **negative** predictor
- StandardScaler consistently improves Logistic Regression performance
- GridSearchCV with 5-fold CV was used to tune the best model

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.x-green)
![Scikit--learn](https://img.shields.io/badge/Scikit--learn-1.x-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-yellow)
![VS Code](https://img.shields.io/badge/VS%20Code-Editor-blue)

---

## 👤 Author

**Asfa Hana**
- 🔗 [LinkedIn](https://www.linkedin.com/in/asfa-hana-a6a36a391/)
- 🐙 [GitHub](https://github.com/asfahana01)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
