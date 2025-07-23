# Fear-Greed-Index-Forecasting-Volatility-via-Google-Trends
This project forecasts short-term stock market volatility by using public sentiment data from Google Trends.

📈 Fear & Greed Index: Predicting Stock Volatility via Google Trends
This project develops a predictive model that forecasts short-term stock market volatility by quantifying public sentiment using Google Trends data. It culminates in a live, interactive dashboard that provides real-time volatility alerts.

📜 Project Description
This project tests the hypothesis that spikes in public search interest for finance-related "fear" keywords (e.g., "recession," "market crash") can predict subsequent increases in stock market volatility.

A custom "Fear Index" is engineered from Google Trends data. This index is then used as a feature to train a Gradient Boosting machine learning model that predicts whether the VIX (Volatility Index) will rise above its recent average in the upcoming week. The final output is a full-stack data application built with Streamlit that displays the model's live predictions.

🔑 Key Features
Alternative Data Integration: Fuses traditional financial data (VIX, S&P 500) with alternative sentiment data (Google Trends).

Predictive Modeling: Employs a time-series model to forecast volatility spikes 1 week in advance.

Real-Time Dashboard: A user-friendly web application built with Streamlit provides live sentiment analysis and predictive alerts.

Automated Data Pipeline: The entire process from data collection to prediction is fully automated in Python.

🛠️ Tech Stack & Tools
Programming Language: Python

Data Wrangling & Analysis: Pandas, NumPy

Machine Learning: Scikit-learn

Data Acquisition: yfinance, pytrends

Dashboard & Visualization: Streamlit, Plotly

🚀 How to Run
To run this project locally, follow these steps:

1. Clone the Repository

Bash

git clone https://github.com/YourUsername/Fear-And-Greed-Index.git
cd Fear-And-Greed-Index
2. Create a Virtual Environment & Install Dependencies
It's recommended to use a virtual environment.

Bash

# Create a virtual environment
python -m venv venv

# Activate it
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install required packages
pip install -r requirements.txt
(You will need to create a requirements.txt file containing streamlit, pandas, yfinance, pytrends, scikit-learn, plotly, and joblib).

3. Run the Streamlit App
Make sure the trained model (volatility_predictor_model.joblib) and scaler (google_trends_scaler.joblib) are in the root directory.

Bash

streamlit run app.py
Your web browser will automatically open with the dashboard running.
