# 📈 Netflix Stock Prediction Dashboard

An interactive machine learning pipeline dashboard built with Streamlit for predicting Netflix stock prices. This application provides a complete end-to-end ML workflow from data exploration to model deployment.

![Python](https://img.shields.io/badge/python-3.11-blue.svg)
![Streamlit](https://img.shields.io/badge/streamlit-1.31.0-red.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## Features

- **Data Source Flexibility**: Upload CSV files or fetch real-time data from Yahoo Finance
- **Exploratory Data Analysis**: Interactive visualizations including correlation heatmaps, time series plots, and distribution analysis
- **Data Engineering**: Handle missing values, remove outliers, and create technical indicators
- **Feature Engineering**: Create time-based features and technical indicators (Moving Averages, Volatility, Price Changes)
- **Feature Selection**: Multiple methods including variance threshold, correlation-based, and manual selection
- **Multiple ML Models**: 
  - Linear Regression
  - Ridge Regression
  - Lasso Regression
  - Random Forest
  - Gradient Boosting
- **Model Evaluation**: Comprehensive metrics with cross-validation, residual analysis, and feature importance
- **Predictions**: Make single or batch predictions with confidence intervals

## Installation

### Prerequisites

- Python 3.11 or higher
- pip package manager

### Setup

1. Clone the repository:
```bash
git clone https://github.com/jackstealer/netflix_pred.git
cd netflix_pred
```

2. Create a virtual environment (recommended):
```bash
python -m venv .venv
```

3. Activate the virtual environment:
- Windows:
  ```bash
  .venv\Scripts\activate
  ```
- macOS/Linux:
  ```bash
  source .venv/bin/activate
  ```

4. Install required packages:
```bash
pip install -r requirements.txt
```

## Usage

1. Start the Streamlit application:
```bash
streamlit run netflix_stock_dashboard.py
```

2. Open your browser and navigate to `http://localhost:8501`

3. Follow the workflow:
   - **Step 1**: Upload CSV or fetch Netflix stock data
   - **Step 2**: Explore data with interactive visualizations
   - **Step 3**: Clean data and engineer features
   - **Step 4**: Select relevant features
   - **Step 5**: Train your ML model
   - **Step 6**: Evaluate model performance
   - **Step 7**: Make predictions

## Project Structure

```
netflix-stock-dashboard/
├── netflix_stock_dashboard.py  # Main application file
├── requirements.txt            # Python dependencies
├── README.md                   # Project documentation
├── LICENSE                     # MIT License
├── .gitignore                 # Git ignore rules
└── screenshots/               # Application screenshots
```

## Technical Indicators

The dashboard automatically creates the following technical indicators:

- **Moving Averages**: 7-day, 21-day, and 50-day
- **Volatility**: 21-day rolling standard deviation
- **Price Change**: Daily and 7-day percentage changes

## Model Performance Metrics

- R² Score (Coefficient of Determination)
- RMSE (Root Mean Squared Error)
- MAE (Mean Absolute Error)
- Cross-Validation Scores (5-fold)
- Residual Analysis
- Feature Importance (for tree-based models)

## Data Format

If uploading a CSV file, ensure it contains:
- A `Date` column (optional, for time series analysis)
- A `Close` column (or specify your target variable)
- Numeric features for prediction

Example CSV format:
```csv
Date,Open,High,Low,Close,Volume
2024-01-01,450.00,455.00,448.00,452.00,1000000
2024-01-02,452.00,458.00,451.00,456.00,1100000
```

## Technologies Used

- **Streamlit**: Web application framework
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computing
- **Plotly**: Interactive visualizations
- **Scikit-learn**: Machine learning models and preprocessing
- **Seaborn & Matplotlib**: Statistical visualizations
- **yfinance**: Yahoo Finance data fetching

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Netflix stock data provided by Yahoo Finance
- Built with Streamlit's amazing framework
- Inspired by the need for accessible ML tools

## Contact

Project Link: [https://github.com/jackstealer/netflix_pred](https://github.com/jackstealer/netflix_pred)

## Screenshots

### Data Exploration
![Data Exploration](screenshots/data-exploration.png)

### Model Training
![Model Training](screenshots/model-training.png)

### Performance Metrics
![Performance](screenshots/performance.png)

---

⭐ Star this repo if you find it helpful!
