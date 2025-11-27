# Income Classification Project

## Project Overview
This project predicts whether an individual earns **more than $50K per year** based on demographic, educational, occupational and work-related features.  
The dataset contains income evaluation records from multiple countries and includes attributes such as age, marital status, workclass, education, hours per week, occupation, gender and more.

The goal is to apply data preprocessing, exploratory data analysis, feature engineering and machine learning modeling to classify an individual’s income group.

---

## Problem Statement
Given demographic and employment-related features, predict whether a person’s annual income is **>50K or ≤50K**.  
This helps in understanding income patterns and identifying socio-economic factors linked with high earning potential.

---

## Project Objectives
- Analyze demographic & occupational patterns influencing income levels  
- Clean, preprocess and transform the dataset for modeling  
- Build and compare multiple machine learning models  
- Identify the best-performing model for income prediction  
- Generate insights useful for socio-economic analysis  

---

## Data Preprocessing
Key preprocessing steps include:

- Removed **24 duplicate records** for cleaner data  
- Cleaned column names by removing trailing spaces  
- Dropped **Unnamed: 15** due to **99% null values**  
- Replaced '?' with NaN and imputed missing values in:
  - professionclass, occupation, country (using **mode**)  
- Grouped rare categories (<1%) into an **“Others”** category  
- Treated outliers using:
  - **Log transformation**  
  - **Winsorization**  
- Created two datasets:
  - **Linear models:** scaled + one-hot encoded  
  - **Tree-based models:** label encoded  
- Applied **SMOTE** after train-test split to balance income classes  

---

## Exploratory Data Analysis — Key Insights

### Income Distribution
- Majority of individuals earn **≤50K** (class imbalance)

### Age Influence
- People aged **30–50 years** show the highest likelihood of earning >50K

### Marital Status
- **Married-civ-spouse** group: ~45% earn >50K  
- Strong indicator of earning potential

### Education
- **Doctorate** and **Professional School** graduates show highest income share

### Occupation
- **Exec-managerial (48%)** and **Prof-specialty (34%)** dominate high-income category

### Gender Gap
- **Males:** 30.6% earn >50K  
- **Females:** 11% earn >50K  
- Significant gender income gap

### Workclass
- Private sector employs most individuals  
- **Self-Employed-Incorporated (56%)** has highest high-income percentage

### Work Hours
- **>40 hours/week** strongly correlates with high income

### Capital Gains/Losses
- Highly skewed  
- A small group of high-income individuals show huge capital gains

### Race Distribution
- **White** and **Asian-Pac-Islander** show highest income proportions

---

## Model Development
Multiple machine learning models were trained and evaluated, including:

- Logistic Regression  
- Support Vector Machines (Linear & RBF)  
- KNN  
- Decision Tree  
- Random Forest  
- Gradient Boosting  
- AdaBoost  
- XGBoost  
- CatBoost  

After hyperparameter tuning, **XGBoost achieved the highest overall performance**, with strong Recall and ROC-AUC despite class imbalance.

---

## Model Performance Comparison


| Model               | Train Accuracy | Test Accuracy | Test Recall | Test F1 Score | ROC-AUC (Test) |
|---------------------|----------------|---------------|-------------|---------------|----------------|
| **XGBoost**         | **0.9003**     | **0.8469**    | **0.8189**  | **0.7205**    | **0.9223**     |
| Random Forest       | 0.9999         | 0.8499        | 0.7596      | 0.7091        | 0.9052         |
| Gradient Boosting   | 0.8510         | 0.8250        | 0.8489      | 0.7003        | 0.9192         |
| SVC (RBF)           | 0.8628         | 0.8195        | 0.8565      | 0.6957        | 0.9081         |
| Logistic Regression | 0.8392         | 0.8096        | 0.8272      | 0.6768        | 0.8973         |
| AdaBoost            | 0.8268         | 0.8009        | 0.8591      | 0.6752        | 0.9010         |
| SVC (Linear)        | 0.8332         | 0.8006        | 0.8412      | 0.6702        | 0.8956         |
| KNN                 | 0.9038         | 0.7887        | 0.8042      | 0.6472        | 0.8566         |
| Decision Tree       | 0.9999         | 0.8027        | 0.6990      | 0.6306        | 0.7673         |

---

## XGBoost Model Performance  
After fine-tuning, XGBoost showed the strongest and most reliable performance:

- **Accuracy:** 84%  
- **Recall:** 84% → identifies high-income individuals effectively  
- **F1 Score:** 72% → balanced performance  
- **ROC-AUC:** 0.92 → excellent class separation  

Despite class imbalance, the fine-tuned XGBoost model demonstrates consistent generalization and strong predictive power.

---

## Business Insights
- Age, education, occupation, marital status, hours worked and capital gains significantly influence income level  
- Executive and professional occupations correlate strongly with higher income  
- Longer work hours positively impact income  
- Gender and race disparities are visible and measurable  
- Education advancement dramatically increases high-income probability  

---

## Tech Stack
- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- XGBoost  
- CatBoost  
- Matplotlib  
- Seaborn  

---

## Final Output
The final deliverables include:

- Cleaned and fully preprocessed dataset  
- Exploratory visualizations revealing income-driving factors  
- Multiple machine learning models with performance comparison  
- A tuned **XGBoost classifier** delivering the best results  
- Insights explaining demographic and occupational influences on income  

---

## Conclusion
This project demonstrates how demographic, educational and employment factors influence earning potential.  
Using advanced preprocessing, balanced training (SMOTE) and model comparison, **XGBoost** emerged as the best-performing model with high predictive accuracy and reliability.
