# ML-Course-Project
Beijing Air Quality Index (AQI) Prediction Using ML Algorithms

## Project Overview
This project aims to predict the Air Quality Index (AQI) in Beijing using historical environmental and pollutant data. AQI is a critical measure of air pollution levels, and accurate predictions can help mitigate health risks associated with poor air quality. The project compares the performance of two machine learning models: Random Forest Regressor and Ridge Regression.

## Dataset
The dataset is sourced from the [UCI Machine Learning Repository (Beijing PM2.5 dataset)](https://archive.ics.uci.edu/ml/datasets/Beijing+PM2.5+Data). It includes hourly measurements of pollutants (e.g., PM2.5) and meteorological conditions (e.g., temperature, humidity) from 2010 to 2014. The data was aggregated into daily values for this project.

### Features:
- **Pollutants:** PM2.5 concentration (µg/m³)
- **Meteorological Data:** Dew point (°C), temperature (°C), humidity (%), wind speed (m/s), pressure (hPa)

### Target Variable:
- **AQI (Air Quality Index):** A continuous numeric value representing pollution severity.

## Methodology
### Data Preprocessing
1. **Handling Missing Data:** Rows with missing values were removed.
2. **Normalization:** Min-Max scaling was applied to standardize feature ranges (0 to 1).

### Feature Selection
All six features were retained due to their known impact on air quality:
- PM2.5, dew point, temperature, humidity, wind speed, and pressure.

### Models Implemented
1. **Random Forest Regressor**
   - **Motivation:** Captures complex, nonlinear relationships.
   - **Loss Function:** Mean Squared Error (MSE).
2. **Ridge Regression**
   - **Motivation:** Linear model with L2 regularization to prevent overfitting.
   - **Loss Function:** Mean Squared Error (MSE).

### Model Validation
- **Data Split:** 75% training, 10% validation, 15% test.
- **Evaluation Metric:** MSE on training, validation, and test sets.

## Results
| Model                | Training MSE | Validation MSE | Test MSE |
|----------------------|--------------|-----------------|----------|
| Random Forest        | 0.0469       | 1.1528          | 0.6670   |
| Ridge Regression     | 0.1512       | 0.1669          | 0.1522   |

**Conclusion:** Ridge Regression outperformed Random Forest, achieving lower validation and test errors, indicating better generalization.

## Limitations
1. **Model Complexity:** Ridge Regression's linearity may limit capturing nonlinear patterns.
2. **Feature Set:** Limited to six features; additional data (e.g., traffic, industrial activity) could improve accuracy.
3. **Temporal Scope:** Data spans 2010–2014; newer data might reflect recent trends.

## Future Improvements
1. **Feature Engineering:** Explore interactions or transformations of existing features.
2. **Advanced Models:** Test Gradient Boosting or neural networks.
3. **Time-Series Analysis:** Incorporate temporal dependencies for long-term forecasting.
