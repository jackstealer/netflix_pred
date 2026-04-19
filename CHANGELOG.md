# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-04-19

### Added
- Initial release of Netflix Stock Prediction Dashboard
- Data source options: CSV upload and Yahoo Finance API
- Exploratory Data Analysis with interactive visualizations
  - Correlation heatmaps
  - Time series plots
  - Distribution analysis (box plots)
- Data cleaning features
  - Missing value handling (delete, mean imputation, median imputation)
  - Outlier removal using IQR method
- Feature engineering capabilities
  - Time-based features (Year, Month, Day, DayOfWeek)
  - Technical indicators (MA_7, MA_21, MA_50, Volatility, Price Changes)
- Feature selection methods
  - All features
  - Variance threshold
  - Correlation-based selection
  - Manual selection
- Multiple ML models
  - Linear Regression
  - Ridge Regression
  - Lasso Regression
  - Random Forest Regressor
  - Gradient Boosting Regressor
- Model evaluation metrics
  - R² Score
  - RMSE (Root Mean Squared Error)
  - MAE (Mean Absolute Error)
  - 5-fold Cross-Validation
- Performance visualizations
  - Predicted vs Actual scatter plots
  - Residual analysis
  - Feature importance (for tree-based models)
- Prediction capabilities
  - Single predictions with input form
  - Batch predictions from CSV
  - Confidence intervals for ensemble models
- Export functionality
  - Download predictions as CSV
  - Download batch predictions

### Fixed
- Feature importance array length mismatch error
- NaN handling in feature engineering
- Scipy import compatibility issues

### Technical
- Built with Streamlit 1.31.0
- Python 3.11 compatibility
- Comprehensive error handling
- Session state management for workflow persistence

## [Unreleased]

### Planned Features
- Model persistence (save/load trained models)
- More ML algorithms (XGBoost, LightGBM, Neural Networks)
- Hyperparameter tuning interface
- Real-time stock price updates
- Multiple stock comparison
- Portfolio optimization features
- Advanced technical indicators (RSI, MACD, Bollinger Bands)
- Sentiment analysis integration
- Automated model retraining
- API endpoint for predictions
- Docker containerization
- Unit tests and CI/CD pipeline

---

## Version History

- **1.0.0** - Initial public release
