# Quick Setup Instructions

Follow these steps to move backend to a new repository:

## 1. Create New GitHub Repository

1. Go to https://github.com/new
2. Name: `collaboard-backend`
3. Description: "Backend API for Collaboard collaborative whiteboard"
4. **Do NOT** initialize with README/license
5. Click "Create repository"

## 2. Initialize and Push Backend

Run these commands in the `backend` directory:

```bash
# Make sure you're in the backend directory
cd backend

# Initialize git (if not already initialized)
git init

# Add all files
git add .

# Initial commit
git commit -m "Initial commit: Collaboard backend API"

# Add remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/collaboard-backend.git

# Push to new repository
git branch -M main
git push -u origin main
```

## 3. Remove Backend from Frontend Repo

From the frontend repository root:

```bash
# Remove backend from git tracking
git rm -r --cached backend

# Commit
git commit -m "chore: Move backend to separate repository"

# Push
git push
```

## 4. Update Render/Railway Deployment

When deploying from the new backend repository:

**Render:**
- Root Directory: `./` (backend is now root)
- Build Command: `npm run build`
- Start Command: `npm start`

**Railway:**
- Auto-detects, no root directory needed

Done! ✅

