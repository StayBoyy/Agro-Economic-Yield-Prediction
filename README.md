                                                                        **Farmer Income Prediction for Improved Financial Access**

#_1. Project Overview_ :

This project addresses a critical challenge faced by many farmers in India: the lack of formal credit histories, which limits their access to essential financial services. By leveraging machine learning, we aim to predict farmer income with high accuracy. This predictive model can serve as a valuable tool for financial institutions to assess creditworthiness, ultimately helping to bridge the financial inclusion gap for farmers.

This repository contains the complete pipeline from data exploration to model deployment, based on the "LTF Challenge" dataset.


#_2. Problem Statement_

Farmers in India often struggle to secure loans from formal financial institutions due to insufficient credit data. This forces them to rely on high-interest, informal lenders, hindering their economic growth. The primary goal of this project is to develop a robust machine learning model that accurately predicts farmer income, using a diverse range of agricultural, socio-economic, and environmental data. The key success metric is achieving a low Mean Absolute Percentage Error (MAPE).


#_3. Dataset_

The analysis is performed on the LTF Challenge Dataset, which includes:

  TrainData: Contains 47,970 records and 105 features.

  TestData: The dataset for which predictions are to be made.

  Dictionary: Provides definitions for all the features.

  The features span several domains, including:

  Demographics: State, district, gender, marital status.

  Agricultural Data: Landholding size, crop types, agricultural performance scores.

  Socio-Economic Factors: Household infrastructure, village scores, non-agricultural income.

  Environmental & Infrastructural Data: Rainfall, temperature, proximity to markets (mandis), road density.


#_4. Project Pipeline & Methodology_

The project follows a structured, end-to-end machine learning workflow:

Exploratory Data Analysis (EDA): Investigated data type distributions, identified high-cardinality features, and analyzed the relationships between different variables.

  Data Preprocessing:
  
  Missing Value Imputation: Filled numerical nulls with the median and categorical nulls with the string "Unknown".
  
  Categorical Encoding: Applied frequency encoding for high-cardinality features and label encoding for nominal features with fewer unique values.
  
  Target Transformation: Applied a log(x+1) transformation to the highly skewed Total Income target variable to normalize its distribution, which is crucial for improving model performance.
  
  Feature Engineering: Created new, insightful features to enhance predictive power:
  
  income_per_hectare: Ratio of total income to total agricultural land.
  
  agri_income_ratio: Proportion of income derived from agriculture.
  
  agro_econ_score: A composite score combining agricultural, socio-economic, and night light index data.
  
  access_score: An infrastructure score based on proximity to markets and railways, and road density.
  
  Model Selection: Evaluated several powerful gradient boosting models, with LightGBM and XGBoost showing the best performance due to their efficiency and accuracy.
  
  Ensemble Modeling: Implemented a Stacked Regressor to combine the strengths of multiple models. LightGBM was used as the base model, with XGBoost, Random Forest, and Extra Trees serving as meta-models, and Ridge Regression as the final estimator.


#_5. Results & Key Achievements_

The final stacked ensemble model achieved outstanding results on the validation set:

**Mean Absolute Percentage Error (MAPE): 0.89%

Accuracy (within 10% error): 99.55%

R² Score: 0.9963**

These results demonstrate a highly accurate and reliable model for predicting farmer income.


#_6. Technologies Used_

Programming Language: Python

Core Libraries: Pandas, NumPy

Machine Learning: Scikit-learn, LightGBM, XGBoost

Development Environment: Jupyter Notebook / Google Colab


#_7. Future Work_

To further enhance this project, the following steps are proposed:

Integrate K-Fold Stacking: Improve model generalization and reduce the risk of overfitting.

Incorporate Temporal & Satellite Data: Use time-series data for seasonal trends and remote sensing data for richer environmental features.

Deploy as an Interactive Dashboard: Create a user-friendly web tool for stakeholders to get income predictions.

Expand to Risk & Loan Scoring: Adapt the pipeline for broader applications like credit risk assessment, crop insurance, and policy planning.
