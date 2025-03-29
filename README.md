name: CI Pipeline

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Code
        uses: actions/checkout@v4

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 18

      - name: Install Dependencies
        run: npm install

      - name: Run Tests
        run: npm test
        Step 5: Monitor the Workflow
Once you push the changes, GitHub Actions will trigger the workflow. You can monitor the progress of the workflow in the Actions tab of your GitHub repository.

If everything is configured correctly, the workflow will build the app and deploy it to GitHub Pages.
If there are any issues, you can view the logs in the Actions tab to diagnose the problem.
Step 6: Access the Deployed App
Once the deployment is successful, you can access your React app at the URL specified in your homepage field in package.json, which will look like:

https://<your-username>.github.io/<repository-name>
Step 7: (Optional) Configure a Custom Domain (If Needed)
If you want to use a custom domain for your GitHub Pages site, follow these steps:

Create a CNAME file in your public directory (next to index.html).
Add your custom domain name to the CNAME file. For example:
www.your-custom-domain.com
Configure your DNS settings at your domain provider to point to GitHub's servers (the DNS records you need are typically provided in GitHub’s Pages documentation).
