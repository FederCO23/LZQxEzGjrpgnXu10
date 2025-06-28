# Customer Satisfaction Prediction – Machine Learning from Survey Data

It focuses on predicting customer satisfaction for an app-based logistics company using real-world survey responses. The work demonstrates applied machine learning skills in low-data environments, with a focus on robust feature engineering, thorough evaluation, and actionable business insights.
This project was developed as part of the **Apziva AI Residency Program**. 

---

## Project Summary

- **Objective:** Predict whether customers are satisfied based on their survey responses.
- **Approach:** Performed exploratory data analysis, created tailored features, trained and evaluated a wide range of classification models.
- **Results:** Achieved 76.9% accuracy using a minimal, interpretable feature set.
- **Business Impact:** Identified key survey questions driving satisfaction, enabling survey streamlining and better customer understanding.

---

## 🔁 Project Workflow

### 1. Exploratory Data Analysis (EDA)
- Examined class balance, distribution of responses, and correlations.
- Used visual tools to understand the relationships between features and satisfaction labels.

### 2. Feature Engineering
- Developed binary indicators (e.g., `X1_is_5`, `X6_is_5`).
- Built aggregated and composite metrics (e.g., `X_avg_all`, `num_fives`, `X_1_5_6_weighted`).
- Incorporated domain knowledge to enhance signal extraction.

### 3. Model Training
- Benchmarked 27 classifiers, including NuSVC, ExtraTreesClassifier, and RandomForest.
- Tuned hyperparameters and evaluated models via stratified 5-fold cross-validation.

### 4. Evaluation Strategy
- Conducted exhaustive feature selection with brute-force combinations (4 to 10 features) due to the dataset’s small size and fast iteration speed.
- Used mutual information, chi-square, and partial dependence to guide feature choices.
- Focused on model consistency across folds (accuracy and variance).
- Evaluated recall on the negative class (unsatisfied customers) to reflect the business goal of identifying pain points, confirming the robustness of the best model + feature pair.

### 5. Insights
- Smaller feature sets provided competitive results, increasing model simplicity and interpretability.
- Ensemble models (ExtraTrees, RandomForest) consistently achieved strong performance with low variance.

---


## 📊 Key Results

| Model                 | Top Features Used                                 | Accuracy (%) | Cross-Validated Accuracy (Mean±Std) |
|----------------------|----------------------------------------------------|--------------|-------------------------------------|
| ExtraTreesClassifier | [X1, X3, X6, X1_is_5, X6_is_5, num_fives]          | 76.9         | 0.682 ± 0.044                        |
| RandomForestClassifier | [X1, X3, X6, X1_is_5, X6_is_5, num_fives]                                | 76.9            | 0.674 ± 0.047                        |


  

*Note: The top-performing sets share critical features, confirming their predictive strength.*

---

## 🧩 Tools & Libraries

- **Languages & Frameworks:** Python, NumPy, Pandas, Scikit-learn
- **Visualization:** Matplotlib, Seaborn
- **Utilities:** Lazypredict for fast model exploration

---

## 💼 Why This Project Matters to Employers

This project highlights:

- A complete ML pipeline from raw data to actionable insight.
- Creativity in feature engineering with a strong focus on interpretability.
- Rigorous cross-validation, metric selection, and performance analysis.
- Business-oriented thinking: recommending actionable changes to survey design based on model insights.

Independently completed, this project reflects real-world readiness, combining technical depth with a product-driven mindset.

---

## 📁 Repository Contents

- [`HappyCustomers.ipynb`](https://github.com/FederCO23/LZQxEzGjrpgnXu10/blob/main/HappyCustomers.ipynb): Full notebook with code, model training, and visualizations.

---

## 🚀 Contact

**Federico Bessi**  
Email: federico.bessi@gmail.com  
[LinkedIn Profile](https://www.linkedin.com/in/federico-bessi/)
