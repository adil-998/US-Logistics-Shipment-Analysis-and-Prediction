🚚 US Logistics Shipment Analysis and Prediction

This project analyzes a dataset of US logistics shipments to understand delivery trends, cost drivers, and predict transit times. Using machine learning models, the project demonstrates how logistics data can be leveraged for operational insights and predictive analytics.

📌 Project Overview

The dataset consists of 2000 shipment records with details like shipment ID, warehouse origin, destination, carrier, weight, cost, distance, and delivery status.

The main goal:

Predict Transit_Days (shipment delivery time)

Explore key factors influencing cost and delivery delays

🛠️ Workflow
🔹 1. Data Cleaning & Preprocessing

Converted Shipment_Date & Delivery_Date into datetime format.

Cleaned Shipment_ID (removed "SH" prefix, converted to integer).

Handled missing values:

Filled Delivery_Date using Shipment_Date + Transit_Days.

Filled Cost using median values.

Removed outliers in Weight_kg & Cost using IQR method.

Dropped record with Weight_kg = 0.

Encoded Status → 1 = Delivered, 0 = Delayed.

🔹 2. Exploratory Data Analysis (EDA)

Statistical Tests: Used ttest_ind → No significant difference in Weight, Cost, Distance between Delivered & Delayed shipments.

Visualizations:

📊 Bar Plots: Top 10 costly shipments, Orders by Warehouse, Destination & Carrier.

📈 Line Plots: Positive correlation between Transit_Days vs Distance_miles and Transit_Days vs Cost.

🥧 Pie Chart: Delivered vs Delayed shipment distribution.

🔥 Correlation Heatmap: Strong correlation between Distance_miles & Transit_Days.

🔹 3. Model Building & Prediction

Target Variable → Transit_Days

Feature Engineering → One-hot encoding for Carrier.

Train-Test Split applied.

Models Trained:

Linear Regression

Random Forest Regressor

🔹 4. Model Evaluation

Linear Regression:

R² = 0.539

MSE = 1.45

RMSE = 1.21

Random Forest Regressor:

Slightly better performance but similar metrics → R² = 0.539, MSE = 1.45, RMSE = 1.21

✅ Both models performed comparably, with Random Forest slightly improving predictive stability.

⚙️ Installation & Setup

Ensure you have Python 3.7+ installed. Install dependencies:

pip install pandas numpy matplotlib seaborn scikit-learn jupyter

🚀 How to Run

Clone/download the repository.

Place logistics_shipments_dataset.csv and the notebook in the same directory.

Launch Jupyter Notebook:

jupyter notebook


Open us_logistics_prediction.ipynb and run all cells.

📊 Tech Stack

Python

pandas & numpy → Data preprocessing

matplotlib & seaborn → Data visualization

scikit-learn → ML model building & evaluation

Jupyter Notebook → Interactive workflow

🔮 Future Improvements

Apply Hyperparameter Tuning (GridSearchCV/RandomizedSearchCV).

Try Gradient Boosting / XGBoost for improved accuracy.

Incorporate real-time shipment tracking data.

Deploy as a Streamlit/Flask web app for interactive predictions.
