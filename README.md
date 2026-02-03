## GitHub Pages Blog

This project is a portfolio website for Nishon Tandukar, a geo-spatial data scientist and open-source developer, showcasing geo-spatial analysis projects and technical insights.

### Live Site

The site is deployed at: [https://konishon.github.io/](https://konishon.github.io/)

## Deployment to GitHub Pages

This repository is configured to automatically deploy to GitHub Pages using GitHub Actions.

### Setup Instructions

1. **Enable GitHub Pages in Repository Settings:**
   - Go to your repository on GitHub
   - Navigate to `Settings` > `Pages`
   - Under "Build and deployment" section:
     - Set **Source** to `GitHub Actions`
   
2. **Automatic Deployment:**
   - Once configured, the site will automatically build and deploy when you push to the `main` branch
   - You can also manually trigger deployment from the `Actions` tab

3. **Verify Deployment:**
   - Go to the `Actions` tab in your repository
   - You should see the "Deploy Jekyll site to Pages" workflow running
   - Once complete, your site will be live at `https://konishon.github.io/`

### Local Development

To run the site locally:

```bash
# Install dependencies
bundle install

# Serve the site locally
bundle exec jekyll serve

# The site will be available at http://localhost:4000
```

