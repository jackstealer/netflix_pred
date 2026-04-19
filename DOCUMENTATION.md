# Netflix Stock Dashboard - Technical Documentation

## Table of Contents
1. [Architecture Overview](#architecture-overview)
2. [Data Flow](#data-flow)
3. [Components](#components)
4. [API Reference](#api-reference)
5. [Configuration](#configuration)
6. [Troubleshooting](#troubleshooting)

## Architecture Overview

The Netflix Stock Dashboard follows a modular architecture with six main components organized as tabs:

```
┌─────────────────────────────────────────────────┐
│           Streamlit Web Interface               │
├─────────────────────────────────────────────────┤
│  Tab 1: Data & EDA                              │
│  Tab 2: Cleaning & Engineering                  │
│  Tab 3: Feature Selection                       │
│  Tab 4: Model Training                          │
│  Tab 5: Performance Evaluation                  │
│  Tab 6: Predictions                             │
├─────────────────────────────────────────────────┤
│           Session State Management              │
├─────────────────────────────────────────────────┤
│  Data Sources: CSV Upload | Yahoo Finance API  │
└─────────────────────────────────────────────────┘
```

## Data Flow

### 1. Data Ingestion
- **CSV Upload**: User uploads local CSV file
- **Yahoo Finance**: Fetches historical stock data via yfinance API

### 2. Data Processing Pipeline
```
Raw Data → Missing Value Handling → Outlier Removal → 
Feature Engineering → Feature Selection → Model Training → 
Evaluation → Predictions
```

### 3. Session State Variables
- `data`: Raw data from source
- `processed_data`: Cleaned and engineered data
- `selected_features`: Features chosen for modeling
- `model`: Trained ML model
- `scaler`: StandardScaler for feature normalization
- `actual_features`: Features actually used after cleaning
- `results`: Model performance metrics and predictions

## Components

### 1. Data & EDA Tab

**Purpose**: Initial data exploration and visualization

**Features**:
- Dataset summary statistics
- Correlation heatmap
- Time series visualization
- Feature distribution plots

**Key Functions**:
```python
df.describe()  # Summary statistics
df.corr()      # Correlation matrix
px.line()      # Time series plot
px.imshow()    # Heatmap
```

### 2. Cleaning & Engineering Tab

**Purpose**: Data preprocessing and feature creation

**Missing Value Strategies**:
- Keep as is
- Delete rows
- Impute with mean
- Impute with median

**Outlier Removal**:
- IQR method: Q1 - 1.5*IQR to Q3 + 1.5*IQR

**Feature Engineering**:
- Time-based: Year, Month, Day, DayOfWeek
- Technical Indicators:
  - Moving Averages (7, 21, 50 days)
  - Volatility (21-day rolling std)
  - Price Changes (1-day and 7-day)

### 3. Feature Selection Tab

**Methods**:

1. **All Features**: Use all numeric columns
2. **Variance Threshold**: Filter by variance > threshold
3. **Correlation-based**: Filter by |correlation| > threshold
4. **Manual Selection**: User chooses features

**Implementation**:
```python
# Variance threshold
variances = df[numeric_cols].var()
selected = variances[variances > threshold].index

# Correlation-based
correlations = df[numeric_cols].corrwith(df[target]).abs()
selected = correlations[correlations > threshold].index
```

### 4. Model Training Tab

**Available Models**:

| Model | Type | Hyperparameters |
|-------|------|-----------------|
| Linear Regression | Linear | None |
| Ridge Regression | Linear | alpha |
| Lasso Regression | Linear | alpha |
| Random Forest | Ensemble | n_estimators, max_depth |
| Gradient Boosting | Ensemble | n_estimators, learning_rate |

**Training Pipeline**:
1. Train-test split (configurable ratio)
2. Feature scaling (StandardScaler)
3. Model training
4. Cross-validation (5-fold)
5. Predictions on train and test sets

### 5. Performance Tab

**Metrics**:
- **R² Score**: Coefficient of determination (0-1, higher is better)
- **RMSE**: Root Mean Squared Error (lower is better)
- **MAE**: Mean Absolute Error (lower is better)
- **CV Scores**: Cross-validation stability

**Visualizations**:
- Predicted vs Actual scatter plots
- Residual plots
- Residual distribution
- Feature importance (tree-based models)

### 6. Predictions Tab

**Single Prediction**:
- Input form with feature values
- Real-time prediction
- Confidence intervals (for ensemble models)

**Batch Prediction**:
- Upload CSV with feature columns
- Bulk predictions
- Download results

## API Reference

### Data Loading

```python
# CSV Upload
data = pd.read_csv(uploaded_file)

# Yahoo Finance
ticker = yf.Ticker("NFLX")
data = ticker.history(start=start_date, end=end_date)
```

### Feature Engineering

```python
# Moving averages
df['MA_7'] = df['Close'].rolling(window=7).mean()
df['MA_21'] = df['Close'].rolling(window=21).mean()
df['MA_50'] = df['Close'].rolling(window=50).mean()

# Volatility
df['Volatility'] = df['Close'].rolling(window=21).std()

# Price changes
df['Price_Change'] = df['Close'].pct_change()
df['Price_Change_7d'] = df['Close'].pct_change(periods=7)
```

### Model Training

```python
# Initialize model
model = RandomForestRegressor(n_estimators=100, max_depth=10)

# Scale features
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Train
model.fit(X_train_scaled, y_train)

# Predict
predictions = model.predict(X_test_scaled)

# Cross-validation
cv_scores = cross_val_score(model, X_train_scaled, y_train, cv=5)
```

### Evaluation

```python
# Metrics
r2 = r2_score(y_true, y_pred)
rmse = np.sqrt(mean_squared_error(y_true, y_pred))
mae = mean_absolute_error(y_true, y_pred)

# Feature importance
importances = model.feature_importances_
```

## Configuration

### Streamlit Configuration

Create `.streamlit/config.toml`:

```toml
[theme]
primaryColor = "#E50914"
backgroundColor = "#141414"
secondaryBackgroundColor = "#2D2D2D"
textColor = "#FFFFFF"

[server]
port = 8501
enableCORS = false
enableXsrfProtection = true
```

### Environment Variables

Create `.env` file:

```env
# Optional: Set default data source
DEFAULT_TICKER=NFLX
DEFAULT_START_DATE=2019-01-01

# Optional: Model defaults
DEFAULT_TEST_SIZE=0.2
DEFAULT_CV_FOLDS=5
```

## Troubleshooting

### Common Issues

#### 1. Import Errors

**Problem**: `ImportError: cannot import name '_lazywhere' from 'scipy._lib._util'`

**Solution**:
```bash
pip install scipy==1.11.4
```

#### 2. Array Length Mismatch

**Problem**: `ValueError: All arrays must be of the same length`

**Solution**: This is fixed in v1.0.0. Ensure you're using the latest version.

#### 3. Yahoo Finance Connection

**Problem**: Cannot fetch data from Yahoo Finance

**Solution**:
- Check internet connection
- Verify ticker symbol is correct
- Try different date range
- Yahoo Finance may have rate limits

#### 4. Memory Issues

**Problem**: Application crashes with large datasets

**Solution**:
- Reduce date range
- Use sampling for very large datasets
- Increase system memory
- Use batch processing

### Performance Optimization

1. **Large Datasets**:
   - Sample data for EDA
   - Use incremental learning for models
   - Enable caching with `@st.cache_data`

2. **Slow Visualizations**:
   - Reduce number of data points
   - Use aggregation for time series
   - Disable animations

3. **Model Training**:
   - Reduce cross-validation folds
   - Use simpler models for quick iterations
   - Limit hyperparameter search space

## Best Practices

1. **Data Quality**:
   - Always check for missing values
   - Remove outliers carefully
   - Validate feature distributions

2. **Feature Engineering**:
   - Create domain-specific features
   - Avoid data leakage
   - Check for multicollinearity

3. **Model Selection**:
   - Start with simple models
   - Use cross-validation
   - Compare multiple models
   - Check for overfitting

4. **Deployment**:
   - Use virtual environments
   - Pin dependency versions
   - Monitor model performance
   - Implement logging

## Future Enhancements

- [ ] Model persistence (pickle/joblib)
- [ ] Hyperparameter tuning (GridSearch/RandomSearch)
- [ ] More technical indicators
- [ ] Real-time data streaming
- [ ] Multi-stock comparison
- [ ] Sentiment analysis integration
- [ ] Docker deployment
- [ ] REST API endpoints
- [ ] Unit tests
- [ ] Performance monitoring

---

For more information, see [README.md](README.md) or open an issue on GitHub.
