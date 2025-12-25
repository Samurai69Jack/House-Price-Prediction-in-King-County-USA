# House-Price-Prediction-in-King-County-USA
## Overview
Real estate pricing is influenced by a combination of structural, spatial, and qualitative factors. The goal of this project is to analyze housing sales data from King County, USA, and build a machine learning model to predict house prices based on property characteristics.

This project demonstrates an end-to-end data science workflow, including data exploration, feature engineering, model development, and evaluation.

## Objectives
1. Explore key factors that influence housing prices

2. Build and compare regression models to predict house prices

3. Improve model performance through feature engineering and regularization

4. Evaluate models using appropriate performance metrics

## Dataset: King County Housing
## Target Variable : Price
## Features include:
### Structural features: bedrooms, bathrooms, floors, sqft_living, sqft_above, sqft_basement
### Location features: lat, long, waterfront, view
### Quality indicators: grade, sqft_living15

The dataset contains missing values, which were handled during preprocessing.

## Exploratory Data Analysis (EDA)

Inspected data types and summary statistics

Analyzed relationships between individual features and house prices

Observed strong correlations between price and features such as:

1. Living area (sqft_living)
2. Grade of the house
3. Location-based variables

EDA guided the selection of relevant features for modeling.

# Modeling Approach

1. Baseline Models
Implemented simple linear regression using individual predictors
Established baseline performance using R² score
Identified limitations of linear assumptions with single features

2. Multivariate Linear Regression
Selected a subset of influential features
Split the data into training and testing sets
Trained a multivariate linear regression model
Evaluated generalization performance using test data

3. Feature Engineering with Pipelines
Built a Pipeline combining:
1. Standard scaling
2. Polynomial feature transformation
3. Linear regression
Enabled modeling of non-linear relationships between predictors and price

4. Regularization with Ridge Regression
Applied Ridge Regression to control model complexity
Tuned the regularization parameter (alpha = 0.1)
Combined Ridge Regression with 2nd-degree polynomial features
Reduced overfitting while maintaining strong predictive performance

📊 Model Evaluation

Used R² score as the primary evaluation metric

Compared performance across:
Simple linear regression
Multivariate regression
Polynomial regression
Polynomial Ridge regression

The Polynomial Ridge Regression model provided the best balance between bias and variance.

✅ Results & Key Takeaways
House prices are strongly influenced by both size-related and location-based features
Polynomial feature expansion captures non-linear price behavior
Ridge regularization improves model stability and generalization
Pipelines simplify preprocessing and prevent data leakage

🛠️ Tools & Technologies
Python
Pandas, NumPy
Scikit-learn
Matplotlib / Seaborn (EDA)
Jupyter Notebook

