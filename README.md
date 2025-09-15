# Mini Data Analysis Project

## Overview  
This project demonstrates a **full data analysis workflow** on a small customer dataset (~45 rows).  
The analysis is performed entirely in a **Jupyter Notebook (`analysis.ipynb`)**.  

The dataset was designed with missing values, duplicates, and inconsistent categorical entries to reflect **real-world data challenges**.  

---

## Dataset Details  

**File:** `week4_dataset.csv`  

Columns:  
- **CustomerID** → Unique identifier  
- **Age** → Customer age (numeric, may contain missing values)  
- **Annual_Income_k** → Annual income in thousands (numeric)  
- **SpendingScore** → Customer spending score (numeric, 1–100)  
- **Gender** → Male/Female (with inconsistent spellings, cleaned later)  
- **Region** → Region of residence (some missing, standardized)  
- **Membership** → Loyalty membership (Yes/No, inconsistent spellings cleaned)  

---

## Workflow (Notebook Steps)  

### 1. Data Loading & Cleaning  
- Loaded dataset using **pandas**.  
- Standardized categorical values (e.g., `male/M/male` → `Male`).  
- Filled missing values:  
  - `Age` → median  
  - `Annual_Income_k` → mean  
  - `Region` → "Unknown"  
- Removed duplicates.  
- Saved as **`week4_dataset_cleaned.csv`**.  

### 2. Data Transformation  
Created two derived columns:  
- **Income_USD** → `Annual_Income_k * 1.2` (currency conversion).  
- **Affluence_Index** → `Annual_Income_k * (SpendingScore / 100)` (proxy for purchasing power).  

### 3. Exploratory Analysis  
- Summary statistics of numerical columns.  
- Frequency counts for categorical variables.  
- Correlation matrix between numerical features.  

### 4. Visualization  
All plots are saved in the **`plots/`** folder:  
-  **Histogram** → Age distribution (`hist_age.png`)  
-  **Bar chart** → Gender distribution (`bar_gender.png`)  
-  **Scatter plot** → Income vs SpendingScore (`scatter_income_spending.png`)  

---

## Key Insights  
1. Higher **annual income** tends to align with higher **Affluence Index**, but the relationship with SpendingScore is weak.  
2. **Gender distribution** in this dataset is slightly skewed toward males.  
3. Cleaning revealed inconsistent entries like `"m"`, `"FEMALE"`, `"yes/YES"`, which were standardized.  
4. Missing values were handled logically — **median for Age**, **mean for Income**, and `"Unknown"` for Region.  

---

## How to Use  
1. Open **`analysis.ipynb`** in Jupyter Notebook or VS Code.  
2. Run the cells step by step to reproduce the workflow.  
3. Cleaned dataset and plots will be generated automatically.  

---

## Deliverables  
- `week4_dataset.csv` → Raw dataset  
- `week4_dataset_cleaned.csv` → Cleaned dataset  
- `analysis.ipynb` → Jupyter Notebook (main workflow)  
- `plots/` → Generated visualizations  
- `insights.txt` → Summary of findings  

---
# This project was created as a Week 4 mini-task to practice a complete data analysis pipeline using Jupyter Notebook.
