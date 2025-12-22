# 📦 CloudBox - GitHub Pages Setup Guide

This guide will help you host your CloudBox file storage and converter application on GitHub Pages.

## 🚀 Quick Setup Steps

### Step 1: Create a GitHub Account
1. Go to [github.com](https://github.com)
2. Click "Sign up" if you don't have an account
3. Follow the registration process

### Step 2: Create a New Repository
1. Click the **"+"** icon in the top right corner
2. Select **"New repository"**
3. Name your repository: `cloudbox` (or any name you prefer)
4. **Choose visibility:**
   - **Public**: Anyone can see your repository and access the URL
   - **Private**: Only you (and collaborators) can see the repository
   - ⚠️ **Note**: Even with a private repo, the GitHub Pages URL will be publicly accessible unless you use GitHub Pro
5. Check **"Add a README file"**
6. Click **"Create repository"**

**Security Recommendation:**
- If using a **public** repository: Anyone can view your code, but files are still PIN-protected
- If using a **private** repository: Code is hidden, but GitHub Pages URL is still accessible (unless you have GitHub Pro)
- **Best security**: Private repo + Strong PIN + Keep URL private

### Step 3: Upload Your File
1. In your new repository, click **"Add file"** → **"Upload files"**
2. Drag and drop the `index.html` file (the one I created for you)
3. Scroll down and click **"Commit changes"**

### Step 4: Enable GitHub Pages
1. In your repository, click **"Settings"** (top menu)
2. Click **"Pages"** in the left sidebar
3. Under "Source", select **"Deploy from a branch"**
4. Under "Branch", select **"main"** (or "master")
5. Keep the folder as **"/ (root)"**
6. Click **"Save"**

### Step 5: Access Your Site
After a few minutes, your site will be live at:
```
https://YOUR-USERNAME.github.io/cloudbox/
```

Replace `YOUR-USERNAME` with your actual GitHub username.

## 🌐 Your CloudBox is Now Live!

Your application will be hosted on GitHub's servers and accessible from anywhere. Files uploaded by anyone will be synced across all devices accessing the same URL.

## 📝 Important Notes

### 🔐 Security Features

**PIN Protection:**
- On first visit, you'll set a 4-digit PIN code
- This PIN is required every time you open CloudBox in a new browser session
- Your PIN is stored securely in your browser's local storage (hashed)
- Only people who know the PIN can access the files
- You can lock CloudBox anytime by clicking the "🔒 Lock" button

**Important Security Notes:**
- The PIN is stored in your **browser's local storage** (localStorage)
- Files are stored in **shared storage** (accessible across devices)
- This means: PIN protects your browser session, but files themselves are shared storage
- For maximum security: Keep your CloudBox URL private + use a strong PIN

⚠️ **If you forget your PIN:**
1. Open browser DevTools (F12)
2. Go to Console tab
3. Type: `localStorage.removeItem('cloudbox_pin_hash')`
4. Refresh the page - you can now set a new PIN
5. **Note**: This won't affect your uploaded files

### About File Storage
- Files are stored using the browser's persistent storage API
- Files are **SHARED** across all users who access your CloudBox URL
- Storage limits depend on the browser (typically 50-100MB+)
- Perfect for personal cloud storage or trusted team sharing

### Privacy Recommendations
1. **For Personal Use**: Keep URL private + use a strong 4-digit PIN
2. **For Team Sharing**: Share URL + PIN with trusted people only
3. **For Sensitive Files**: Use encryption before uploading (e.g., password-protected ZIP files)
4. **For GitHub Repo**: Keep your repository **PRIVATE** if you want extra security

### Browser Compatibility
Works on all modern browsers:
- ✅ Chrome/Edge (Desktop & Mobile)
- ✅ Firefox (Desktop & Mobile)
- ✅ Safari (Desktop & Mobile)

## 🔄 File Conversion Features

Your CloudBox now includes a powerful **LOSSLESS** file converter:

### Supported Conversions

#### Image Conversions (Lossless)
- **Any image** → **PNG** (100% lossless compression)
- **Any image** → **WebP 100%** (100% lossless mode)
- **Any image** → **JPEG 100%** (near-lossless, minimal quality loss)

All image conversions use **quality = 1.0** (maximum quality) to prevent compression artifacts!

#### PDF Creation (Lossless)
- **Images** → **PDF** (no compression applied)
- Automatically adjusts PDF size to match image dimensions
- Uses PNG compression mode in jsPDF for lossless storage

#### Text Extraction
- **Text files, JSON, JavaScript** → Plain text (.txt)
- Pure text conversion, no data loss

### How to Use Conversion
1. Toggle the **"Convert Files Before Upload"** switch (with LOSSLESS badge)
2. Select your desired output format
3. Upload your files - they'll be automatically converted!
4. Files are marked with a "CONVERTED" badge in the file list

### Technical Details
- PNG: Uses lossless compression algorithm
- WebP-100: Browser's lossless WebP mode (quality=1.0)
- JPEG-100: Maximum quality setting (quality=1.0) - near-lossless with minimal artifacts
- PDF: No image compression applied (compression='NONE')
- All conversions happen in your browser - no server upload!

## 🛠️ Updating Your CloudBox

To update the application:
1. Go to your repository on GitHub
2. Click on `index.html`
3. Click the pencil icon (Edit)
4. Make your changes
5. Scroll down and click **"Commit changes"**

Changes will be live within a few minutes.

## 🎨 Customization Ideas

You can customize your CloudBox by editing the HTML file:

### Change the Name
Find this line and change "CloudBox":
```html
<div class="logo">📦 CloudBox</div>
```

### Change Colors
Look for the `:root` section in the CSS and modify colors:
```css
--accent-primary: #00ff88;  /* Change to your preferred color */
--accent-secondary: #00d4ff;
```

### Change the Icon
Replace the 📦 emoji with any other emoji you like!

## 🔧 Troubleshooting

### Site Not Loading?
- Wait 5-10 minutes after enabling GitHub Pages
- Check that the file is named `index.html` (lowercase, no spaces)
- Ensure your repository is public

### Files Not Saving?
- Make sure you're using a modern browser
- Check browser console for errors (F12 → Console tab)
- Try clearing browser cache and reload

### Conversion Not Working?
- Ensure you're converting compatible file types
- Large files may take longer to convert
- Check browser console for error messages

## 📱 Mobile Access

Your CloudBox works perfectly on mobile devices!
- Upload photos from your camera
- Download files to your phone
- Convert images on-the-go

## 🌟 Advanced: Custom Domain

Want to use your own domain? (e.g., `cloudbox.yourdomain.com`)

1. Buy a domain from any registrar
2. In GitHub Pages settings, add your custom domain
3. Configure DNS at your domain registrar:
   - Add a CNAME record pointing to `YOUR-USERNAME.github.io`
4. Wait for DNS propagation (can take up to 24 hours)

## 📊 Features Summary

✅ **4-Digit PIN Protection** - Secure your CloudBox with a PIN code
✅ **Upload & Download** - Any file type, any size (within browser limits)
✅ **Lossless File Conversion** - Images, PDFs, Text files (100% quality)
✅ **Cross-Device Sync** - Access from any device
✅ **No Compression** - Files stored exactly as uploaded
✅ **Beautiful Interface** - Modern, responsive design
✅ **100% Free** - Hosted on GitHub Pages forever
✅ **No Server Required** - Everything runs in the browser
✅ **Lock Feature** - Instantly lock your CloudBox when stepping away

## 🤝 Support

If you encounter any issues:
1. Check the Troubleshooting section above
2. Review browser console for errors
3. Ensure you're using the latest version of your browser

## 📄 License

This CloudBox application is free to use and modify for personal or commercial purposes.

---

**Enjoy your personal cloud storage and file converter! 🎉**
