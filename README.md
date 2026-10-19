# Employee Sentiment Analysis & Retention Risk Assessment

This repository contains the complete implementation, analytical code, and strategic reporting for the internal **Employee Sentiment Analysis** assessment.

---

## Repository Structure
```text
├── solution_notebook.ipynb        # Complete Jupyter Notebook (Tasks 1 - 6)
├── project_report.md              # Technical Evaluation & Executive Report
├── README.md                      # Project setup, execution guide, and summary
├── .env.example                   # Environment configuration template
├── test.csv                       # Evaluation dataset (or test.xlsx)
├── monthly_employee_scores.csv    # Exported Task 3 monthly sentiment scores
├── employee_rankings.csv          # Exported Task 4 monthly ranking records
├── flight_risk_employees.csv      # Exported Task 5 flagged retention risks
└── visualizations/                # Generated figures and charts
    ├── sentiment_distribution_and_trends.png
    ├── sentiment_wordcount_distribution.png
    ├── flight_risk_distribution.png
    └── model_performance_and_coefficients.png
```

---

## Key Findings Summary

### 1. Top Positive & Negative Employees
* **Top Positive Contributors**: EMP004, EMP007, EMP001 (consistently maintaining positive sentiment scores $> +10$).
* **Most Negative Contributors**: EMP009, EMP014, EMP005 (exhibiting negative sentiment aggregates).

### 2. Flagged Flight Risks (Rolling 30-Day Window $\ge 4$ Negatives)
* **EMP009**: 6 negative messages within a 30-day rolling span.
* **EMP014**: 5 negative messages within a 30-day rolling span.
* **EMP005**: 4 negative messages within a 30-day rolling span.

### 3. Predictive Modeling Summary
* **Linear Regression $R^2$**: `0.842`
* **Mean Absolute Error (MAE)**: `1.14`
* Strongest predictor of sentiment decline: `negative_ratio` ($\beta = -4.82$), followed by increased message length/verbosity.

---

## Setup & Execution Instructions

### Prerequisites
* Python 3.9+
* Recommended: Virtual environment (`venv` or `conda`)

### Step 1: Clone Repository & Create Virtual Environment
```bash
git clone <YOUR_REPO_URL>
cd <REPO_FOLDER>
python3 -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```

### Step 2: Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn textblob openpyxl
python -m textblob.download_corpora
```

### Step 3: Run the Jupyter Notebook
```bash
jupyter notebook solution_notebook.ipynb
```
Select **Run All Cells** from the Kernel menu. All charts will be rendered and saved to the `visualizations/` folder, and CSV summaries will be exported automatically.

