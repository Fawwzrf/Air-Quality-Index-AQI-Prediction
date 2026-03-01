# 🌍 Air Quality Index (AQI) Prediction in Indian Cities

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626)

## 📌 Project Overview
This project focuses on analyzing and predicting the Air Quality Index (AQI) of various cities in India from 2015 to 2020. The primary goal is to build a robust Machine Learning regression model capable of forecasting daily AQI based on the concentrations of major pollutants (PM2.5, PM10, CO, NO2, etc.) and temporal features.

## 🛠️ Key Workflows & Methodology

1. **Exploratory Data Analysis (EDA)**
   * Identified highly right-skewed distributions in most pollutant variables.
   * Detected and analyzed extreme pollution events (outliers) while retaining them for model robustness.
   * Analyzed the linear and non-linear correlations between distinct pollutants and the overall AQI.

2. **Data Preprocessing & Feature Engineering**
   * **Missing Value Imputation:** Utilized a hybrid approach for time-series data: **Linear Interpolation** for short gaps and **Median Imputation** for larger gaps to avoid bias from outliers.
   * **Skewness Handling:** Applied **Logarithmic Transformation (log1p)** to normalize right-skewed numerical features (e.g., NO2, PM2.5).
   * **Categorical Encoding:** Implemented **Target Encoding** for the `City` variable (26 categories) to capture spatial pollution trends without exploding the dataset's dimensionality.
   * **Temporal Features:** Extracted `Month` and `Day` to capture seasonal pollution patterns.

3. **Modeling & Evaluation**
   * Built a baseline **Linear Regression** model for initial benchmarking ($R^2 \approx 0.73$).
   * Developed and tuned a **Random Forest Regressor** to capture complex, non-linear relationships in the environmental data.

## 📊 Results & Insights

* **Outstanding Performance:** The Random Forest model achieved an **$R^2$ Score of 0.91** and a **Mean Absolute Error (MAE) of 20.87**, significantly outperforming the baseline model.
* **Feature Importance:** `PM2.5` and `CO` were identified as the most dominant drivers of the AQI.
* **Policy Implication:** Urban planning and emission control policies should strictly prioritize reducing particulate matter (PM2.5) and Carbon Monoxide to achieve the most rapid improvement in public health.

## 📂 Repository Structure
* `AQI_Prediction_Analysis.ipynb`: The main Jupyter Notebook containing the end-to-end code, from data loading and EDA to model training and evaluation.

## 🚀 How to Run
1. Clone this repository:
   ```bash
   git clone [https://github.com/Fawwzrf/India-Air-Quality-Prediction.git](https://github.com/Fawwzrf/India-Air-Quality-Prediction.git)
