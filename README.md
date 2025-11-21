# 🧠 Interpretable AI: SHAP Analysis of Survival Model

## 📌 Project Overview
This project applies survival analysis techniques to the Wisconsin Breast Cancer Dataset.
The goal is not only to predict survival outcomes but also to interpret model predictions using SHAP (SHapley Additive Explanations).
We simulate survival times and events based on tumor features, train a survival model, and use SHAP to explain both global feature importance and individual patient risk predictions.

---

## 🎯 Objectives
1. Implement and cross-validate a survival model (XGBoost with survival objective).
2. Evaluate model performance using C-index and Brier Score.
3. Perform global SHAP analysis to identify top risk factors.
4. Generate local SHAP force plots for contrasting patients (low-risk vs high-risk).
5. Summarize findings and discuss trade-offs between model complexity and interpretability.

---

## 📂 Dataset
- **Source:** Wisconsin Breast Cancer Dataset (Kaggle)
- **Features:** Tumor characteristics (radius, texture, smoothness, etc.)
- **Labels:**
  - duration: simulated survival time
  - event: simulated event indicator (1 = event occurred, 0 = censored)

---

## ⚙️ Methodology
1. **Data Preparation**
   - Loaded dataset from Google Drive in Colab
   - Encoded categorical features
   - Scaled numeric features
   - Simulated survival labels (duration, event)

2. **Modeling**
   - Trained XGBoost survival model (survival:aft objective)
   - Evaluated with C-index and Brier Score

3. **Interpretability**
   - Global SHAP summary plot: ranked top 5 features
   - Local SHAP force plots: explained predictions for low-risk and high-risk patients

---

## 📊 Results
- **C-index:** ~0.70
- **Brier Score:** Low values indicate good calibration
- **Top 5 Features (SHAP importance):**
  1. radius_mean
  2. texture_mean
  3. smoothness_mean
  4. concavity_mean
  5. symmetry_mean

- **Local SHAP Insights:**
  - Low-risk patient: Small tumor radius and low concavity reduced predicted risk
  - High-risk patient: Large tumor radius and high concavity increased predicted risk

---

## 📁 Deliverables
- shap_summary.png → Global SHAP summary plot
- force_low.png → SHAP force plot for low-risk patient
- force_high.png → SHAP force plot for high-risk patient
- metrics.txt → Model evaluation metrics
- README.md → Project documentation

---

## 📝 Conclusion
This project demonstrates how SHAP values provide transparency in survival analysis.
By interpreting both global and local feature contributions, we gain insights into risk factors and validate domain hypotheses.
The balance between model complexity and interpretability is achieved by combining XGBoost’s predictive power with SHAP’s explainability.

---

## 🚀 How to Run
1. Upload dataset to Google Drive (breast_cancer.csv).
2. Open Google Colab and run the provided notebook/script.
3. Outputs (plots + metrics) will be saved back to Google Drive.
