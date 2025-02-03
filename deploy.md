# Deploying to GitHub Pages

This guide provides a step-by-step walkthrough to deploy the production version of the project to GitHub Pages.

## Step 1: Configure Vite for GitHub Pages

Update your `vite.config.js` file to set the base URL to your repository name. For example, if your repository is located at `https://github.com/roryp/deepseek-r1-webgpu`, modify the configuration as follows:

```js
import { defineConfig } from 'vite';
import tailwindcss from '@tailwindcss/vite';
import react from '@vitejs/plugin-react';

export default defineConfig({
  base: '/deepseek-r1-webgpu/',
  plugins: [tailwindcss(), react()],
});
```

## Step 2: Branch Setup

Create a new branch called `gh-pages`, or configure your CI to build and push to `gh-pages`.

## Step 3: Updated Build Process

Modify your build scripts to generate production-ready artifacts (e.g., minification, bundling). Ensure the output folder (e.g., `dist` or `build`) is correctly placed for deployment.

## Step 4: Commit and Push

Commit the generated build files. Push the changes to the `gh-pages` branch.

## Step 5: GitHub Pages Configuration

In your GitHub repository settings, enable GitHub Pages and set `gh-pages` as the source.

## Step 6: View Your Site

Access your published site at `https://<USERNAME>.github.io/<REPO>`.

## Step 7: Build the Production Version

Generate a production build to create an optimized output in the dist folder by running:

```sh
npm run build
```

## Step 8: Deploy to GitHub Pages using gh-pages

Install gh-pages:
Ensure that the gh-pages package is installed as a dev dependency:

```sh
npm install --save-dev gh-pages
```

## Step 9: Check the deploy script in package.json

Confirm that your package.json includes the following deploy script:

```json
{
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "lint": "eslint .",
    "preview": "vite preview",
    "deploy": "gh-pages -d dist"
  }
  // ...existing code...
}
```
