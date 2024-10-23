# CatBoost VS LightGBM VS XGBoost

This repository provides an overview and comparison of three popular boosting algorithms used for regression and classification tasks in machine learning: **CatBoost**, **LightGBM**, and **XGBoost**. Each of these models has unique characteristics, especially in how they structure decision trees, handle categorical data, sample data, and their historical development.

## 1. Decision Tree Structure

All three models utilize decision trees as the foundational building blocks, leveraging the principle of boosting, which combines multiple models together.

- **CatBoost (Categorical Boosting)**: 
  - The decision trees are symmetric, meaning that both nodes at the same level use the same splitting conditions, leading to uniform nodes in the subsequent levels.

- **LightGBM (Light Gradient Boosting Machine)**: 
  - The decision trees grow leaf-wise, where only one leaf grows with each iteration, enhancing the efficiency of the model.

- **XGBoost (eXtreme Gradient Boosting)**: 
  - The decision trees grow in a depth-wise manner, where each leaf breaks based on different conditions.

<img width="850" alt="Difference in Decision Trees" src="https://github.com/user-attachments/assets/7ec6e325-c225-4a65-af89-eb075ee8e518">


## 2. Handling of Categorical Columns

Different methods are used to handle categorical data in each model:

- **CatBoost**: 
  - Uses ordered encoding to manage categorical features effectively.

- **LightGBM**: 
  - Employs a bin-based or bucket-based approach for categorical variables.

- **XGBoost**: 
  - Does not have a specific method for categorical data; it requires preprocessing to clean and transform categorical features using methods like label encoding, ordinal encoding, or one-hot encoding.

## 3. Data Sampling Techniques

Each algorithm employs different strategies for selecting data samples after multiple trees are created:

- **CatBoost**: 
  - Utilizes Minimum Variance Sampling (MVS) or uniform sampling.

- **LightGBM**: 
  - Implements Gradient One-Side Sampling (GOSS) to prioritize significant data points.

- **XGBoost**: 
  - Uses Bootstrap sampling, similar to k-fold cross-validation.

## 4. Historical Context

The popularity and community support for these algorithms can often be linked to their age:

- **CatBoost**: Developed by Yandex in 2017.
- **LightGBM**: Created by Microsoft in 2016.
- **XGBoost**: An open-source project started in 2014, making it the oldest and most widely used.

## 5. Installation

To install the required libraries for each boosting algorithm, use the following commands:

```bash
# Install CatBoost
pip install catboost

# Install LightGBM
pip install lightgbm

# Install XGBoost
pip install xgboost
```

## 6. Performance Overview
- **CatBoost**:
Generally the slowest and least accurate of the three.

- **LightGBM**:
Known for being fast and accurate, with automatic handling of categorical columns.

- **XGBoost**: 
The fastest and most accurate model, though it requires manual handling of categorical data using various encoding methods.

| Model     | R-squared  | Execution Time (seconds) |
|-----------|------------|---------------------------|
| CatBoost  | 0.888      | 14.251                    |
| LightGBM  | 0.977      | 0.181                     |
| XGBoost   | 0.979      | 0.113                     |

*table of model performance metrics*
