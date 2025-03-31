# Weather Forecasting Model - Regression and Clustering

## Data Overview
The dataset used in this project includes real-time, historical, and forecasted weather data for 17 Canadian cities. The dataset was last updated at **11:23 PM on March 30, 2025**. It contains data for various weather attributes, such as temperature, humidity, wind speed, and pressure, which are key in understanding weather patterns and forecasting future weather conditions.

### YData Profiling Report
To gain a better understanding of the dataset, we used **YData Profiling** to generate an exploratory data analysis (EDA) report. You can view the full **EDA Report** here: [Exploratory Data Analysis Report - Laptop Dataset](https://sandeepmondkar14.github.io/pages/combined_weather_report.html).

## Model Choice: Extra Trees Regressor
For the regression task, we experimented with multiple models using **PyCaret**, which is a low-code machine learning library. After comparing various models, the **Extra Trees Regressor** was selected as the best performing model. 

**Why Extra Trees?**
- **Performance:** Extra Trees Regressor achieved the best metrics in terms of error (low MAE, MSE, and RMSE values) and R² score (near perfect at 0.9935).
- **Efficiency:** Extra Trees is known for handling large datasets efficiently and does not overfit, making it an excellent choice for real-world data like weather forecasting.
- **Stability:** It tends to be more stable and robust against overfitting than other models such as Decision Trees or Random Forest, which is why it was selected.

## Model Results
The selected **Extra Trees Regressor** model provided the following evaluation metrics:
- **Mean Absolute Error (MAE):** 0.2706
- **Mean Squared Error (MSE):** 0.2532
- **Root Mean Squared Error (RMSE):** 0.4847
- **R² Score:** 0.9935
- **Root Mean Squared Logarithmic Error (RMSLE):** 0.1102
- **Mean Absolute Percentage Error (MAPE):** 0.2206

These results indicate that the model performs exceptionally well, with a very low error rate and almost perfect predictive accuracy.

### Key Visualizations:
- **Residuals Plot:** Shows minimal error distribution, confirming the model’s effectiveness.
- **Prediction Error Plot:** Displays a high alignment with the identity line, highlighting the model's strong predictive power.
- **Feature Importance Plot:** Identifies key weather attributes influencing the predictions, such as temperature, humidity, and wind speed.
- **Learning Curve & Validation Curve:** Demonstrates that the model performs well on unseen data and doesn’t overfit.

## Instructions to Run the Notebooks:

1. **Download the CSV Files**:
    - You need to download the following CSV files to run the notebooks successfully:
        - `weather_data.csv` (Real-time weather data)
        - `historical_hourly_data.csv` (Historical hourly weather data)
        - `24_hour_forecast.csv` (24-hour weather forecast data)
        - `14_day_forecast.csv` (14-day weather forecast data)

2. **File Path Changes in Jupyter Notebook**:
    After downloading the CSV files, make sure to update the file paths in the Jupyter notebooks (located in the "Weather Regression" and "Weather Forecasting Model" files). Here’s how to adjust the paths in the notebook:

    In the cells where the CSV files are loaded, change the paths to where the downloaded files are located. For example:

    ```python
    real_time_df = pd.read_csv('<path-to-your-directory>/weather_data.csv', encoding='latin1')
    historical_df = pd.read_csv('<path-to-your-directory>/historical_hourly_data.csv', encoding='latin1')
    forecast_24h_df = pd.read_csv('<path-to-your-directory>/24_hour_forecast.csv', encoding='latin1')
    forecast_14d_df = pd.read_csv('<path-to-your-directory>/14_day_forecast.csv', encoding='latin1')
    ```

    Replace `<path-to-your-directory>` with the actual directory path where the files are located.

## Conclusion
In this project, we successfully built a weather forecasting model using the **Extra Trees Regressor**. By preprocessing and merging multiple weather datasets, we were able to train a robust model that predicts temperature with high accuracy. The visualizations and evaluation metrics confirm that the model is both stable and effective.

With these results, we can now confidently predict future weather conditions for Canadian cities, making the model valuable for various applications, including forecasting, city planning, and resource management.

### Author: Sandeep Mondkar
