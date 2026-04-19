# GitHub Repository Setup Guide

Follow these steps to create and push your Netflix Stock Dashboard to GitHub.

## Prerequisites

1. **Install Git** (if not already installed):
   - Download from: https://git-scm.com/downloads
   - Follow the installation wizard
   - Verify installation: Open a new terminal and run `git --version`

2. **Create a GitHub Account**:
   - Go to https://github.com
   - Sign up for a free account if you don't have one

## Step-by-Step Setup

### 1. Initialize Git Repository

Open a terminal in your project directory and run:

```bash
git init
```

### 2. Add All Files

```bash
git add .
```

### 3. Create Initial Commit

```bash
git commit -m "Initial commit: Netflix Stock Prediction Dashboard"
```

### 4. Create GitHub Repository

1. Go to https://github.com/new
2. Repository name: `netflix-stock-dashboard`
3. Description: "Interactive ML pipeline dashboard for Netflix stock prediction"
4. Choose Public or Private
5. **DO NOT** initialize with README, .gitignore, or license (we already have these)
6. Click "Create repository"

### 5. Link Local Repository to GitHub

Replace `yourusername` with your actual GitHub username:

```bash
git remote add origin https://github.com/yourusername/netflix-stock-dashboard.git
```

### 6. Push to GitHub

```bash
git branch -M main
git push -u origin main
```

### 7. Verify

Visit your repository at:
```
https://github.com/yourusername/netflix-stock-dashboard
```

## Alternative: Using GitHub Desktop

If you prefer a GUI:

1. Download GitHub Desktop: https://desktop.github.com/
2. Install and sign in to your GitHub account
3. Click "Add" → "Add Existing Repository"
4. Select your project folder
5. Click "Publish repository"
6. Choose repository name and visibility
7. Click "Publish Repository"

## Future Updates

After making changes to your code:

```bash
git add .
git commit -m "Description of your changes"
git push
```

## Common Git Commands

- `git status` - Check current status
- `git log` - View commit history
- `git branch` - List branches
- `git checkout -b feature-name` - Create new branch
- `git pull` - Pull latest changes from GitHub

## Troubleshooting

### Authentication Issues

If you encounter authentication errors:

1. **Using HTTPS**: GitHub now requires Personal Access Tokens
   - Go to GitHub Settings → Developer settings → Personal access tokens
   - Generate new token with `repo` scope
   - Use token as password when pushing

2. **Using SSH** (recommended):
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   # Add the SSH key to your GitHub account
   git remote set-url origin git@github.com:yourusername/netflix-stock-dashboard.git
   ```

### Large Files

If you have large data files:
- They're already excluded in `.gitignore`
- Consider using Git LFS for large files if needed

## Next Steps

1. Add screenshots to the `screenshots/` folder
2. Update README.md with your GitHub username
3. Add topics/tags to your GitHub repository
4. Enable GitHub Pages if you want to host documentation
5. Set up GitHub Actions for CI/CD (optional)

## Resources

- Git Documentation: https://git-scm.com/doc
- GitHub Guides: https://guides.github.com/
- GitHub Desktop: https://docs.github.com/en/desktop

---

Need help? Open an issue or check GitHub's documentation!
