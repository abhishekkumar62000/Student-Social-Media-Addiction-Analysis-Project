# Student Social Media Addiction Analysis & Prediction
<img width="1082" height="862" alt="image" src="https://github.com/user-attachments/assets/3f211c58-c5d3-410c-9282-7d3c9269ed45" />
<img width="1522" height="642" alt="image" src="https://github.com/user-attachments/assets/fb14a20f-b4b5-41c8-bdf4-29ce64d47739" />
<img width="528" height="595" alt="image" src="https://github.com/user-attachments/assets/3f0afebb-5adb-4c0e-bdd8-b2490c24df44" />
  
 
## Overview  
This project analyzes and models social media addiction among students based on survey data. The workflow starts  with extensive data processing and feature engineering, then builds and compares multiple machine learning models to predict an "Addicted_Score" for each student. 
 
## Dataset   
     
- **Source:** `Students Social Media Addiction.csv` (contains 705 samples, 13 features per student)
- Features include: social media usage patterns, sleep time, mental health score, frequency of conflicts over social media, and more.

## Methodology

### 1. Feature Engineering
- Derived new attributes such as:
  - **Age Group:** Teen, Young Adult, Adult
  - **Usage Intensity:** Light, Moderate, Heavy
  - **Sleep Quality:** Poor, Adequate, Good
  - **Mental Health Category:** Low, Medium, High
  - **Ratio and interaction features** (e.g., Usage/Sleep Ratio, Usage × Mental Health Score)
- Original features: 13, after engineering: 23

### 2. Data Preparation
- Grouped top 15 countries; all others labeled “Other”, for less sparse one-hot encoding.
- Split data into training (80%) and test (20%) sets.

### 3. Encoding & Scaling
- One-hot encoded categorical features (total: 61 columns after encoding).
- Scaled all numerical features using standardization.

### 4. Modeling
Trained multiple regression models:
- Linear Regression (baseline)
- Ridge & Lasso Regression
- Random Forest Regressor
- Gradient Boosting Regressor
- XGBoost Regressor (if available)

#### Model Evaluation Metrics
- **RMSE** (Root Mean Square Error)
- **MAE** (Mean Absolute Error)
- **R²** (Coefficient of Determination)

#### Best Model Performance
- **Random Forest** performed best, with:
  - Test RMSE: ~0.18
  - Test MAE: ~0.06
  - Test R²: ~0.99

### 5. Visualization
- Bar plots comparing model metrics (RMSE, MAE, R²)
- Predicted vs Actual Addicted Score
- Residual plots and error distributions for best model
- Feature importance visualization (when supported)

## Key Results

- Random Forest and XGBoost significantly outperformed linear models.
- Feature engineering and handling categorical variables contributed to strong model performance.
- The analysis reveals factors strongly correlated with social media addiction, such as usage time, sleep quality, conflict frequency, and mental health.

## How to Run

1. Place the CSV dataset with the notebook.
2. Execute all cells in order—dependencies: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `xgboost` (optional).
3. Visualizations and model performance output directly in the notebook.

## Repository Structure

- `social-media-addiction-prediction.ipynb` – Main notebook for modeling and analysis
- `students-social-media-addiction-eda.ipynb` – Exploratory Data Analysis (EDA)
- `Students Social Media Addiction.csv` – The dataset file

---

**This project demonstrates the power of feature engineering and advanced regression models for behavioral data and can be adapted to similar social media or digital behavior studies.**

> For more details, check the notebook: [social-media-addiction-prediction.ipynb](social-media-addiction-prediction.ipynb)
