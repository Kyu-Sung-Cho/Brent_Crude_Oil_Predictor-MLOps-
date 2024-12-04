# Kyu Sung's Brent Crude Oil Price Prediction

## About
A motivated data scientist with a proven track record of leveraging data to solve complex problems and driving impactful business decisions.

Extensive cross-industry experience in ESG consulting, manufacturing, healthcare, and academia, showcasing expertise in data analysis, predictive modeling, and building data-driven applications. Proficient in Python, SQL, R, Tableau, and Power BI, combined with a strong foundation in machine learning, NLP, and statistical modeling. Adept at creating ETL pipelines, crafting personalized recommendation systems, and developing dashboards for actionable insights, while excelling in stakeholder communication and cross-functional collaboration.

Keen passion for advancing data science applications in healthcare and sustainability. Successfully fine-tuned LLM models for radiology annotation, optimized forecasting models for revenue growth, and designed a green index to enhance ESG performance. Always seeking innovative solutions to bridge technical and business goals while fostering impactful collaboration.

## Education
+ M.S., Applied Data Science | The University of Chicago 
(Sep 2023 – Present)

+ M.S., Business and Technology Management | Korea Advanced Institute of Science and Technology 
(Aug 2020 – Aug 2022)

+ B.S., Security and Risk Analysis (Cybersecurity) | Pennsylvania State University 
(Aug 2014 – May 2018)

## Brent Crude Oil Price Prediction

### Overview

This project focuses on predicting Brent Crude Oil prices using macroeconomic indicators and global events. The primary goal is to build an end-to-end machine learning pipeline in Databricks, leveraging MLOps principles for data preprocessing, model training, deployment, and monitoring.

Brent Crude Oil is a significant global economic indicator, affecting energy costs, transportation, and manufacturing. Our model aims to enhance forecasting accuracy and provide insights into the factors influencing price fluctuations.


### Objectives
1. Predict Brent Crude Oil prices using historical and macroeconomic data.
2. Build scalable and reproducible MLOps pipelines in Databricks.
3. Deploy models for real-time inference and monitoring.
4. Evaluate the impact of feature changes (covariate shifts) on model performance.


### Key Features

+ **Pipeline Implementation**:
  + Data preprocessing, including feature engineering.
  + Automated model selection using **H2O AutoML**.
  + Model deployment with **MLflow**.
  + Model monitoring with **Evidently AI**.

+ **Feature Importance**:
  + Macro-economic variables like GDP, CPI, and Dollar Index.
 
+ **Experimentation**:
  + Tested impact of feature swaps (e.g., Dollar Index and Auto Sales) to simulate real-world changes.


### Methodology

**1. Data Collection and Preprocessing**

  + Source: Historical macroeconomic and Brent Crude Oil datasets.
  
  + **Exploratory Data Analysis (EDA)**:
    + Analysis of variables like GDP, CPI, Federal Funds Rate, and Vehicle Sales.
    + Insights:
      + Weak correlation between macroeconomic factors and Brent Crude Oil prices.
      + Strong negative correlation with the **Dollar Index**.

**2. Model Training**
  + AutoML Settings:
    + Runtime: 30 minutes.
    + Evaluation Metric: RMSE.
  + Selected Model:
    + Random Forest with hyperparameter optimization using Optuna.
  + Performance Metrics:
    + RMSE (Cross-validation): 2.8802.

**3. Deployment and Monitoring**
+ **Model Deployment**: MLflow for tracking and real-time inference.
+ **Monitoring**:
  + Pre- and post-feature swap monitoring using Evidently AI.
  + Metrics include Covariate Shift and Prior Probability Shift.

**4. Feature Engineering**
+ Developed custom features like:
  + Dollar Change Calculations (short, medium, and long-term trends).
  + Real GDP adjustments.
  + Interest Rate Spreads (impact on yield curves).


### Results
+ **Model Performance**:
  + Best Model: **Random Forest**.
  + **RMSE: 2.8802** (after optimization).
+ **Feature Impact**:
  + Dollar Index: Most influential feature, with significant negative correlation.
  + Car Sales: Surprisingly weak correlation with oil prices.
+ **Monitoring**:
  + Evident covariate shift after feature swaps, impacting prediction accuracy.

 
### Files

1.	_AutoML.py_

Script for running automated machine learning using H2O AutoML to identify the best-performing models for Brent Crude Oil price prediction.

2.	_Data Pipeline.py_

Contains the preprocessing pipeline for raw data, including cleaning, feature selection, and dataset preparation.

3.	_Data Preprocessing and Feature Engineering.py_

Includes detailed steps for feature extraction and transformation, such as calculating dollar change trends and real GDP adjustments.

4.	_Inference Data Preprocessing and Feature Engineering.py_

Handles preprocessing for the test data during model inference, including feature transformations and adjustments.

5.	_Model Inference and Monitoring.py_

Implements model inference and monitoring tasks, including evaluating predictions and detecting covariate shifts.

6.	_Model Training and Deployment.py_

Combines model training and deployment using MLflow, ensuring reproducibility and scalability of the pipeline.

7. _actual_vs_predicted.png_

Visual comparison of actual vs. predicted Brent Crude Oil prices before and after feature swaps, demonstrating the model’s performance.

8. _actual_vs_predicted (After Swapping Features).png_

Shows how feature swaps impacted the model’s predictions, including visualization of covariate shifts.

9. _training_data_processed.csv_

The preprocessed training dataset used for model development and optimization.

10.	_validation_data.csv_

Validation dataset used to test model performance and fine-tune hyperparameters.

11.	_validation_data_changed.csv_

Validation dataset with altered feature values (e.g., feature swaps) to simulate covariate shifts and evaluate robustness.

12.	_validation_data_processed.csv_

Fully preprocessed validation dataset used for monitoring and inference tasks.
