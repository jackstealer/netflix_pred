# Quick Start Guide

Get up and running with Netflix Stock Dashboard in 5 minutes!

## 🚀 Installation (2 minutes)

### Option 1: Quick Install

```bash
# Clone the repository
git clone https://github.com/yourusername/netflix-stock-dashboard.git
cd netflix-stock-dashboard

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run netflix_stock_dashboard.py
```

### Option 2: With Virtual Environment (Recommended)

```bash
# Clone the repository
git clone https://github.com/yourusername/netflix-stock-dashboard.git
cd netflix-stock-dashboard

# Create virtual environment
python -m venv .venv

# Activate it
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run netflix_stock_dashboard.py
```

## 📊 First Prediction (3 minutes)

### Step 1: Get Data (30 seconds)

**Option A - Fetch from Yahoo Finance** (Easiest):
1. Select "Fetch from Yahoo Finance"
2. Choose date range (default: last 5 years)
3. Click "Fetch Data"

**Option B - Upload CSV**:
1. Select "Upload CSV"
2. Drag and drop your CSV file
3. Ensure it has a 'Close' column

### Step 2: Explore Data (30 seconds)

1. Go to "Data & EDA" tab
2. Check the correlation heatmap
3. View the time series plot
4. Select target variable (usually 'Close')

### Step 3: Engineer Features (30 seconds)

1. Go to "Cleaning & Engineering" tab
2. Check "Create technical indicators"
3. This adds moving averages, volatility, and price changes
4. Click through to see processed data

### Step 4: Select Features (30 seconds)

1. Go to "Feature Selection" tab
2. Choose "Correlation-based" method
3. Set threshold to 0.1
4. See which features are selected

### Step 5: Train Model (30 seconds)

1. Go to "Model Training" tab
2. Select "Random Forest" (good default choice)
3. Keep default parameters
4. Click "🚀 Start Training Pipeline"
5. Wait for training to complete

### Step 6: Check Performance (30 seconds)

1. Go to "Performance" tab
2. Check R² Score (aim for > 0.80)
3. View predicted vs actual plots
4. Check residual analysis

### Step 7: Make Predictions (30 seconds)

1. Go to "Predictions" tab
2. Adjust feature values or keep defaults
3. Click "🔮 Predict"
4. See your prediction!

## 🎯 Example Workflow

Here's a complete example using Netflix stock data:

```python
# The app does this for you, but here's what happens behind the scenes:

# 1. Fetch data
import yfinance as yf
data = yf.Ticker("NFLX").history(period="5y")

# 2. Create features
data['MA_7'] = data['Close'].rolling(7).mean()
data['MA_21'] = data['Close'].rolling(21).mean()
data['Volatility'] = data['Close'].rolling(21).std()

# 3. Train model
from sklearn.ensemble import RandomForestRegressor
model = RandomForestRegressor(n_estimators=100)
model.fit(X_train, y_train)

# 4. Predict
prediction = model.predict(X_test)
```

## 💡 Tips for Best Results

### Data Quality
- ✅ Use at least 2 years of data
- ✅ Check for missing values
- ✅ Remove extreme outliers

### Feature Engineering
- ✅ Always create technical indicators
- ✅ Include moving averages
- ✅ Add volatility measures

### Model Selection
- 🥇 **Random Forest**: Best for most cases
- 🥈 **Gradient Boosting**: Good for complex patterns
- 🥉 **Ridge Regression**: Fast and interpretable

### Feature Selection
- Start with correlation-based (threshold: 0.1)
- Remove highly correlated features (> 0.95)
- Keep 5-15 features for best results

## 🐛 Quick Troubleshooting

### App won't start
```bash
# Check Python version (need 3.11+)
python --version

# Reinstall dependencies
pip install -r requirements.txt --force-reinstall
```

### Can't fetch Yahoo Finance data
- Check internet connection
- Try a different date range
- Use CSV upload instead

### Model training fails
- Check for missing values in data
- Ensure you have enough data (> 100 rows)
- Try a simpler model (Linear Regression)

### Poor predictions (R² < 0.5)
- Add more features
- Use longer time period
- Try different models
- Check for data quality issues

## 📚 Next Steps

1. **Read the full documentation**: [DOCUMENTATION.md](DOCUMENTATION.md)
2. **Customize the app**: Edit `netflix_stock_dashboard.py`
3. **Try different stocks**: Change ticker symbol
4. **Experiment with models**: Try all 5 available models
5. **Export predictions**: Download CSV results

## 🎓 Learning Resources

- [Streamlit Documentation](https://docs.streamlit.io)
- [Scikit-learn User Guide](https://scikit-learn.org/stable/user_guide.html)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Yahoo Finance API](https://pypi.org/project/yfinance/)

## 🆘 Need Help?

- 📖 Check [DOCUMENTATION.md](DOCUMENTATION.md)
- 🐛 Report issues on GitHub
- 💬 Ask questions in Discussions
- 📧 Contact: your.email@example.com

---

**Ready to predict? Let's go! 🚀**

```bash
streamlit run netflix_stock_dashboard.py
```

Then open http://localhost:8501 in your browser!
