# Coupon Recommendation System

## Project Overview

This project focuses on predicting whether a user will **accept or reject a coupon** based on user attributes, coupon details and contextual driving scenarios.  
The dataset was collected from an e-commerce survey using Mechanical Turk, containing information such as weather, time, destination, coupon type and user demographics.

The goal of the project is to:
- Perform exploratory data analysis to identify key behavioral patterns  
- Preprocess and transform data for machine learning  
- Build a classification model to predict coupon acceptance  
- Generate actionable business insights for targeted coupon campaigns  

---

## Problem Statement

The dataset includes several driving scenarios, environmental conditions, coupon characteristics and user demographics. The objective is to predict whether a user will **accept** a coupon based on these contextual and behavioral factors.

---

## Objective

- Analyze user behavior and understand what influences coupon acceptance  
- Preprocess and clean the dataset to ensure high-quality input for modeling  
- Build a predictive model (XGBoost) to classify coupon acceptance  
- Provide business recommendations to improve coupon targeting and redemption rates  

---

## Data Preprocessing

- Removed **291 duplicate records** to improve dataset reliability  
- Dropped the **Car** column due to **99% missing values**  
- Filled missing values in other categorical columns using **mode imputation**  
- Verified class balance:  
  - **56% Accepted**, **44% Not Accepted** → imbalance not severe  
- Dropped `direction_opposite` because it strongly correlated with `direction_same`  
- Grouped **Occupation** into broader professional categories to reduce high cardinality  
- Combined `toCoupon_GEQ15min` and `toCoupon_GEQ25min` into a new feature: **distance_driving**  
- Applied:  
  - **Ordinal Encoding** for ordered categorical features  
  - **One-Hot Encoding** for nominal features  
- Scaled the dataset to bring features to a similar range  
- Split data into **80% training** and **20% testing** sets  

---

## Data Analysis (Insights)

- **Destination: No Urgent Place** users accept the most coupons  
- Users traveling with **Friends** or **Partners** show significantly higher acceptance  
- **Carry-Out** and **Restaurant (<$20)** coupons have the highest acceptance rates  
- **Bar coupons** have the lowest acceptance rate  
- Longer coupon **expiration periods** lead to higher acceptance  
- Frequent visitors to **Bars, Coffee Houses, and Restaurants** are more likely to redeem similar coupons  
- Acceptance remains high even when the user is traveling in the opposite direction, as long as they have **no urgent place to go**  
- Users are most likely to accept coupons that are:  
  - inexpensive  
  - convenient  
  - valid for longer durations  
  - aligned with their typical visiting patterns  

---

## Model Development

Several machine learning models were trained and evaluated on the processed dataset to identify the best-performing algorithm.  
The models tested include:

- Logistic Regression  
- Support Vector Machines (Linear, RBF, Polynomial)  
- K-Nearest Neighbors (KNN)  
- Decision Tree  
- Random Forest  
- Gradient Boosting  
- AdaBoost  
- XGBoost  
- CatBoost  

A comprehensive comparison was performed using key evaluation metrics such as **Accuracy**, **Precision**, **Recall**, **F1 Score** and **ROC-AUC** on the test dataset.

Based on the results, **XGBoost and CatBoost emerged as the top-performing models**, with XGBoost achieving the highest balance across precision, recall, F1 score and ROC-AUC.

---

## Model Performance Comparison

| Model              | Test Accuracy | Test Precision | Test Recall | Test F1 Score | ROC AUC (Test) |
|--------------------|---------------|----------------|-------------|---------------|----------------|
| Logistic Regression | 0.6712        | 0.6950         | 0.7470      | 0.7200        | 0.7294         |
| SVC (Linear)        | 0.6712        | 0.6965         | 0.7427      | 0.7189        | 0.7287         |
| SVC (RBF)           | 0.7269        | 0.7391         | 0.7997      | 0.7682        | 0.7891         |
| SVC (Poly)          | 0.7007        | 0.7153         | 0.7826      | 0.7474        | 0.7539         |
| KNN                 | 0.6870        | 0.7120         | 0.7505      | 0.7307        | 0.7246         |
| Decision Tree       | 0.6668        | 0.7077         | 0.7006      | 0.7042        | 0.6627         |
| Random Forest       | 0.7398        | 0.7493         | 0.8118      | 0.7793        | 0.7984         |
| Gradient Boosting   | 0.7047        | 0.7197         | 0.7833      | 0.7502        | 0.7643         |
| AdaBoost            | 0.6724        | 0.6905         | 0.7634      | 0.7251        | 0.7277         |
| **XGBoost**         | **0.7434**    | **0.7535**     | **0.8125**  | **0.7819**    | **0.8198**     |
| CatBoost            | 0.7455        | 0.7500         | 0.8254      | 0.7859        | 0.8182         |

---

## XGBoost Modeling and Performance

XGBoost delivered the best performance after fine-tuning among all tested models.

**Model Metrics**
- **Recall: 82%**  
  - Strong ability to identify users who are likely to accept a coupon  
- **Precision: 75%**  
  - Predictions of acceptance are mostly accurate  
- **F1 Score: 78%**  
  - Balanced precision and recall  
- **ROC-AUC: 0.81**  
  - Good discrimination between accept vs. reject classes  
- **Accuracy: 74%**  
  - Solid overall accuracy, though recall/precision is more meaningful due to slight imbalance  

---

## Business Insights & Recommendations

- **Restaurant (<$20)** and **Carry-Out coupons** are the most influential features → campaigns should prioritize these categories  
- **Longer coupon expiration** directly boosts acceptance → users prefer flexibility  
- Users with **no urgent destination** or traveling **toward the venue** are more likely to redeem  
- Target users based on **travel context** and **companionship** (e.g., friends, partner)  
- Focus campaigns on **frequent venue visitors** (Bars, Restaurants, Coffee Houses) to maximize coupon redemption  
- Personalized coupon strategies can significantly increase overall conversion and customer engagement  

---

## Tech Stack

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- XGBoost  
- CATBoost
- Matplotlib  
- Seaborn  

---

## Final Output

The final deliverables include:

- A trained **XGBoost model** for coupon acceptance prediction  
- Cleaned and feature-engineered dataset  
- Comprehensive EDA visualizations  
- Business insights for improving coupon campaign performance  

---

## Conclusion
This project successfully demonstrates how **behavioral patterns**, **contextual factors** and **coupon attributes** influence redemption likelihood.  
The developed model and insights enable businesses to design smarter, personalized coupon strategies that significantly boost user engagement.
