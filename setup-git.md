# Setup Git Repository

## 1. Initialize Git Repository
```bash
cd "c:/Users/PTNATGAMING/OneDrive/Muziek/Documenten/bookmarks-web-main"
git init
git add .
git commit -m "Initial commit - Status Monitor with GitHub Actions"
```

## 2. Connect to GitHub Repository
```bash
git remote add origin https://github.com/bookmarks-cih/bookmarks.github.io.git
git branch -M main
git push -u origin main
```

## 3. Push GitHub Actions Files
```bash
git add .github/
git commit -m "Add GitHub Actions workflows for URL scanning and Neocities deployment"
git push origin main
```

## 4. Verify Setup
- Go to https://github.com/bookmarks-cih/bookmarks.github.io
- Check that all files are uploaded
- Go to Actions tab to see the workflows

## 5. Enable GitHub Actions
- In your repo, go to Settings → Actions → General
- Under "Workflow permissions", select "Read and write permissions"
- Check "Allow GitHub Actions to create and approve pull requests"
- Click Save

## 6. Test the Workflows
- Go to Actions tab
- Click on "URL Status Scanner" workflow
- Click "Run workflow" to test manually
- Check that it runs successfully

## 7. Check Neocities Deployment
- After the scanner completes, the deploy workflow should run automatically
- Verify that your Neocities site is updated with the latest results
