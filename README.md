# Anomaly Detection in Stock Prices

## Project Overview
This project focuses on detecting anomalies in stock prices using machine learning techniques. The primary goal is to identify unusual patterns or outliers in stock price data that may indicate significant market events or errors in data collection. The project utilizes the Isolation Forest algorithm, a popular method for anomaly detection, to analyze historical stock price data and predict anomalies in new data.

## Table of Contents
1. [Introduction](#introduction)
2. [Data Preprocessing](#data-preprocessing)
3. [Feature Engineering](#feature-engineering)
4. [Anomaly Detection Model](#anomaly-detection-model)
5. [Visualization](#visualization)
7. [Conclusion](#conclusion)

## Introduction
Anomaly detection is a crucial task in financial markets, where identifying unusual patterns can help in risk management and decision-making. This project uses historical stock price data to train an anomaly detection model and applies it to new data to identify potential anomalies.

## Data Preprocessing
Data preprocessing is a critical step in preparing the dataset for analysis. The following steps are performed:

- **Date Conversion**: The 'date' column is converted to a datetime format to facilitate time-based operations.
- **Sorting**: The data is sorted by date to maintain chronological order.
- **Handling Missing Values**: Missing values are forward-filled and replaced with zeros where necessary to ensure a complete dataset.

## Feature Engineering
Feature engineering involves creating new features from the existing data to improve the model's performance. The following features are engineered:

- **Price Range**: Calculated as the difference between the high and low prices.
- **Price Change**: The difference between the closing and opening prices.
- **Price Change Percentage**: The percentage change between the closing and opening prices.
- **Volume Change Percentage**: The percentage change in trading volume.
- **Moving Averages**: 5-day and 20-day moving averages of the closing price.
- **Volatility**: 20-day rolling standard deviation of the closing price.
- **Relative Strength Index (RSI)**: A momentum indicator that measures the magnitude of recent price changes.

These features help capture the underlying patterns in the stock price data, which are essential for detecting anomalies.

## Anomaly Detection Model
The Isolation Forest algorithm is used for anomaly detection. It is an unsupervised learning algorithm that isolates anomalies by randomly selecting a feature and then randomly selecting a split value between the maximum and minimum values of the selected feature. The key parameters include:

- **Contamination**: The proportion of outliers in the data.
- **Random State**: Ensures reproducibility of results.
- **n_jobs**: Utilizes multiple processors for faster computation.

The model is trained on the preprocessed and scaled features to learn the normal patterns in the data.

## Visualization
Visualization is a powerful tool for interpreting the results and understanding the anomalies detected by the model. The project employs several visualization techniques:

- **Line Plots**: These plots display stock prices over time, providing a clear view of the price trends and fluctuations. The seaborn library is used to create aesthetically pleasing line plots that show the 'close' price of stocks over time.
- **Anomaly Markers**: Anomalies detected by the model are highlighted on the line plots using scatter plots. These markers are plotted in red to distinguish them from normal data points. This visual distinction helps in quickly identifying periods of unusual activity.
- **Z-Score Filtering**: Before plotting, extreme outliers are removed using the z-score method. This ensures that the visualizations are not skewed by extreme values, providing a more accurate representation of the data.
- **Yearly Breakdown**: The data is visualized on a yearly basis from 2004 to 2024, allowing for a detailed examination of anomalies within specific time frames. This approach helps in understanding the context of anomalies and their potential impact on the market during different periods.

These visualizations help in understanding the context of anomalies and their potential impact, making it easier to interpret the results and draw meaningful conclusions.



## Conclusion
This project demonstrates the application of machine learning techniques for anomaly detection in stock prices. By leveraging feature engineering and the Isolation Forest algorithm, it provides a robust framework for identifying unusual patterns in financial data. The visualization techniques employed offer valuable insights into the nature and timing of detected anomalies.

