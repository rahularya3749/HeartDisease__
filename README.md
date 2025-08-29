# HeartDisease__
End-to-end data science project on Heart Disease prediction. Covers preprocessing, statistical analysis, visualization, A/B Test, feature engineering, model training, and performance evaluation.

Got it ✅
Here’s the entire thing in **one markdown cell** (no \`\`\` fencing) — you can directly paste this into your README.md:

# Heart Disease Prediction and Analysis

## Project Overview

Cardiovascular disease is one of the leading causes of death worldwide. Early detection and risk prediction can significantly improve patient outcomes. This project analyzes a heart disease dataset, builds predictive models to classify whether a patient is likely to have heart disease, performs A/B testing to explore key risk factors, and includes a PowerBI dashboard for interactive visualization.

The main focus is on machine learning-based prediction using XGBoost, combined with statistical hypothesis testing (A/B tests) to validate clinical insights. The project demonstrates a complete data science workflow from exploration to model interpretation.

---

## Dataset Description

The dataset is a combination of five well-known heart disease datasets (Cleveland, Hungarian, Switzerland, Long Beach VA, and Statlog), merged into a single collection of 918 patient records with 11 features.

* **Target Variable**: `HeartDisease`

  * 1 → Patient has heart disease
  * 0 → Patient does not have heart disease

* **Features**:

  * `Age`: Patient age (years)
  * `Sex`: Gender (M = Male, F = Female)
  * `ChestPainType`: Chest pain type (TA = Typical Angina, ATA = Atypical Angina, NAP = Non-Anginal Pain, ASY = Asymptomatic)
  * `RestingBP`: Resting blood pressure (mm Hg)
  * `Cholesterol`: Serum cholesterol (mg/dl)
  * `FastingBS`: Fasting blood sugar (1 if >120 mg/dl, else 0)
  * `RestingECG`: Resting electrocardiogram results (Normal, ST = ST-T wave abnormality, LVH = Left ventricular hypertrophy)
  * `MaxHR`: Maximum heart rate achieved (60–202 bpm)
  * `ExerciseAngina`: Exercise-induced angina (Y = Yes, N = No)
  * `Oldpeak`: ST depression induced by exercise
  * `ST_Slope`: Slope of the ST segment (Up, Flat, Down)

* **Source**: [Kaggle - fedesoriano/heart-failure-prediction](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)
  *(Original records curated from the UCI Heart Disease datasets — Cleveland, Hungarian, Switzerland, Long Beach VA, Statlog.)*

---
## Repository Structure
- **`1. heart_disease_analysis.ipynb`**: Main notebook for data exploration, preprocessing, EDA, feature engineering, model training (XGBoost), evaluation, and interpretations (including SHAP and ROC).
- **`2. heath-AB-testing.ipynb`**: Notebook for A/B testing (hypothesis tests) on key risk factors like ST_Slope, cholesterol levels, and high cholesterol thresholds.
- **`3.1 Heart Disease Dashboard.png`**: Screenshot of the PowerBI dashboard.
- **`3.2 heart_disease_dashboard.pdf`**: PDF export of the PowerBI dashboard.
- **`3.3 heart_diease_dashboard_temp.pbit`**: PowerBI template file for the dashboard.
- **`README.md`**: This file.
---

## Requirements
To run the notebooks, install the following Python libraries (via `pip install -r requirements.txt` if provided, or manually):

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- xgboost
- optuna (for hyperparameter tuning)
- shap (for model interpretability)
- scipy (for statistical tests)

For the PowerBI dashboard:
- Microsoft PowerBI Desktop (free download from [Microsoft](https://powerbi.microsoft.com/)).

No additional datasets are needed; the notebooks assume the data is loaded from a standard source (e.g., via pandas or direct import).

---

## Usage
1. **Clone the Repository**:
   ```
   git clone https://github.com/your-username/heart-disease-prediction.git
   cd heart-disease-prediction
   ```

2. **Run the Main Notebook**:
   - Open `heart_disease_analysis.ipynb` in Jupyter Notebook or JupyterLab.
   - Execute cells sequentially for data loading, EDA, modeling, and evaluation.

3. **Run the A/B Testing Notebook**:
   - Open `heath-AB-testing.ipynb` in Jupyter.
   - Perform hypothesis tests on the dataset.

4. **View the Dashboard**:
   - Open `3.3 heart_diease_dashboard_temp.pbit` in PowerBI Desktop.
   - Alternatively, view the static image (`3.1 Heart Disease Dashboard.png`) or PDF (`3.2 heart_disease_dashboard.pdf`).

---

## Workflow
The project follows this structure:

1. **Data Exploration and Descriptive Statistics**: Profiling, cleaning (handling outliers in Cholesterol, RestingBP, Oldpeak).
2. **Exploratory Data Analysis (EDA)**:
   - Correlation heatmap.
   - Univariate distributions (e.g., age, cholesterol).
   - Categorical breakdowns (e.g., donut charts for gender, chest pain).
   - Trivariate visualizations for continuous features.
3. **Feature Engineering**:
   - Domain-informed features (e.g., risk scores).
   - Encoding categorical variables.
   - Feature interactions (e.g., ChestPainType_ST_Slope).
4. **Train/Valid/Test Split**: 70/20/10.
5. **Feature Importance**: Calculated and evaluated using model-based methods.
6. **Pre-Model Baseline**: Pipeline setup and base model evaluation.
7. **ML Modeling**:
   - Hyperparameter tuning with Optuna.
   - Model comparison.
   - Final model: XGBoost Classifier.
8. **Evaluation and Insights**:
   - Confusion matrix, SHAP explanations, ROC curve.
9. **A/B Testing**: Hypothesis tests on risk factors (detailed below).
10. **Dashboard**: Interactive visualizations in PowerBI.

---

## Key Insights from ML Model

- **Model Performance**:
  - Training Accuracy: 97.58%, Test Accuracy: 85.87%.
  - ROC AUC (Test): 0.9273.
- **Classification Report (Test)**:
  - Class 0 (No Disease): Precision 0.80, Recall 0.90, F1 0.85.
  - Class 1 (Disease): Precision 0.91, Recall 0.82, F1 0.87.
- **Confusion Matrix**: TN=37, FP=4, FN=9, TP=42.
- **Top Features (SHAP)**:
  - ST_Slope_max_hr_bins (0.95).
  - ChestPainType_ST_Slope (0.80).
  - Sex_RiskScore_coded (0.71).
- **Overall**: The model shows strong generalization, with exercise-related and chest pain features as dominant predictors. Future work could tune for higher recall to reduce missed positives.


---

## A/B Testing Insights

Three hypothesis tests were conducted to explore risk factors:

1. **ST_Slope Effect (Flat vs. Down)**:
   - Heart disease rate: Flat (82.8%) vs. Down (77.7%).
   - p-value: 0.326 (>0.05) → Not significant.
   - Insight: ST_Slope alone isn't a reliable predictor; combine with other features.

2. **Cholesterol Difference (With vs. Without Disease)**:
   - Average cholesterol: Disease (249.3) vs. No Disease (238.6).
   - p-value: 0.0022 (<0.05) → Significant.
   - Insight: Higher cholesterol is a key risk factor; include in screening programs.

3. **High Cholesterol Risk (>240 mg/dL vs. ≤240)**:
   - p-value: 2.3e-09 (<0.05) → Highly significant.
   - Insight: >240 mg/dL is a strong cutoff for risk stratification; prioritize interventions.

These tests provide statistical evidence for clinical and business decisions, such as targeted cholesterol management (e.g., prioritizing cholesterol control).

---

## Dashboard Preview

The PowerBI dashboard visualizes key metrics:
- Total Patients: 918.
- Heart Disease %: 55.34%.
- Age Group Distribution: Highest in 50-59.
- Gender: 78.98% Male.
- Chest Pain Type vs. Heart Disease: ASY highest risk (86.13%).
- Average Max HR by Age: Declining trend.
- And more (see screenshot below).

![Heart Disease Dashboard](./3.1%20Heart%20Disease%20Dashboard.png)

For interactive exploration, load the `.pbit` file in PowerBI.

---

## Important Links

* Project data (Kaggle): [https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)
* UCI Heart Disease dataset: [https://archive.ics.uci.edu/ml/datasets/heart+disease](https://archive.ics.uci.edu/ml/datasets/heart+disease)
* Power BI: [https://powerbi.microsoft.com/](https://powerbi.microsoft.com/)

---

## Author

Project by **Arya Rahul**
📧 [rahularya3749@gmail.com](mailto:rahularya3749@gmail.com) | 🔗 [LinkedIn](https://www.linkedin.com/in/rahul-arya--1810zoro/) | 💻 [GitHub](https://github.com/rahularya3749)



