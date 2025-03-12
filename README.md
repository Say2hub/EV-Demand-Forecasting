Demand Forecasting of Electric Vehicles (EVs) in India
A Time Series Analysis Project
GitHub License
Python Version

Overview
This project focuses on forecasting the demand for Electric Vehicles (EVs) in India using advanced time series analysis techniques. The study analyzes trends in vehicle registrations across different fuel types, including EVs, Hybrid, CNG, Petrol, and Diesel, to uncover patterns and predict future adoption rates. By leveraging robust statistical and machine learning models, this project provides actionable insights for policymakers, market analysts, and industry stakeholders to make data-driven decisions that shape the future of sustainable transportation in India.

Table of Contents
Introduction
Objectives
Dataset Description
Methodology
Key Findings
Technologies Used
Project Structure
How to Run the Code
Future Scope
Contributors
References
License
Introduction
The automotive industry in India is undergoing a significant transformation, driven by the rapid adoption of alternative fuel vehicles, particularly Electric Vehicles (EVs). This project aims to analyze historical vehicle registration data to forecast future trends in EV adoption. By identifying underlying patterns, seasonality, and relationships between different fuel types, the project contributes to a deeper understanding of the market dynamics and supports strategic decision-making for sustainable mobility solutions.

Objectives
The primary objectives of this project are:

Data Cleaning : Preprocess the dataset to handle inconsistencies, missing values, and outliers.
Trend Identification : Detect long-term trends in vehicle registrations across various fuel types.
Seasonality Analysis : Investigate periodic fluctuations in the data caused by factors like festivals, policy changes, or new model launches.
Smoothing Techniques : Apply smoothing methods to reduce noise and highlight significant patterns.
Model Selection and Evaluation : Identify optimal parameters for statistical and machine learning models and evaluate their performance using accuracy metrics.
Forecasting : Predict future vehicle registrations to inform policy decisions and market strategies.
Dataset Description
The dataset used in this project contains historical vehicle registration data spanning several years. Key features include:

Date : Timestamp of recorded observations.
Fuel Categories : Counts for Electric Vehicles (EV), Hybrid, CNG, Petrol, Diesel, and other fuel types.
Source: Parivahan.gov.in

Methodology
1. Data Preprocessing
Removed inconsistencies, missing values, and outliers.
Transformed the data into a format suitable for time series analysis.
2. Exploratory Data Analysis (EDA)
Decomposed the time series into trend , seasonal , and residual components.
Applied smoothing techniques such as Simple Exponential Smoothing (SES), Double Exponential Smoothing (DES), and Triple Exponential Smoothing (TES).
3. Stationarity Testing
Used the Augmented Dickey-Fuller (ADF) Test to check for stationarity.
Conducted Granger Causality Tests to identify relationships between different fuel types.
4. Model Implementation
Implemented advanced time series models:
Vector AutoRegression (VAR) : Captured dynamic relationships between multiple fuel categories.
ARIMA with Exogenous Variables (ARIMAX) : Incorporated external factors influencing the data.
GARCH : Modeled volatility in the time series.
5. Forecasting and Validation
Generated forecasts for a 12-month period.
Evaluated model performance using metrics like RMSE, MAE, MAPE, and MPE.
Key Findings
Granger Causality Results :
CNG and Hybrid vehicle registrations strongly influence EV adoption.
Petrol shows moderate causality at specific lags, while Diesel has no significant impact.
Impulse Response Functions (IRF) :
A shock in CNG sales positively impacts EV sales.
Petrol sales negatively affect EV adoption in the short term.
Hybrid sales exhibit a mixed relationship, serving as a bridge to EV adoption.
Forecast Accuracy :
The VAR model outperformed ARIMAX and GARCH in capturing interdependencies between fuel types and providing accurate predictions.
Technologies Used
Programming Language : Python
Libraries :
pandas, numpy for data manipulation.
statsmodels for time series modeling.
matplotlib, seaborn for visualization.
sklearn for error metrics.
Tools : Google Colab for implementation.
Project Structure
Copy
1
2
3
4
5
6
├── data/                  # Contains raw and cleaned datasets
├── notebooks/             # Jupyter notebooks for analysis and modeling
├── scripts/               # Python scripts for preprocessing and modeling
├── visualizations/        # Saved plots and charts
├── README.md              # Project documentation
└── requirements.txt       # List of required Python libraries
How to Run the Code
Clone the Repository :
bash
Copy
1
2
git clone https://github.com/your-username/demand-forecasting-ev.git
cd demand-forecasting-ev
Install Dependencies :
bash
Copy
1
pip install -r requirements.txt
Run the Notebooks :
Open the Jupyter notebooks in the notebooks/ folder using Google Colab or your local environment.
Generate Forecasts :
Follow the instructions in the notebooks to preprocess the data, train the models, and generate forecasts.
Future Scope
Incorporate additional features such as fuel prices, GDP, and government incentives to enhance predictive power.
Explore advanced machine learning models like LSTM or Transformers for capturing non-linear relationships.
Analyze regional trends in vehicle registrations for a more granular understanding.
Simulate the impact of policy changes on EV adoption.
Extend the project to enable real-time forecasting using live data streams.
Contributors
Shobit Gupta (GitHub Profile )
Saiyyam Lodaya (GitHub Profile )
Sayantan Mukherjee (GitHub Profile )
Guided by:

Prof. Shruti Mathur
References
Dataset: Fuel Type and Vehicle Registration Trends.
Source: Parivahan.gov.in
Jason Brownlee, "Regression Metrics for Machine Learning."
Source: Machine Learning Mastery
Davide Burba, "An Overview of Time Series Forecasting Models."
Source: Towards Data Science
Statsmodels Documentation: Statistical Models for Time Series.
Source: Statsmodels
Seaborn and Matplotlib Documentation for Visualization.
Source: Matplotlib | Seaborn
License
This project is licensed under the MIT License .




