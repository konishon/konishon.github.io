# GitHub Pages Deployment Guide

## Overview

This repository is now configured with GitHub Actions to automatically deploy your Jekyll site to GitHub Pages. The deployment happens automatically whenever you push changes to the `main` branch.

## One-Time Setup (Required)

Before the workflow can deploy your site, you need to configure GitHub Pages in your repository settings:

### Step 1: Enable GitHub Actions for GitHub Pages

1. Go to your repository on GitHub: `https://github.com/konishon/konishon.github.io`
2. Click on `Settings` (top menu)
3. In the left sidebar, click on `Pages`
4. Under the "Build and deployment" section:
   - **Source**: Select `GitHub Actions` from the dropdown menu
   - This tells GitHub to use the workflow file we've created instead of the default Jekyll build

### Step 2: Verify the Workflow

1. After merging this PR to the `main` branch
2. Go to the `Actions` tab in your repository
3. You should see a workflow run called "Deploy Jekyll site to Pages"
4. Click on it to see the progress
5. The workflow will:
   - Install Ruby and dependencies
   - Build your Jekyll site
   - Deploy it to GitHub Pages

### Step 3: Access Your Site

Once the workflow completes successfully:
- Your site will be live at: `https://konishon.github.io/`
- It may take a few minutes for the first deployment

## How It Works

The GitHub Actions workflow (`.github/workflows/jekyll.yml`) does the following:

1. **Triggers**: Runs on every push to `main` branch, or can be manually triggered
2. **Build Job**: 
   - Checks out the code
   - Sets up Ruby environment
   - Installs dependencies (using Gemfile)
   - Builds the Jekyll site
   - Uploads the built site as an artifact
3. **Deploy Job**:
   - Takes the built artifact
   - Deploys it to GitHub Pages

## Automatic Deployment

After the initial setup, deployment is automatic:
- Push changes to `main` branch → Site rebuilds and deploys automatically
- Typically takes 2-3 minutes to complete

## Manual Deployment

You can also manually trigger a deployment:
1. Go to the `Actions` tab
2. Click on "Deploy Jekyll site to Pages" workflow
3. Click "Run workflow"
4. Select the branch (usually `main`)
5. Click "Run workflow" button

## Local Development

To preview changes locally before pushing:

```bash
# Install dependencies
bundle install

# Start local server
bundle exec jekyll serve

# Open browser to http://localhost:4000
```

## Troubleshooting

### Workflow fails with "Permission denied"
- Make sure you've set the Source to "GitHub Actions" in Settings > Pages

### Site not updating after deployment
- Check the Actions tab to ensure the workflow completed successfully
- GitHub Pages may take a few minutes to update
- Try clearing your browser cache

### Ruby version errors
- The workflow uses Ruby 3.1. If you need a different version, edit `.github/workflows/jekyll.yml`

## Additional Configuration

### Custom Domain
If you want to use a custom domain:
1. Go to Settings > Pages
2. Add your custom domain in the "Custom domain" field
3. Add a `CNAME` file to your repository root with your domain name

### Base URL
The workflow automatically configures the base URL. If you need to override it:
- Edit `_config.yml` and set the `baseurl` and `url` fields
- For this repository (`konishon.github.io`), the baseurl should be empty (`''`)

## Next Steps

1. Merge this PR to the `main` branch
2. Follow Step 1 above to enable GitHub Actions in repository settings
3. Your site will automatically deploy!
