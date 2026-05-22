# House-Price-Prediction-ML


## Project Overview
This project aims to predict residential property prices based on various features such as area, number of bedrooms, and proximity to city centers. The workflow involves cleaning a 'dirty' dataset, performing exploratory data analysis (EDA), and training machine learning models to identify the best predictor of market value.

## Dataset Summary
- **Source**: `house_prices_dirty.csv`
- **Features**: 
    - `bedrooms`, `bathrooms`, `area_sqft`: Property size indicators.
    - `age_of_house`: Years since construction.
    - `distance_to_city_center_km`: Location-based feature.
    - `nearby_schools`, `parking_spaces`: Amenity indicators.
- **Target**: `price` (USD)

## Methodology
1. **Data Cleaning**: 
    - Dropped rows with missing target values (`price`).
    - Performed **Median Imputation** on missing numerical features to maintain data volume without introducing significant bias.
2. **Outlier Removal**: Used the **Interquartile Range (IQR)** method to remove extreme values in `area_sqft` and `price`, ensuring the model generalizes well to standard properties.
3. **Modeling**: 
    - **Linear Regression**: Baseline model to capture linear relationships.
    - **Random Forest Regressor**: Ensemble model to capture non-linear interactions.
4. **Evaluation**: Models were assessed using R², MAE, MSE, and RMSE.

## Key Findings
- **Best Model**: The **Random Forest Regressor** outperformed Linear Regression, achieving a significantly higher R² score (~0.57 vs ~0.44).
- **Primary Driver**: `distance_to_city_center_km` and `nearby_schools` emerged as top features influencing house prices in this dataset.
- **Data Quality**: Cleaning was essential, as ~10% of the original data contained missing values or extreme outliers that would have skewed a simple regression.
