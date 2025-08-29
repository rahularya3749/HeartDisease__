# HeartDisease__
End-to-end data science project on Heart Disease prediction. Covers preprocessing, statistical analysis, visualization, A/B Test, feature engineering, model training, and performance evaluation.


# Heart Disease Prediction & Analysis

## Project Overview
Cardiovascular disease is one of the leading causes of death worldwide. Early detection and accurate prediction can save lives and improve treatment strategies.  
This project explores a combined heart disease dataset, applying **statistical analysis, machine learning, and data visualization** to gain insights and build predictive models.  

The work includes:
- End-to-end **machine learning pipeline** for heart disease classification
- **A/B testing (hypothesis testing)** on clinical risk factors
- An interactive **Power BI dashboard** for data visualization

---

## Dataset
- **Source**: UCI Machine Learning Repository (Cleveland, Hungarian, Switzerland, Long Beach VA, Stalog datasets combined)  
- **Size**: 918 patient records  
- **Features**: 11 clinical attributes  
- **Target Variable**:  
  - `1` → Patient has heart disease  
  - `0` → Patient does not have heart disease  

**Key Features:**
- Age, Sex, Chest Pain Type  
- Resting Blood Pressure, Cholesterol, Fasting Blood Sugar  
- Resting ECG, Max Heart Rate, Exercise Angina  
- Oldpeak, ST Slope  

---

##  Workflow
1. **Data Cleaning & Preprocessing**
   - Handled missing/inconsistent values  
   - Feature engineering (risk scores, binning, interactions)  

2. **Exploratory Data Analysis (EDA)**
   - Correlation heatmaps  
   - Distribution plots & categorical analysis  
   - Clinical insights  

3. **A/B Testing (Statistical Analysis)**
   - Compared groups to test significant differences  
   - Example tests: cholesterol impact, ST slope effect, high cholesterol cutoff  

4. **Machine Learning Modeling**
   - Baseline models → Logistic Regression, Decision Trees, Random Forest  
   - Hyperparameter tuning with **Optuna**  
   - Final model: **XGBoost Classifier**  

5. **Model Evaluation**
   - Accuracy: **85.9%** (Test set)  
   - ROC AUC: **0.93**  
   - Balanced precision & recall across classes  
   - SHAP analysis for feature importance  

6. **Dashboard (Power BI)**
   - Interactive visualizations of age groups, cholesterol, chest pain types, and gender distribution  
   - KPIs for patient statistics and heart disease prevalence  

---

## Results & Insights
- **Cholesterol** is a statistically significant predictor of heart disease  
- Patients with **cholesterol > 240 mg/dL** have a much higher risk (p ≈ 2.3e-09)  
- **ST slope + chest pain type + exercise angina** were among the strongest predictors  
- XGBoost model generalizes well with high discriminative power  
- **Business/Medical Impact**: Cholesterol management and exercise-related monitoring are crucial in risk reduction  

---

## Repository Structure
```
├── 1. heart_disease_analysis.ipynb # Main ML project notebook
├── 2. heart-AB-testing.ipynb # A/B testing & statistical analysis
├── 3.1 Heart Disease Dashboard.png # Power BI dashboard (image)
├── 3.2 heart_disease_dashboard.pdf # Dashboard report
├── 3.3 heart_disease_dashboard_temp.pbit # Power BI template file
├── README.md # Project documentation
```


---

## Dashboard Preview
![Heart Disease Dashboard](./3.1%20Heart%20Disease%20Dashboard.png)

---

## Key Learnings
- End-to-end data science workflow: data → analysis → ML → visualization  
- Importance of combining **statistics + machine learning** for healthcare insights  
- Effective communication of results via **dashboard and interpretation**  

---

## Future Work
- Improve recall to catch more positive cases (reduce false negatives)  
- Explore deep learning models for improved accuracy  
- Deploy as an **API on AWS / Streamlit** for real-time predictions  

---

## Tools & Technologies
- **Python**: pandas, numpy, matplotlib, seaborn, scikit-learn, xgboost, shap, optuna  
- **Statistics**: A/B testing, hypothesis testing, z-tests, t-tests  
- **Visualization**: Matplotlib, Seaborn, Power BI  
- **Version Control**: GitHub  

---

##  Author
Project by **Arya Rahul**  
[Your Email] | [LinkedIn] | [GitHub Profile]  



