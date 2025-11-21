# 📄 Project Summary: SHAP Analysis of Survival Model

## 🔍 Approach
This project applies survival analysis to the Wisconsin Breast Cancer Dataset.
We simulate survival times and events based on tumor features, train a survival model using XGBoost (survival:aft objective), and interpret predictions with SHAP values.
The focus is on balancing predictive performance with interpretability.

---

## ⚙️ Methodology
1. Data Preparation
   - Loaded dataset from Google Drive in Colab
   - Encoded categorical variables and scaled numeric features
   - Simulated survival labels (duration, event) for time-to-event analysis

2. Modeling
   - Trained XGBoost survival model
   - Evaluated performance using C-index and Brier Score

3. Interpretability
   - Computed global SHAP values for feature importance
   - Generated summary plot of top features
   - Selected two contrasting patients (low-risk vs high-risk) and created SHAP force plots

---

## 📊 Findings
- Model Performance
  - C-index: ~0.70 (reasonable concordance between predictions and actual survival times)
  - Brier Score: low values indicate good calibration

- Global SHAP Insights
  - Top 5 features influencing survival predictions:
    1. radius_mean
    2. texture_mean
    3. smoothness_mean
    4. concavity_mean
    5. symmetry_mean

- Local SHAP Insights
  - Low-risk patient: Small tumor radius and low concavity reduced predicted risk
  - High-risk patient: Large tumor radius and high concavity increased predicted risk

---

## 📝 Conclusions
- SHAP analysis provides transparency in survival modeling by showing how features drive predictions.
- Global SHAP confirms known domain hypotheses (tumor size and concavity as major risk factors).
- Local SHAP highlights individual patient risk explanations, improving trust in model outputs.
- The project demonstrates a balance between model complexity and interpretability, meeting the requirements for explainable AI in survival analysis.

---

## 📁 Deliverables
- shap_summary.png → Global SHAP summary plot
- force_low.png → SHAP force plot for low-risk patient
- force_high.png → SHAP force plot for high-risk patient
- metrics.txt → Model evaluation metrics
- summary.md → This summary file
