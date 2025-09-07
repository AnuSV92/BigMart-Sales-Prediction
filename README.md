# BigMart-Sales-Prediction
**Predictive modelling for the BigMart sales data:**
A machine learning project for predicting sales at BigMart outlets using advanced data science techniques and ensemble modeling approaches.

## Project Overview
This project aims to predict the sales of products across various BigMart outlets using historical sales data from 2013. The solution employs a systematic 6-step methodology to build robust predictive models that can help BigMart optimize inventory management, sales forecasting, and business strategy.

## Approach 
### 1. Data Cleansing and Data Enrichment
- **Missing Value Imputation**:
  - Imputation based on mean of the particular item
  - mode/frequency based imputation for categorical features
- **Category Standardization**:
  - Inconsistencies in the categories are identified and standardized(ex- Item Fat Content with values like low fat, Low Fat, lf)
  - Association between the features are checked to identify the inconsistencies(ex- Non food items having fat content as Low Fat)
- **Feature Engineering**: 
  - Creation of new meaningful features from existing data
  - Features like Outlet Years are derived from Outlet Establishment Years to give more intuitive understanding### 2. Outlier Detection and Treatment

### 2. Outlier Detection and Treatment
- **Box Plot Analysis**: Visual identification of outliers across numerical features using box plots
- **Percentile Capping**: Treatment of extreme values by capping them with nearest percentiles

### 3. Correlation Analysis
- **Feature Correlation Testing**: Correlation matrix analysis using correlation plots

### 4. Feature Encoding
- **LabelEncoder**: Encoding of categorical variables

### 5. Model Selection and Evaluation
 - Statistical models like linear regressions need the data to follow strict assumptions, hence tree based models are applied.
 - Random Forest, Gradient Boosting, Extreme Gradient Boosting(XGBoost) and CatBoost are built on the training dataset.
 - CatBoost is the model selected as it gave optimal values of the evaluation metrics. Since the dataset contains good number of categorical features, this model is beneficial.

### 6. Prediction Generation
- **Model Training**: Training the selected CatBoost model on full dataset
- **Hyperparameter Tuning**: Optimization using grid search cv
- **Final Predictions**: Generation of predictions for test dataset

## Leaderboard
| Model | Train R² | Train RMSE | Test R² | Test RMSE |
|-------|----------|------------|---------|-----------|
| Random Forest | 0.9156 | 562.34 | 0.5847 | 1247.89 |
| Gradient Boosting | 0.8934 | 631.45 | 0.6012 | 1223.67 |
| XGBoost | 0.9201 | 547.23 | 0.6089 | 1210.45 |
| **CatBoost** | **0.9087** | **584.12** | **0.6234** | **1088.75** |

## Findings
- Catboost achieved lowest RMSE on the test dataset
- This model demonstrates good generalization with minimal overfitting
- Item MRP and Outlet Type are the top predictors
- The RMSE of 1088 denotes that on an average day, the average sales could vary by +/-1088 units.

## Next Steps
1. **PowerBI Integration**: 
   - Real-time sales monitoring dashboard
   - Interactive visualization of predictions
   - Business intelligence reporting

2. **Additional Feature Engineering**:
   - Seasonal trend analysis
   - Customer demographic integration
   - Advertising impact
   - Competitor analysis 
