# Repository Structure

```
netflix-stock-dashboard/
│
├── .github/
│   └── workflows/
│       └── streamlit-app.yml          # GitHub Actions CI/CD workflow
│
├── screenshots/
│   └── README.md                      # Instructions for adding screenshots
│
├── .gitignore                         # Git ignore rules
├── CHANGELOG.md                       # Version history and changes
├── CONTRIBUTING.md                    # Contribution guidelines
├── DOCUMENTATION.md                   # Technical documentation
├── LICENSE                            # MIT License
├── QUICKSTART.md                      # Quick start guide
├── README.md                          # Main project documentation
├── REPO_STRUCTURE.md                  # This file
├── SETUP_GITHUB.md                    # GitHub setup instructions
│
├── netflix_stock_dashboard.py         # Main application file
└── requirements.txt                   # Python dependencies
```

## File Descriptions

### Core Application
- **netflix_stock_dashboard.py**: Main Streamlit application with all ML pipeline functionality

### Documentation
- **README.md**: Project overview, features, installation, and usage
- **QUICKSTART.md**: 5-minute quick start guide
- **DOCUMENTATION.md**: Comprehensive technical documentation
- **CHANGELOG.md**: Version history and release notes
- **CONTRIBUTING.md**: Guidelines for contributors
- **SETUP_GITHUB.md**: Step-by-step GitHub setup instructions
- **REPO_STRUCTURE.md**: This file - repository organization

### Configuration
- **requirements.txt**: Python package dependencies
- **.gitignore**: Files and directories to exclude from Git
- **LICENSE**: MIT License terms

### CI/CD
- **.github/workflows/streamlit-app.yml**: GitHub Actions workflow for automated testing

### Assets
- **screenshots/**: Directory for application screenshots

## Key Components in Main Application

### netflix_stock_dashboard.py Structure

```python
# Imports and Configuration
├── Library imports (streamlit, pandas, sklearn, etc.)
├── Page configuration
└── Session state initialization

# Sidebar - Data Source
├── Upload CSV option
└── Yahoo Finance fetch option

# Tab 1: Data & EDA
├── Dataset summary
├── Correlation heatmap
├── Time series visualization
└── Feature distributions

# Tab 2: Cleaning & Engineering
├── Missing value handling
├── Outlier removal
├── Time-based features
└── Technical indicators

# Tab 3: Feature Selection
├── All features
├── Variance threshold
├── Correlation-based
└── Manual selection

# Tab 4: Model Training
├── Model selection (5 algorithms)
├── Hyperparameter configuration
├── Train-test split
├── Feature scaling
└── Cross-validation

# Tab 5: Performance
├── Metrics display (R², RMSE, MAE)
├── Cross-validation results
├── Predicted vs Actual plots
├── Residual analysis
└── Feature importance

# Tab 6: Predictions
├── Single prediction form
├── Batch prediction upload
└── Results export
```

## Dependencies (requirements.txt)

```
streamlit==1.31.0      # Web framework
pandas==2.1.4          # Data manipulation
numpy==1.26.3          # Numerical computing
plotly==5.18.0         # Interactive visualizations
scikit-learn==1.4.0    # Machine learning
scipy==1.11.4          # Scientific computing
seaborn==0.13.1        # Statistical visualizations
matplotlib==3.8.2      # Plotting library
yfinance==0.2.36       # Yahoo Finance API
```

## Workflow Files

### GitHub Actions (.github/workflows/streamlit-app.yml)
- Runs on push/PR to main branch
- Tests Python syntax
- Verifies dependencies install
- Checks Streamlit app loads

## Documentation Hierarchy

```
README.md (Start here)
    ├── QUICKSTART.md (5-minute tutorial)
    ├── DOCUMENTATION.md (Technical details)
    │   ├── Architecture
    │   ├── API Reference
    │   └── Troubleshooting
    ├── CONTRIBUTING.md (For contributors)
    ├── CHANGELOG.md (Version history)
    └── SETUP_GITHUB.md (GitHub setup)
```

## Getting Started Path

1. **First Time Users**: README.md → QUICKSTART.md
2. **Developers**: README.md → DOCUMENTATION.md → CONTRIBUTING.md
3. **Contributors**: CONTRIBUTING.md → DOCUMENTATION.md
4. **GitHub Setup**: SETUP_GITHUB.md

## File Sizes (Approximate)

| File | Lines | Purpose |
|------|-------|---------|
| netflix_stock_dashboard.py | ~600 | Main application |
| README.md | ~200 | Project overview |
| DOCUMENTATION.md | ~400 | Technical docs |
| QUICKSTART.md | ~200 | Quick guide |
| requirements.txt | ~10 | Dependencies |
| CONTRIBUTING.md | ~100 | Contribution guide |
| CHANGELOG.md | ~100 | Version history |
| SETUP_GITHUB.md | ~150 | GitHub setup |

## Maintenance

### Regular Updates
- Update CHANGELOG.md for each release
- Keep requirements.txt versions current
- Add screenshots as features are added
- Update documentation for new features

### Version Control
- Main branch: Stable releases
- Feature branches: New development
- Tags: Version releases (v1.0.0, v1.1.0, etc.)

## Future Structure

Planned additions:
```
├── tests/                    # Unit tests
│   ├── test_data.py
│   ├── test_models.py
│   └── test_predictions.py
├── data/                     # Sample datasets
│   └── sample_stock_data.csv
├── models/                   # Saved models
│   └── .gitkeep
├── notebooks/                # Jupyter notebooks
│   └── analysis.ipynb
├── docker/                   # Docker configuration
│   ├── Dockerfile
│   └── docker-compose.yml
└── api/                      # REST API
    └── app.py
```

---

**Note**: This structure follows best practices for Python projects and open-source repositories.
