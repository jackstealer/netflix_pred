# Push Your Code to GitHub - Step by Step

Your GitHub repository is ready at: **https://github.com/jackstealer/netflix_pred**

Follow these steps to push your code.

## Step 1: Install Git

### Download Git
1. Go to: https://git-scm.com/downloads
2. Download "Git for Windows"
3. Run the installer
4. Use default settings (just keep clicking "Next")
5. **Important**: Make sure "Git Bash" is selected during installation

### Verify Installation
After installation, **close and reopen your terminal**, then run:
```bash
git --version
```
You should see something like: `git version 2.x.x`

## Step 2: Configure Git (First Time Only)

Open a new terminal and run these commands (replace with your info):

```bash
git config --global user.name "jackstealer"
git config --global user.email "your.email@example.com"
```

## Step 3: Initialize Repository

In your project folder (`C:\Users\ATUL\Desktop\New folder`), run:

```bash
git init
```

## Step 4: Add All Files

```bash
git add .
```

This adds all your files to git staging.

## Step 5: Create First Commit

```bash
git commit -m "Initial commit: Netflix Stock Prediction Dashboard v1.0.0"
```

## Step 6: Connect to GitHub

```bash
git remote add origin https://github.com/jackstealer/netflix_pred.git
```

## Step 7: Set Main Branch

```bash
git branch -M main
```

## Step 8: Push to GitHub

```bash
git push -u origin main
```

### If Asked for Authentication:

**Option A: Personal Access Token (Recommended)**
1. Go to: https://github.com/settings/tokens
2. Click "Generate new token" → "Generate new token (classic)"
3. Give it a name: "Netflix Dashboard"
4. Select scope: Check "repo" (full control of private repositories)
5. Click "Generate token"
6. **Copy the token** (you won't see it again!)
7. When git asks for password, paste the token

**Option B: GitHub CLI**
```bash
# Install GitHub CLI from: https://cli.github.com/
gh auth login
# Follow the prompts
```

## Step 9: Verify Upload

Go to: https://github.com/jackstealer/netflix_pred

You should see all your files!

## Quick Reference - All Commands Together

```bash
# Install git first, then:
git init
git add .
git commit -m "Initial commit: Netflix Stock Prediction Dashboard v1.0.0"
git remote add origin https://github.com/jackstealer/netflix_pred.git
git branch -M main
git push -u origin main
```

## Future Updates

After making changes to your code:

```bash
git add .
git commit -m "Description of your changes"
git push
```

## Troubleshooting

### "git is not recognized"
- Git is not installed or terminal needs restart
- Install from: https://git-scm.com/downloads
- Close and reopen terminal after installation

### "Permission denied"
- Need to authenticate with GitHub
- Use Personal Access Token (see Step 8)

### "Repository not found"
- Check the URL is correct: https://github.com/jackstealer/netflix_pred.git
- Make sure you're logged into the correct GitHub account

### "Failed to push"
- Check internet connection
- Verify authentication
- Try: `git push -f origin main` (only for first push)

## What Happens Next?

Once pushed, your repository will have:
- ✅ All your code
- ✅ Professional README
- ✅ Complete documentation
- ✅ MIT License
- ✅ GitHub Actions CI/CD
- ✅ Contribution guidelines

## Add Repository Topics

After pushing, go to your GitHub repo and add these topics:
1. Click the ⚙️ gear icon next to "About"
2. Add topics:
   - `streamlit`
   - `machine-learning`
   - `stock-prediction`
   - `netflix`
   - `python`
   - `data-science`
   - `ml-pipeline`
   - `random-forest`
   - `gradient-boosting`

## Update README

Don't forget to update README.md:
- Replace `yourusername` with `jackstealer`
- Add your contact information
- Add screenshots once you take them

## Take Screenshots

1. Run your app: `streamlit run netflix_stock_dashboard.py`
2. Take screenshots of different tabs
3. Save in `screenshots/` folder
4. Push again:
   ```bash
   git add screenshots/
   git commit -m "Add application screenshots"
   git push
   ```

---

**Need Help?** Open an issue on your GitHub repository or check the documentation files!

Good luck! 🚀
