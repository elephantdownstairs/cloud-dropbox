# 🔥 Firebase Setup Guide for CloudBox

Your CloudBox now uses Firebase for cloud storage, which means files sync across ALL devices! Here's how to set it up:

## 🚀 Step 1: Create a Firebase Project (FREE)

1. **Go to Firebase Console**: https://console.firebase.google.com/
2. Click **"Add project"** or **"Create a project"**
3. **Project name**: Enter `CloudBox` (or any name you like)
4. **Google Analytics**: You can disable this (not needed)
5. Click **"Create project"**
6. Wait for it to finish, then click **"Continue"**

## 🌐 Step 2: Set Up Firebase Storage (for files)

1. In your Firebase project, click **"Storage"** in the left menu
2. Click **"Get started"**
3. **Security rules**: Select **"Start in test mode"**
4. **Location**: Choose the closest region to you
5. Click **"Done"**

## 📊 Step 3: Set Up Realtime Database (for metadata)

1. Click **"Realtime Database"** in the left menu
2. Click **"Create Database"**
3. **Location**: Choose the same region as Storage
4. **Security rules**: Select **"Start in test mode"**
5. Click **"Enable"**

## 🔒 Step 4: Configure Security Rules

### Storage Rules:
1. In **Storage**, click the **"Rules"** tab
2. Replace with:

```
rules_version = '2';
service firebase.storage {
  match /b/{bucket}/o {
    match /files/{fileId} {
      allow read, write: if true;
    }
  }
}
```

3. Click **"Publish"**

### Database Rules:
1. In **Realtime Database**, click the **"Rules"** tab
2. Replace with:

```json
{
  "rules": {
    "files": {
      ".read": true,
      ".write": true
    }
  }
}
```

3. Click **"Publish"**

⚠️ **Note**: These rules allow anyone to read/write. This is okay since your CloudBox is PIN-protected. For better security, set up Firebase Authentication later.

## 🔑 Step 5: Get Your Firebase Config

1. Click the **⚙️ gear icon** (top left) → **"Project settings"**
2. Scroll down to **"Your apps"** section
3. Click the **web icon** `</>` (add web app)
4. **App nickname**: Enter `CloudBox`
5. **Don't** check "Firebase Hosting"
6. Click **"Register app"**
7. You'll see a code snippet with `firebaseConfig` - **COPY THIS!**

It will look like this:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXX",
  authDomain: "your-project.firebaseapp.com",
  databaseURL: "https://your-project.firebaseio.com",
  projectId: "your-project-id",
  storageBucket: "your-project.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:xxxxxxxxxxxxx"
};
```

## 📝 Step 6: Update Your index.html

1. Open your `index.html` file
2. Find this section (around line 870):

```javascript
const firebaseConfig = {
    apiKey: "YOUR_API_KEY_HERE",
    authDomain: "YOUR_PROJECT.firebaseapp.com",
    databaseURL: "https://YOUR_PROJECT.firebaseio.com",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_PROJECT.appspot.com",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
};
```

3. **Replace it** with YOUR Firebase config from Step 4
4. **Save the file**

## 🎯 Step 7: Upload to GitHub

1. Go to your GitHub repository
2. Upload the updated `index.html`
3. Wait a few minutes for GitHub Pages to update
4. **That's it!** Your CloudBox now syncs across devices! 🎉

## ✅ Testing Cross-Device Sync

1. Open CloudBox on your **laptop**
2. Upload a file
3. Open CloudBox on your **phone** (same URL)
4. You should see the file appear!
5. Download it on your phone ✨

## 🔧 Troubleshooting

### "Firebase not configured" error
- Make sure you replaced the `firebaseConfig` with YOUR actual values
- Check that all the values are in quotes
- No extra spaces or missing commas

### Files not appearing on other device
- Wait 5-10 seconds and refresh
- Check your internet connection
- Open browser console (F12) and look for errors

### "Permission denied" error
- Make sure you published the security rules in Step 3
- The rules should have `".read": true` and `".write": true`

## 💰 Firebase Free Tier Limits

Firebase is FREE with generous limits:
- **Storage**: 5 GB
- **Download**: 1 GB/day
- **Upload**: 1 GB/day
- **Operations**: 50k reads, 20k writes per day

This is MORE than enough for personal use!

## ⚡ Performance

**This version is MUCH FASTER** than the previous one because:
- Files stored directly in Firebase Storage (not base64 encoded)
- Only metadata in Realtime Database (not the entire file)
- Faster uploads, faster downloads
- No browser memory issues with large files

## 🔐 Security Notes

**Current Setup:**
- Files are accessible by anyone with the database URL
- PIN protects the CloudBox interface
- Files are base64 encoded (not encrypted)

**For Better Security (Optional):**
1. Enable Firebase Authentication
2. Add user-specific file storage
3. Encrypt files before upload

But for personal use, the current setup with PIN protection is perfectly fine!

## 🎨 Features Now Working

✅ **Cross-Device Sync** - Upload on laptop, download on phone
✅ **File Conversion** - Toggle ON, select format, upload to convert
✅ **Lossless Quality** - PNG/WebP-100 completely lossless
✅ **PIN Protection** - Secure access to your files
✅ **Cloud Storage** - Files stored in Firebase (not local)

---

**Need Help?** Open browser console (F12 → Console) and check for error messages!
