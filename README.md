# Well Log Analysis Projects

This repository contains two projects focused on well log analysis and oil production forecasting using various data analysis and machine learning techniques.

## Project 1: Salt Creek Field Well Log Analysis

### Overview
- Dataset: 'Salt-Creek.DAT' containing 403 rows and 10 columns of well log data
- Variables: GR, log10(LLD), log10(MSFL), DT, RHOB, NPHI, PEF, POR, Kg, ln(Kg)
- Objective: Analyze well logs using statistical analysis, classification, and regression

### Methodology
1. Data Preprocessing
   - Removed outliers using the Interquartile Range (IQR) method
   - Reduced data from 403 to 286 rows

2. Exploratory Data Analysis
   - Visualized correlations using Seaborn's pairplot
   - Observed Gaussian or log-normal distributions for all variables

3. Dimensional Reduction
   - Applied Principal Component Analysis (PCA)
   - Selected 4 principal components explaining ~90% of variance

4. Classification
   - Used K-means clustering with 6 clusters
   - Visualized clusters along first two principal components

5. Regression
   - Implemented a Decision Tree Regressor to predict permeability
   - Used 70% training, 30% testing split
   - Evaluated using MAE, MSE, RMSE, and R-squared metrics

### Results
- Successfully created a model for classifying data and predicting permeability
- Suggested future improvements: hyperparameter tuning, ensemble methods, and refined clustering

## Project 2: Volve Field Time Series Analysis

### Overview
- Dataset: Volve Field time series data from 16 wells (2008-2016)
- Focus: Daily Oil Production Rate (m^3/day)
- Selected wells: P-F-12 and P-F-14 (highest non-zero production days)

### Methodology
1. Data Exploration
   - Visualized time series plots for P-F-12 and P-F-14
   - Removed "shut-in" time (zero production) for analysis

2. Persistence Forecast
   - Applied to P-F-12 well
   - Limitations: 1-step horizon, struggles with large changes

3. LSTM (Long Short-Term Memory) Model
   - Transformed time series into supervised learning problem
   - Made data stationary through differencing
   - Scaled data from -1 to 1
   - Used 300 epochs and 4 neurons for training

4. Model Validation
   - Applied LSTM model to P-F-14 well
   - Attempted to increase forecast horizon

### Results
- LSTM outperformed Persistence Forecast (RMSE: 12.7 vs 27)
- Validation on P-F-14 showed unrealistic sudden production increase
- Identified areas for improvement in increasing forecast horizon

## Future Work
- Refine LSTM model to improve long-term forecasting
- Explore other machine learning techniques for well log analysis
- Investigate methods to increase forecast horizon reliability

## Technologies Used
- Python
- Pandas
- Seaborn
- Scikit-learn
- Keras (for LSTM implementation)

---

This README provides an overview of two well log analysis projects. For detailed information, please refer to the individual project reports and code files within this repository.