# Ethereum Price Prediction using Machine Learning

This project focuses on predicting Ethereum prices using machine learning techniques. The dataset contains historical Ethereum price data, and we implement a robust model to forecast future prices. This repository includes the entire pipeline, from data preprocessing to model evaluation and optimization.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset Details](#dataset-details)
3. [Project Steps](#project-steps)
4. [Model Performance](#model-performance)
5. [Key Features](#key-features)
6. [How to Run](#how-to-run)
7. [Future Work](#future-work)
8. [Acknowledgments](#acknowledgments)

---

## Introduction

Predicting cryptocurrency prices is a challenging task due to high volatility and dynamic trends. In this project, we utilize supervised machine learning algorithms, including Decision Trees (DT), Support Vector Machines (SVM), and Long Short-Term Memory networks (LSTM), to create an optimized model capable of forecasting Ethereum prices.

---

## Dataset Details

- **Source:** Historical Ethereum price data.
- **Features:**
  - `date`: Timestamp of the record.
  - `open`: Opening price of Ethereum.
  - `high`: Highest price of Ethereum for the day.
  - `low`: Lowest price of Ethereum for the day.
  - `close`: Closing price of Ethereum.
  - `volume`: Trading volume.

---

## Project Steps

### 1. **Data Preprocessing**
   - Handled missing values and formatted date/time fields.
   - Converted `Timestamp` data to numerical format to address errors.
   - Normalized features for better performance.

### 2. **Exploratory Data Analysis (EDA)**
   - Visualized price trends using line plots.
   - Analyzed distributions using histograms and boxplots.
   - Checked correlations between features.

### 3. **Feature Engineering**
   - Derived new features like daily returns and moving averages.
   - Selected relevant features to reduce noise.

### 4. **Model Implementation**
   - Implemented multiple algorithms:
     - **Decision Tree (DT):** Initial implementation to understand data behavior.
     - **SVM:** Enhanced model performance with kernel optimizations.
     - **LSTM:** Focused on temporal dependencies in data.

### 5. **Model Optimization**
   - Tuned hyperparameters using Grid Search and Cross-Validation.
   - Applied early stopping to prevent overfitting.

### 6. **Evaluation Metrics**
   - **Mean Absolute Error (MAE):** 1.39
   - **Mean Squared Error (MSE):** 16.53
   - **R-squared (R²):** 0.9997

---

## Model Performance

Our final model achieved outstanding performance:
- **Optimized Model Metrics:**
  - Mean Absolute Error: `1.39`
  - Mean Squared Error: `16.53`
  - R-squared: `0.9997`

This performance indicates high accuracy in predicting Ethereum prices. However, additional testing on unseen datasets is recommended to validate generalization.

---

## Key Features

1. **Comprehensive Pipeline:** From raw data to optimized predictions.
2. **Multiple Algorithms:** Comparison of ML techniques (DT, SVM) and DL (LSTM).
3. **Hyperparameter Tuning:** Focused on improving model precision.
4. **Visualizations:** Clear EDA plots for insights.
5. **Reproducible Workflow:** Step-by-step instructions provided.

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/ethereum-price-prediction.git

2.	Install dependencies:
   ```bash
   pip install -r requirements.txt

3.	Download the dataset:
Place your dataset file (ETH_day.csv) in the project directory.

4.	Run the main script:
            python main.py

5.	View predictions:
Results will be saved in the output folder.

## Future Work
	1.	Expand Dataset: Use larger datasets with more features.
	2.	Advanced Models: Explore ensemble techniques and transformer architectures.
	3.	Real-Time Predictions: Integrate with live price feeds for dynamic updates.
	4.	Web Deployment: Build an interactive interface for user predictions.

## Acknowledgments

Special thanks to the contributors and the open-source community for datasets and tools.