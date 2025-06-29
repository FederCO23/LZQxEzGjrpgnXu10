## Customer Satisfaction Study – Predicting Satisfaction from Survey Data

<table>
  <tr>
    <td style="vertical-align: top; padding-right: 20px; line-height: 1.6; font-size: 16px;">

<b>The goal of this project</b> was to analyze and model customer satisfaction for an app-based logistics company, based on real survey responses using machine learning techniques.  

This study showcases:
- Data preprocessing  
- Feature engineering  
- Model selection & evaluation  
- Communication of business insights

<br>

<b>This project was completed as part of the Apziva ML Program.</b>

</td>
    <td style="text-align: center;">
      <img src="images/banner.png" alt="Food Delivery App Promo" width="2300">
    </td>
  </tr>
</table>


## Project Summary

- **Objective:** Predict customer happiness based on the answers provided in survey responses.
- **Approach:** Built and evaluated multiple machine learning models including SVMs and ensemble tree-based classifiers.
- **Outcome:** Achieved robust performance with interpretable results; the best accuracy reached 76.9% using a minimal feature set.
- **Recommendation:** Highlight the key predictive features and propose new questions to maximize the value of customer feedback.

---

## Project Workflow

### 1. Exploratory Data Analysis (EDA)
[Dataset](./ACME-HappinessSurvey2020.csv) 

- Assessed class balance, feature distributions, and potential correlations.
- Calculate the Mutual Information and Chi-Squared scores indentifing the more predictive or informative features for the possitive prediction.

### 2. Feature Engineering
- Created and tested a large group of new features, including:
- Weighted sum for the strongest contributors: `X_1_5_6_weighted`
- Binary indicators: e.g., `X1_is_5`, `X6_is_5`
- Binary flags: e.g., `X2_dissappointed`, `X4_bad_price`
- Aggregated features such as `X_avg_all` and `num_fives`.

### 3. Model Training
- Compared multiple classifiers (27 models): **NuSVC**, **ExtraTreesClassifier**, **RandomForestClassifier**, and more using the Lazypredict library.
- Experiment with hyperparameters optimization and evaluated performance through cross-validation accuracy.

### 4. Evaluation Strategy
- Performed exhaustive feature selection considering Mutual Information and Chi-Square Scores, and also Partial Dependence on Prediction.
- Measured accuracy over a fixed train/test split using all the combinations between the best 6 performing models with all the possible groups of features between a sub-selection of 4 to 10 features from the intermediary 12 feature selection. This *brute-force* approach has been chossen because the dataset was limited and the training time was very quick.
- Using cross-validations accuracy over 5 stratified folds, measured average accuracy and variance to ensure model robustness, where we evaluate the performance of the 14 best performing pair of models and group of selected features.
- Identified top-performing combinations with highest predictive power.

### 5. Insights
- Found that models with fewer well-engineered features performed comparably to those using the full set.
- ExtraTreesClassifier and RandomForestClassifier offered the best trade-off between performance and consistency.

### 6. Key Results

<table>
  <tr style="background-color: #f0f0f0;">
    <th>Model</th>
    <th>Top Features Used</th>
    <th style="text-align: center;">Accuracy (%)</th>
    <th style="text-align: center;">Cross-Validated Accuracy (Mean±Std)</th>
  </tr>
  <tr style="background-color: #ffffff;">
    <td>ExtraTreesClassifier</td>
    <td style="font-size: 14px;">[X1, X3, X6, X1_is_5, X6_is_5, num_fives]</td>
    <td style="text-align: center;">76.9</td>
    <td style="text-align: center;">0.682 ± 0.044</td>
  </tr>
  <tr style="background-color: #ffffff;">
    <td>RandomForestClassifier</td>
    <td style="font-size: 14px;">[X1, X3, X6, X1_is_5, X6_is_5, num_fives]</td>
    <td style="text-align: center;">76.9</td>
    <td style="text-align: center;">0.674 ± 0.047</td>
  </tr>
</table>

<p><i>Note: The top-performing sets share critical features, confirming their predictive strength.</i></p>


---

### 7. Study Conclusion and Recommendation (Condensed Version)

This study aimed not only to predict customer satisfaction based on survey data but also to identify the most informative questions for future surveys. Through feature engineering and robust evaluation (including recall on the negative class), we confirmed that:

- A minimal set of six features performed best, particularly with ExtraTreesClassifier and RandomForestClassifier.
- When optimizing for recall on dissatisfied customers, the same configurations were most effective.
- Three core questions consistently drove satisfaction predictions: delivery timeliness (X1), completeness of the order (X3), and app usability (X6).

To enhance future survey design:

- **Retain** X1, X3, and X6 as essential questions.
- **Remove** less informative items (e.g., X2, X4, X5).
- **Add** new 2 proposed questions on communication and packaging quality.
- **Include** a classification question asking customers to identify the main driver behind their satisfaction.

This refined survey approach boosts insight quality while reducing cognitive load, helping businesses act swiftly on dissatisfaction signals and improve customer retention.

---

### Tools & Libraries

- **Languages & Frameworks:** Python, NumPy, Pandas, Scikit-learn
- **Visualization:** Matplotlib, Seaborn
- **Utilities:** Lazypredict for fast model exploration

---

### 💼 Why This Project Matters to Employers

This project highlights:

- An ML pipeline from raw data to actionable insight.
- Creativity in feature engineering with a strong focus on interpretability.
- Rigorous cross-validation, metric selection, and performance analysis.
- Business-oriented thinking: recommending actionable changes to survey design based on model insights.

Independently completed, this project reflects real-world readiness, combining technical depth with a product-driven mindset.

---

## Repository Contents

- [`HappyCustomers.ipynb`](https://github.com/FederCO23/LZQxEzGjrpgnXu10/blob/main/HappyCustomers.ipynb): Full notebook with code, model training, and visualizations.

---

## 🚀 Contact

**Federico Bessi**  
Email: federico.bessi@gmail.com  
[LinkedIn Profile](https://www.linkedin.com/in/federico-bessi/)
