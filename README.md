# Supervised Learning Midterm Project

This project explores supervised learning techniques to analyze and predict scores for synthetic team datasets using Linear Regression and its variants, including Ridge and Lasso regression models. The analysis focuses on feature engineering, regression modeling, and evaluation metrics.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Data Preprocessing](#data-preprocessing)
- [Feature Selection](#feature-selection)
- [Modeling and Results](#modeling-and-results)
- [Conclusion](#conclusion)
- [How to Run the Project](#how-to-run-the-project)
- [Acknowledgments](#acknowledgments)

## Project Overview

The objective of this project is to apply supervised learning techniques to a synthetic dataset containing both numerical and categorical features. The goal is to develop regression models that can accurately predict the performance scores of teams. The project evaluates the effectiveness of Linear, Ridge, and Lasso regression models based on metrics like RMSE and R².

## Dataset

The dataset consists of:
- **9 numerical features:** Player Score 0 to 6, Score, and Players Injured
- **2 categorical features:** Performance and Country

The dataset contained missing values, which were handled through imputation techniques.

## Data Preprocessing

Key preprocessing steps included:
- **Missing Value Imputation:** Used k-Nearest Neighbors (kNN) imputation based on Shannon distance, which outperformed Linear Regression for this dataset.
- **Feature Scaling:** Applied robust scaling to handle outliers and improve regression performance.
- **Outlier Detection:** Used IQR-score, though robust scaling already mitigated the impact of outliers.
- **Label Encoding:** Converted categorical features for use in regression models.
- **Dimensionality Expansion:** Utilized polynomial features from `sklearn` for enhanced regression modeling.

## Feature Selection

Several feature selection methods were evaluated, including ANOVA tests and model-based selection using Random Forest and Recursive Feature Elimination (RFE). Ultimately, model selection provided the best results for feature optimization.

## Modeling and Results

Multiple regression techniques were explored:
1. **Linear Regression:** 
   - Best learning rate (eta) of 0.11
   - Test RMSE: 66.79
   - Test R²: -0.03
2. **Ridge Regression:** 
   - Required large alpha values to stabilize RMSE
3. **Lasso Regression:** 
   - Best RMSE achieved at alpha = 3
   - Converged faster than Ridge with lower test RMSE (66.00)

**Model Comparisons:**
- Lasso Regression delivered the best test RMSE and faster convergence compared to Ridge Regression.
- Linear Regression showed quick convergence but higher RMSE values.

Learning curve analysis highlighted that all models faced underfitting due to high RMSE and poor R² values.

## Conclusion

The project concluded that Lasso Regression was the most suitable for this dataset due to its smaller RMSE and better convergence properties. However, the dataset's synthetic nature posed challenges, resulting in underfitting across all models. The findings suggest that better data representation and complexity are needed for accurate score prediction.

## How to Run the Project

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Hanuro/supervised-learning-midterm.git
   cd supervised-learning-midterm
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Preprocess and train models:**
   ```bash
   python preprocess_data.py
   python train_models.py
   ```

4. **Evaluate models:**
   ```bash
   python evaluate_models.py
   ```

## Acknowledgments

- SUPSI – DTI DSAI
- Teacher’s notes
- Scikit-learn Documentation
