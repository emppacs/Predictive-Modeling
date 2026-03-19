# Predictive Modeling: Clinical vs. Behavioral Data

This repository contains two machine learning projects built to compare how different data types (clinical vs. survey-based) affect model performance. I utilized Scikit-Learn Pipelines to ensure the preprocessing was modular, reproducible, and ready for production.

## Project 1: Heart Disease Prediction (85.3% Accuracy)
For this model, I used clinical patient data to predict heart disease risk. I simplified the target variable into a binary "Risk" vs. "No Risk" classification to make it more practical for a medical screening tool.

* **The Approach:** I used a **Random Forest** with a **RobustScaler**. I specifically chose a RobustScaler because medical data like cholesterol often has extreme outliers that can throw off a standard scaler.
* **The Result:** After tuning the model with **GridSearchCV**, I pushed the accuracy from 84% to **85.3%**.
* **Key Findings:** Chest pain type (cp), maximum heart rate (thalch), and ST depression (oldpeak) were the primary predictors of cardiac risk.

## Project 2: Remote Work & Mental Health
This project was an experiment in predicting employee stress levels based on work habits and environment. This was a much tougher dataset to crack.

* **The Challenge:** The model achieved 36.3% accuracy. Since a random guess for three classes is 33.3%, the model found a very slight signal in a highly "noisy" dataset.
* **The Lesson:** Even with hyperparameter tuning, behavioral data like "Industry" or "Job Role" didn't provide a strong mathematical signal. This proved that data quality is often more important than the algorithm itself.
* **Feature Importance:** The analysis revealed that Age, Hours Worked per Week, and Years of Experience were the most influential factors, suggesting stress is more tied to career stage than remote work specifics.

## Tech Stack
* **Modeling:** Scikit-Learn (Pipelines, ColumnTransformer, RandomForest, GridSearchCV).
* **EDA:** Pandas, YData-Profiling, and Seaborn for visualizing distributions.
* **Visualization:** Plotly Express for interactive density heatmaps and Matplotlib for feature importance analysis.

## Repository Structure
* `/notebooks`: Cleaned-up Jupyter notebooks for both models
* `/data`: Raw CSV files