# 🔥 CloudBox Firebase Setup Instructions

## ⚠️ Current Status: DEMO MODE

The CloudBox is currently using a demo database. **All files are visible to everyone**. To create your own private CloudBox:

## 📝 5-Minute Setup (FREE)

### Step 1: Create Firebase Project (2 min)
1. Go to https://console.firebase.google.com
2. Click **"Add Project"**
3. Enter project name: `my-cloudbox` (or anything you want)
4. Click **"Continue"**
5. **Disable Google Analytics** (not needed)
6. Click **"Create Project"**
7. Wait 30 seconds for project creation

### Step 2: Enable Realtime Database (1 min)
1. In left menu, click **"Realtime Database"**
2. Click **"Create Database"**
3. Choose location (closest to you)
4. Select **"Start in test mode"** (allows read/write for 30 days)
5. Click **"Enable"**

### Step 3: Get Your Config (1 min)
1. Click the **gear icon** ⚙️ next to "Project Overview"
2. Click **"Project settings"**
3. Scroll down to **"Your apps"** section
4. Click the **"</>"** button (Web app)
5. Enter app nickname: `cloudbox`
6. Click **"Register app"**
7. Copy the `firebaseConfig` object

### Step 4: Update Your Code (1 min)
1. Open `index.html` in text editor
2. Find line ~360 (search for `firebaseConfig`)
3. Replace the demo config with your own

4. Save the file
5. Upload to GitHub Pages

## ✅ Done!

Now your CloudBox is:
- **Private** - only accessible via your URL
- **Synced** - works across all your devices
- **Free** - Firebase free tier is generous (1GB storage, 10GB/month download)
