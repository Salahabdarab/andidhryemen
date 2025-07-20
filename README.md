#!/usr/bin/env bash
# deploy.sh: Script to push project to GitHub and deploy to Vercel

# Step 1: Initialize Git repository and push to GitHub
# Replace <GITHUB_USERNAME> with your GitHub username
GITHUB_USERNAME="Salahabdarab"
REPO_NAME="andid-hryemen"

echo "Initializing git repository..."
git init

echo "Adding all files..."
git add .

echo "Committing changes..."
git commit -m "Initial commit of Andid HR Yemen"

echo "Creating GitHub repository..."
gh repo create $GITHUB_USERNAME/$REPO_NAME --public --source=. --remote=origin --push

# Step 2: Deploy to Vercel
# Ensure you have Vercel CLI installed and logged in: npm i -g vercel && vercel login

echo "Deploying to Vercel..."
# Link the project (choose existing or create new)
vercel link
# Deploy to production
vercel --prod

echo "Deployment complete! Visit https://$REPO_NAME.vercel.app"
