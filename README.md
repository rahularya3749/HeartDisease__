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
```
├── heart_disease_analysis.ipynb → Data exploration, preprocessing, EDA, feature engineering, model training (XGBoost), evaluation, and interpretation.
├── heath-AB-testing.ipynb → A/B testing on risk factors (ST\_Slope, cholesterol, high cholesterol thresholds).
├── 3.1 Heart Disease Dashboard.png → Screenshot of PowerBI dashboard.
├── 3.2 heart_disease_dashboard.pdf → PDF export of dashboard.
├── 3.3 heart_diease_dashboard_temp.pbit → PowerBI template file.
├── README.md → Project documentation.
```
---

## Requirements

Install the following Python libraries:

* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn
* xgboost
* optuna
* shap
* scipy

For the dashboard:

* [Microsoft Power BI Desktop](https://powerbi.microsoft.com/) (free download).

---

## Usage

1. **Clone the Repository**:

   ```
   git clone https://github.com/your-username/heart-disease-prediction.git
   cd heart-disease-prediction
   ```

2. **Run the Main Notebook**:

   * Open `heart_disease_analysis.ipynb` in Jupyter Notebook or JupyterLab.
   * Execute cells sequentially for data loading, EDA, modeling, and evaluation.

3. **Run the A/B Testing Notebook**:

   * Open `heath-AB-testing.ipynb` in Jupyter.
   * Execute to reproduce hypothesis tests on ST\_Slope, cholesterol, and high-cholesterol thresholds.

4. **View the Dashboard**:

   * Open `3.3 heart_diease_dashboard_temp.pbit` in Power BI Desktop to interact with the dashboard.
   * Or view the static image (`3.1 Heart Disease Dashboard.png`) or PDF (`3.2 heart_disease_dashboard.pdf`).

---

## Workflow

1. Data exploration & cleaning
2. Exploratory data analysis (EDA)
3. Feature engineering & encoding
4. Train/validation/test split (70/20/10)
5. Modeling with XGBoost + Optuna
6. Evaluation (confusion matrix, ROC, SHAP)
7. A/B testing for clinical insights
8. Dashboard visualization in Power BI

---

## Key Results

**Model Performance (XGBoost):**

* Train Accuracy: **97.58%**
* Test Accuracy: **85.87%**
* ROC AUC: **0.9273**

**Classification Report (Test):**

* Class 0 (No Disease): Precision 0.80, Recall 0.90, F1 0.85
* Class 1 (Disease): Precision 0.91, Recall 0.82, F1 0.87

**Top Predictors (SHAP):**

* ST\_Slope × MaxHR
* ChestPainType × ST\_Slope
* Sex & RiskScore

---

## A/B Testing Insights

1. **ST\_Slope (Flat vs. Down)** → Not significant (p = 0.326).
2. **Cholesterol (Disease vs. No Disease)** → Significant (p = 0.0022).
3. **High Cholesterol (>240 mg/dL)** → Highly significant (p < 1e-8).

These tests provide statistical evidence to support screening and intervention decisions (e.g., prioritizing cholesterol control).

---

## Dashboard Preview

![Heart Disease Dashboard](./3.1%20Heart%20Disease%20Dashboard.png)

---

## Important Links

* Project data (Kaggle): [https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)
* UCI Heart Disease dataset: [https://archive.ics.uci.edu/ml/datasets/heart+disease](https://archive.ics.uci.edu/ml/datasets/heart+disease)
* Power BI: [https://powerbi.microsoft.com/](https://powerbi.microsoft.com/)

---

## Contributing

Contributions welcome! Fork the repo and submit a pull request with improvements, bug fixes, or additional analyses.

---

## Author

Project by **Arya Rahul**
📧 [rahularya3749@gmail.com](mailto:rahularya3749@gmail.com) | 🔗 [LinkedIn](https://www.linkedin.com/in/rahul-arya--1810zoro/) | 💻 [GitHub](https://github.com/rahularya3749)



