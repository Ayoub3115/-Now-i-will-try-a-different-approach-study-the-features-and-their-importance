# Wind Power Forecasting Project

This project focuses on predicting wind turbine power generation using machine learning and time series analysis techniques. The analysis includes comprehensive data preprocessing, feature engineering, and model comparison to achieve accurate forecasts.

---

## 1. Project Overview

Wind power forecasting is essential for energy grid management and renewable energy optimization. This project analyzes turbine operational data to predict **Active Power** using various machine learning approaches, with emphasis on missing data treatment and feature selection to improve model performance.

---

## 2. Dataset

The project uses operational wind turbine data from `Turbine_Data.csv`, which includes:

- **118,224 records** with **22 variables**
- Time-stamped data at 10-minute intervals from December 2017 to March 2020
- Key operational parameters such as:
  - **Active Power** (target variable)
  - Wind speed and direction
  - Temperature measurements (ambient, bearing, gearbox, generator, hub)
  - Blade pitch angles
  - Rotor RPM
  - Operational status indicators

---

## 3. Key Features

### 3.1 Data Preprocessing

- **Missing Value Treatment**:
  - **KNN imputation** for correlated variables: RotorRPM, ReactivePower, GearboxOilTemperature
  - **Forward fill** for time-dependent variables: WindSpeed
  - **Mean imputation** for temperature-related variables

- **Feature Selection**:
  - Removal of variables with **correlation > 99%**
  - Elimination of constant or irrelevant columns

---

### 3.2 Model Implementation

Three forecasting approaches were used:

1. **Random Forest Regressor**
   - Non-parametric ensemble method
   - Handles nonlinear relationships effectively
   - Feature importance analysis  
   - **Results**:  
     - MAE: 19.82  
     - RMSE: 104.19  

2. **ARIMA (AutoRegressive Integrated Moving Average)**
   - Time series-specific model
   - Stationarity testing and differencing applied

3. **Exponential Smoothing**
   - Models trend and seasonal components
   - Adaptive forecasting technique

---

## 4. Model Performance

### 4.1 Random Forest (Primary Model)
- **MAE**: 19.82 kW  
- **RMSE**: 104.19 kW  
- **R² Score**: High correlation between predictions and actual values  
- **Overfitting**: Balanced performance on both training and test sets  

### 4.2 Time Series Models
- **ARIMA**: Effectively captures temporal dependencies after differencing
- **Exponential Smoothing**: Performs well on trend and seasonal patterns
- **Comparison**: Random Forest outperforms traditional time series models for this dataset

---

## 5. Data Processing Pipeline

1. **Data Loading**: Import from `Turbine_Data.csv`
2. **Feature Engineering**:
   - Datetime conversion for temporal analysis
   - Correlation analysis and feature selection
   - Removal of constant-value columns
3. **Missing Value Treatment**:
   - Strategic imputation based on variable characteristics
   - KNN for correlated variables, forward fill for temporal series
4. **Model Training**:
   - 80/20 chronological split to preserve time order
5. **Evaluation**:
   - Performance metrics comparison (MAE, RMSE, R²)

---

## 6. Key Insights

- **Feature Importance**: Wind speed, rotor RPM, and temperature readings are key predictors
- **Temporal Patterns**: Strong time-based dependencies in power generation
- **Model Performance**: Random Forest performs robustly with proper preprocessing
- **Data Quality**: Strategic handling of missing values significantly improves accuracy
- **Stationarity**: Differencing is required for time series models like ARIMA

---

## 7. Visualizations

The project includes detailed visualizations:

- Correlation heatmaps for feature analysis
- Time series plots showing train/test split
- Prediction vs actual comparisons
- Feature distribution histograms
- Performance metric dashboards
- Scatter plots for correlation exploration

---

## 8. Technical Highlights

- **Missing Data Strategy**: 47% missing values handled using multiple imputation techniques
- **Feature Selection**: Reduced from 22 to 11 relevant variables
- **Chronological Validation**: Proper train/test split preserving temporal order
- **Performance Monitoring**: In-depth overfitting analysis conducted

---

## 9. Future Improvements

- Implement deep learning models (LSTM, GRU) for sequence modeling
- Integrate weather forecast data for improved accuracy
- Develop ensemble methods combining multiple model types
- Add real-time prediction capabilities with streaming data
- Advanced feature engineering using seasonal and meteorological patterns
- Hyperparameter tuning using Grid Search or Bayesian Optimization

---

## 10. Installation & Requirements

### Requirements:
- Python  
- pandas  
- numpy  
- scikit-learn  
- matplotlib  
- seaborn  
- statsmodels

---

## 11. Contributing

You can contribute by:

- Adding new forecasting models
- Improving preprocessing techniques
- Enhancing visualizations
- Optimizing model hyperparameters
- Adding real-time prediction features



---

## 12. Contact

For questions or collaboration opportunities, please open an issue in the repository.

---

This project demonstrates practical applications of **machine learning** in renewable energy forecasting, showcasing end-to-end data preprocessing, model experimentation, and performance evaluation.
