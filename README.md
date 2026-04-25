# Churn-Prediction-for-Telecom-Companies
Predictive Analytics Project - Telecom Churn Prediction using XGBoost, Random Forest, and SHAP
# 🛠️ Member 1: Data Engineering & Statistical Insights
**Portion:** Data Preprocessing, Exploratory Data Analysis (EDA), and Class Balancing (SMOTE).

This branch contains the specialized pipeline responsible for transforming raw telecom data into a balanced, high-quality training set for predictive modeling.

---

## Stage 3: Data Preprocessing
The goal was to ensure data integrity and prepare features for the XGBoost engine.
* **Cleaning:** Resolved whitespace issues in `TotalCharges` by converting them to float and imputing **0.0** for customers with zero tenure.
* **Feature Engineering:** * Created `ServiceCount` to quantify customer engagement levels.
    * Developed `ContractRisk` to map ordinal risk based on contract duration.
* **Encoding:** Implemented **One-Hot Encoding** for multi-level categories (Internet Service, Payment Method) to maintain mathematical consistency.

---

## Stage 4: Exploratory Data Analysis (EDA)
I conducted a visual deep-dive to identify the primary drivers of customer attrition using `Seaborn` and `Matplotlib`.

### Key Discovery Highlights:
1. **Contract Type:** Month-to-month subscribers represent the highest churn risk, suggesting a need for loyalty incentives.
2. **Tenure Impact:** Most churn occurs within the first **6 months**, identifying a critical "onboarding" window for retention teams.
3. **Price Friction:** High monthly charges, particularly in the Fiber Optic segment, correlate strongly with negative customer retention.

---

## Stage 5: SMOTE Implementation
To combat the **73/27 class imbalance** found in the original dataset, I utilized **Synthetic Minority Over-sampling Technique (SMOTE)**. 

* **Strategy:** Applied SMOTE strictly to the **Training Set** to avoid data leakage into the test set.
* **Outcome:** Balanced the target classes to a perfect **50/50 distribution**, ensuring the subsequent models (Random Forest/XGBoost) do not develop a bias toward the majority class.

---

## Branch Assets
The following files are unique to this branch's documentation:
* `telco_churn_cleaned.csv`: The final preprocessed dataset.
* `main_code.ipynb`: Contains the full executable pipeline for Stages 3, 4, and 5.
* `*.png`: Visual distributions and correlation heatmaps stored in the root for quick reference.

---

### How to Run this Portion
1. Clone the repository and switch to this branch:
   `git checkout member1/Data-preprocessing/EDA/SMOTE`
2. Ensure `requirements.txt` dependencies are installed.
3. Execute the first 5 stages in `main_code.ipynb` to generate the balanced training arrays.
