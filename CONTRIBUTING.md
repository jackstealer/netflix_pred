# Contributing to Netflix Stock Dashboard

Thank you for considering contributing to this project! We welcome contributions from everyone.

## How to Contribute

### Reporting Bugs

If you find a bug, please create an issue with:
- A clear title and description
- Steps to reproduce the issue
- Expected vs actual behavior
- Screenshots if applicable
- Your environment details (OS, Python version, etc.)

### Suggesting Features

We love new ideas! Please create an issue with:
- A clear description of the feature
- Why it would be useful
- Any implementation ideas you have

### Pull Requests

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature-name`)
3. Make your changes
4. Test your changes thoroughly
5. Commit with clear messages (`git commit -m 'Add feature: description'`)
6. Push to your branch (`git push origin feature/your-feature-name`)
7. Open a Pull Request

### Code Style

- Follow PEP 8 guidelines for Python code
- Use meaningful variable and function names
- Add comments for complex logic
- Keep functions focused and modular

### Testing

- Test your changes with different datasets
- Ensure all existing features still work
- Test edge cases

### Documentation

- Update README.md if you add new features
- Add docstrings to new functions
- Update requirements.txt if you add dependencies

## Development Setup

1. Clone your fork:
```bash
git clone https://github.com/yourusername/netflix-stock-dashboard.git
cd netflix-stock-dashboard
```

2. Create a virtual environment:
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Run the application:
```bash
streamlit run netflix_stock_dashboard.py
```

## Questions?

Feel free to open an issue for any questions or concerns.

Thank you for contributing! 🎉
