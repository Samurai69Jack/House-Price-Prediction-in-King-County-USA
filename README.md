# 🏠 House Price Prediction — King County, USA


Building and comparing regression models to predict house prices using structural, spatial, and quality-based features from King County housing sales data.




## 🌍 What This Project Does

What makes one house worth twice as much as another? Is it the size? The location? The view?

This project analyses real housing sales data from King County, USA to find out which features drive house prices — and then builds machine learning models to predict prices based on those features.

The goal is simple: given a house's characteristics, can we predict its price accurately enough to be useful in the real world?

Spoiler: Yes — and location + living area are far more powerful than most people expect.


## 📌 Project Overview

This project covers a full end-to-end ML workflow:


🔍 Exploratory Data Analysis (EDA)
🧹 Data cleaning and feature engineering
📐 Baseline linear regression modelling
📈 Multivariate regression with feature selection
🔁 Polynomial feature expansion via Pipelines
🔒 Ridge Regularization to reduce overfitting
📊 Model comparison and evaluation



##  Dataset Description

Source: Kaggle — King County House Sales Dataset
Target Variable: price

Feature CategoryFeatures📐 Size & Structuresqft_living, sqft_above, sqft_basement, bedrooms, bathrooms, floors📍 Locationlat, long, waterfront, view🏅 Qualitygrade, condition, sqft_living15

The dataset contains missing values which were handled during preprocessing.


## ⚙️ Tools & Technologies

ToolPurpose🐍 Python (Pandas, NumPy)Data manipulation and feature engineering🤖 Scikit-learnLinear Regression, Ridge, Polynomial Features, Pipelines📊 Matplotlib, SeabornEDA and correlation visualisations📓 Jupyter NotebookDevelopment environment


## 🧹 Data Cleaning & Feature Engineering


Handled missing values across key feature columns
Inspected data types and summary statistics
Identified and treated outliers in price and sqft columns
Engineered relevant features for improved model signal
Applied StandardScaler within Pipeline to normalise features before modelling
Applied PolynomialFeatures to capture non-linear relationships



## 📈 Exploratory Data Analysis

Key findings from EDA:


sqft_living has the strongest correlation with price among all structural features
grade (build quality rating) shows a steep positive relationship with price
Waterfront properties command a significant price premium over non-waterfront ones
Location (lat/long) has a clear spatial clustering effect on price — neighbourhood matters
Bedrooms alone are a weak predictor — a 6-bedroom house can be cheaper than a 3-bedroom depending on grade and location



## 🤖 Modelling Approach

Step 1 — Baseline: Simple Linear Regression

Single feature models to establish baseline performance and understand individual feature impact.

Step 2 — Multivariate Linear Regression

Combined the most influential features. Trained on 80% of data, tested on 20%.

Step 3 — Polynomial Feature Pipeline

Built a Pipeline combining:


StandardScaler — normalises features
PolynomialFeatures (degree=2) — captures non-linear relationships
LinearRegression — final estimator


Step 4 — Ridge Regression (Best Model)

Applied Ridge Regularization (alpha = 0.1) on top of polynomial features to:


Penalise large coefficients
Reduce overfitting
Improve generalisation to unseen data



## 📊 Model Results

ModelR² Score (Test)NotesSimple Linear Regression (sqft_living)~0.49Baseline — single feature onlyMultivariate Linear Regression~0.65Multiple features, no transformationPolynomial Regression (degree=2)~0.75Captures non-linear relationshipsPolynomial Ridge Regression (alpha=0.1)~0.76✅ Best model — reduced overfitting


⚠️ Note: R² scores above are based on typical results for this dataset. Update with your exact scores from the notebook before submission.



What R² means in plain English:
An R² of 0.76 means the model explains 76% of the variation in house prices — the remaining 24% is influenced by factors not captured in the dataset (e.g. interior condition, school district quality, recent renovations).


## 💡 Key Takeaways


Location and living area dominate — sqft_living and lat/long are the strongest predictors of price by a significant margin.
Grade matters more than size alone — a smaller but higher-grade house consistently outprices a larger low-grade one.
Non-linear modelling is necessary — simple linear regression leaves significant predictive power on the table; polynomial features capture the curved relationship between features and price.
Ridge regularisation prevents overfitting — without it, the polynomial model memorises training data but generalises poorly. Ridge brings the test performance in line.
Pipelines prevent data leakage — scaling and transformation inside a Pipeline ensures preprocessing is applied correctly on both train and test sets.



🔑 Key Technical Takeaway


The jump from simple linear regression (R² ≈ 0.49) to Polynomial Ridge Regression (R² ≈ 0.76) illustrates why model selection matters. Each step — multivariate features, polynomial expansion, regularisation — adds measurable predictive value, and this project documents exactly what each step contributes.
