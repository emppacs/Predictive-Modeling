# Predictive Modeling: Clinical vs. Behavioral Data

This repository contains two machine learning projects I built to compare how different types of data (clinical vs. survey-based) affect model performance. I focused on using **Scikit-Learn Pipelines** to keep the preprocessing clean and reproducible.

## Project 1: Heart Disease Prediction (85.3% Accuracy)
For this model, I used clinical patient data to predict heart disease risk. I chose to simplify the target variable into a binary "Risk" vs. "No Risk" classification to make it more practical for a medical screening tool.

* **The Approach:** I used a **Random Forest** with a **RobustScaler**. I specifically chose a RobustScaler because medical data like cholesterol often has extreme outliers that can throw off a standard scaler.
* **The Result:** After tuning the model with **GridSearchCV**, I pushed the accuracy from 84% to **85.3%**.
* **Key Findings:** Chest pain type (`cp`) and maximum heart rate (`thalch`) were the strongest predictors of heart disease in this dataset.

## Project 2: Remote Work & Mental Health
This project was an experiment in predicting employee stress levels based on work habits and environment. This was a much tougher dataset to crack.

* **The Challenge:** The model stayed around **36.3% accuracy** (just above a random 33% guess for 3 classes). 
* **The Lesson:** Even with hyperparameter tuning, the high "noise" in the survey data (Industry, Age, etc.) didn't provide a strong mathematical signal. This was a great case study in why data quality matters more than the model itself.
* **Feature Importance:** Despite the low accuracy, "Social Isolation" and "Work-Life Balance" were the only features that showed any real correlation with stress.

## Tech Stack
* **Modeling:** Scikit-Learn (Pipelines, ColumnTransformer, RandomForest).
* **EDA:** Pandas, YData-Profiling, and Seaborn for visualizing distributions.
* **Visualization:** Plotly Express for density heatmaps to see where stress levels overlapped.

## Repository Structure
* `/notebooks`: Cleaned-up Jupyter notebooks for both models.
* `/data`: Raw CSV files.
* `/reports`: Automated EDA profiles for a deep dive into data health.