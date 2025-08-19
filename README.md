# Currency Exchange Rate Forecasting

This project explores different approaches to forecast **currency exchange rates** using both **statistical** and **machine learning** models.  

## Project Overview
- Dataset: historical time series of exchange rates  
- Goal: forecast the next-day `Close` price  

## Models Implemented
1. **Linear Regression (naïve approach)** – trained directly on `Close` (same data used in lag features).  
   - R² = 1.0 → misleading, because the model was reconstructing known values, not forecasting.  
   - Included for methodological clarity.  

2. **Linear Regression (corrected)** – target defined as `Close_target = Close.shift(-1)`.  
   - R² ≈ 0.9763  
   - Correct approach, predicting the next-day value.  

3. **SARIMA(2,1,0)(2,1,0,52)** – best statistical model tested.  
   - R² ≈ 0.05  
   - Seasonal structure captured, but much weaker predictive performance compared to ML.  

## Key Insights
- Machine Learning with lag features **outperformed** SARIMA for this dataset.  
- Careful definition of the **target variable** is essential in forecasting.  
- Statistical models remain interpretable, but less effective here.  

## Next Steps
- Extend forecasting horizon beyond 1 day.  
- Experiment with more advanced models (XGBoost, LSTM).  
- Add hyperparameter tuning and cross-validation.  

##  Installation
Install dependencies with:
```bash
pip install -r requirements.txt
