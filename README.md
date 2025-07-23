📈 Fear & Greed Index: Predicting Stock Volatility via Google Trends
A data-driven application that quantifies public sentiment to forecast short-term stock market volatility.
<!-- Replace with your live app URL -->
A preview of the live dashboard, providing real-time volatility predictions.
📜 Project Overview
This project explores the relationship between public sentiment and stock market behavior. It tests the hypothesis that spikes in public search interest for finance-related "fear" keywords (e.g., "recession," "market crash") can serve as a leading indicator for increases in market volatility.
A custom "Fear Index" is engineered by aggregating and normalizing Google Trends data for these keywords. This index is then fed into a Gradient Boosting machine learning model to predict whether the VIX (CBOE Volatility Index) will experience a significant spike in the upcoming week.
The entire pipeline—from data collection to model inference—is automated and presented in a user-friendly, interactive dashboard built with Streamlit.
🔑 Key Features
🤖 Automated Data Pipeline: Gathers and processes real-time data from two distinct APIs (yfinance for market data, pytrends for sentiment).
🧠 Predictive Modeling: Utilizes a Scikit-learn Gradient Boosting Classifier to forecast volatility spikes one week in advance.
📈 Alternative Data Integration: Fuses traditional financial metrics with novel behavioral data from Google searches.
🌐 Interactive Dashboard: A live web application built with Streamlit provides at-a-glance insights and predictive alerts.
📊 Backtested Strategy: The model's performance is validated on an out-of-sample test set, simulating real-world predictive accuracy.
🛠️ How It Works
Data Collection: The application fetches the last 5+ years of daily closing prices for the S&P 500 (SPY) and the VIX from Yahoo Finance. Simultaneously, it pulls corresponding weekly search interest data from the Google Trends API for a basket of keywords.
Preprocessing: The data is resampled to a consistent weekly frequency. The Google Trends data for each keyword is normalized on a 0-1 scale.
Feature Engineering: A composite "Fear Index" is created by averaging the normalized scores of the individual keywords. Lagged values of this index and SPY returns are created to serve as features for the model.
Model Training: A Gradient Boosting Classifier is trained on the historical data. The target variable is a binary flag indicating whether the VIX will be above its 4-week rolling average in the next week.
Inference & Visualization: In the live app, the latest data is fetched and processed through the saved model to generate a prediction for the upcoming week. The results, along with historical data, are visualized using Plotly charts.
💻 Tech Stack
Component
Technology
Language


Data Analysis


Machine Learning


Dashboard


Data Acquisition
yfinance, pytrends (Custom APIs)
Visualization



📂 Project Structure
.
├── 📄 app.py                           # Main Streamlit application script
├── 📄 requirements.txt                  # Python dependencies
├── 📦 google_trends_scaler.joblib       # Saved scaler for Google Trends data
├── 📦 volatility_predictor_model.joblib  # Saved trained Gradient Boosting model
└── 📄 README.md                        # Project documentation (this file)


🚀 Setup and Installation
To run this project on your local machine, follow these steps:
1. Clone the Repository
git clone https://github.com/YourUsername/Fear-And-Greed-Index.git
cd Fear-And-Greed-Index


(Replace YourUsername with your actual GitHub username)
2. Create and Activate a Virtual Environment
Using a virtual environment is highly recommended to manage dependencies.
# Create the environment
python -m venv venv

# Activate the environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate


3. Install Dependencies
Install all the required Python libraries from the requirements.txt file.
pip install -r requirements.txt


(Note: If you don't have a requirements.txt file, create one and add streamlit, pandas, yfinance, pytrends, scikit-learn, plotly, and joblib)
4. Run the Application
Launch the Streamlit dashboard using the following command:
streamlit run app.py


Your default web browser will open a new tab at http://localhost:8501 where the application is running.
💡 Future Improvements
Expand Keyword Basket: Incorporate more nuanced "greed" and "opportunity" keywords (e.g., "buy the dip," "all-time high") to create a more balanced index.
Advanced Modeling: Experiment with more complex time-series models like LSTMs or GRUs to potentially capture more intricate temporal patterns.
Economic Value Backtest: Implement a simple trading strategy simulation (e.g., move to cash on "High Volatility" alerts) to quantify the model's economic significance via metrics like Sharpe ratio.
