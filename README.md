 Bangalore Home Price Predictio
 
A complete **Machine Learning project** to predict home prices in Bangalore.  
This project covers **data cleaning, preprocessing, outlier removal, feature engineering, model building, hyperparameter tuning, and deployment with Flask**.
## 📌 Project Overview

- Cleaned and preprocessed raw housing data (`banglore_hous_price.csv`)  
- Removed outliers and handled missing values  
- Performed **feature engineering** by creating a new column: `price_per_sqft`
- Encoded location data into one-hot vectors  
- Trained models using **Linear Regression, Lasso, and Decision Tree Regressor**  
- Tuned hyperparameters using **GridSearchCV**  
- Saved the best model using **pickle**  
- Deployed a **Flask web app** as an API for real-time predictions  

---

## 📂 Dataset

The dataset `banglore_hous_price.csv` contains the following features:

- `total_sqft` → Total area of the property  
- `bath` → Number of bathrooms  
- `bhk` → Number of bedrooms  
- `price` → Price in lakhs  
- Location columns (one-hot encoded): Example → `1st Block Jayanagar`, `Whitefield`, `Yelahanka`, etc.  

---

## ⚙️ Data Preprocessing

- Removed rows with missing/invalid values  
- Converted `total_sqft` column into numerical values  
- Handled inconsistent data  
- Removed extreme outliers using business logic  
- Added new feature: **price_per_sqft**  

---

## 🔬 Model Building

Implemented multiple algorithms with **GridSearchCV** for hyperparameter tuning:

- **Linear Regression**  
- **Lasso Regression**  
- **Decision Tree Regressor**  

📊 Example GridSearch function:

```python
def find_best_model_using_gridsearchcv(X, y):
    algos = {
        'linear_regression': {
            'model': LinearRegression(),
            'params': {
                'fit_intercept': [True, False]
            }
        },
        'lasso': {
            'model': Lasso(),
            'params': {
                'alpha': [1, 2],
                'selection': ['random', 'cyclic']
            }
        },
        'decision_tree': {
            'model': DecisionTreeRegressor(),
            'params': {
                'criterion': ['mse', 'friedman_mse'],
                'splitter': ['best', 'random']
            }
        }
    }

OUTPUT:-


