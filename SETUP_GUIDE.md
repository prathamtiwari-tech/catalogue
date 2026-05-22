```markdown
# Business Catalogue - GitHub Publishing Setup Guide

## 🚀 Overview
This catalogue system allows admins to manage content and automatically publish changes to your GitHub repository. All users see the same updated data in real-time.

## ⚙️ Setup Instructions

### Step 1: Generate GitHub Personal Access Token

1. Go to [GitHub Settings](https://github.com/settings/profile)
2. Click **Developer settings** (left sidebar)
3. Click **Personal access tokens** → **Tokens (classic)**
4. Click **Generate new token (classic)**

### Step 2: Configure Token Permissions

Select the following scopes:
- ✅ `repo` - Full control of private repositories
- ✅ `workflow` - Update GitHub Action workflows

### Step 3: Copy Your Token

- GitHub will display your token **only once**
- Click the copy icon and save it securely
- **Never share this token publicly**

### Step 4: Use Token in Admin Panel

1. Access admin panel: `?admin`
2. Login with credentials:
   - **Username:** `admin`
   - **Password:** `admin123`
3. Paste your GitHub token in the "GitHub Personal Access Token" field
4. Login

## 📝 How It Works

### User Panel (Default View)
- Display published tiles and contact information
- Read-only access
- Auto-refreshes to show latest changes from GitHub

### Admin Panel (With `?admin`)
Three management tabs:

#### 1️⃣ **Manage Tiles**
- Add new business tiles with:
  - Title
  - Description
  - Link/URL
  - Image upload (max 2MB)
- View all published tiles
- Delete tiles
- Changes automatically publish to GitHub

#### 2️⃣ **Contact Details**
- Update phone number
- Email address
- Physical address
- Website
- Click "Publish Changes to GitHub" to save

#### 3️⃣ **Preview & Download**
- Preview complete catalogue
- Download as PDF with:
  - All contact details
  - All tiles with images
  - Professional formatting
  - Timestamp

## 🔄 Data Flow

```
Admin Panel
    ↓
Publish Changes
    ↓
GitHub Repository (catalogue-data.json)
    ↓
User Panel (Auto-loads latest data)
    ↓
Other Users (See updated content)
```

## 📂 File Structure

After first publish, you'll see:
```
/catalogue/
├── index.html                 (Main application)
├── catalogue-data.json        (Published data - auto-generated)
└── README.md                  (This file)
```

## 🔐 Security Notes

1. **Token Security:**
   - Tokens are NOT stored permanently
   - Only kept in memory during admin session
   - Clear token when logging out
   - Use different tokens for different purposes

2. **Local Fallback:**
   - If GitHub token isn't provided, data saves locally only
   - Useful for testing without publishing
   - Data stored in browser's localStorage

3. **Credentials:**
   - Default: admin / admin123
   - Change in code if needed (search for hardcoded check)

## 🌍 Global Publishing

When admin publishes:
1. Data is saved to `catalogue-data.json` in GitHub
2. User panel fetches latest data from GitHub on page load
3. All other users automatically see updated content
4. Changes propagate globally within seconds

## 🚨 Troubleshooting

### "GitHub token is invalid"
- Token may be expired or revoked
- Generate a new token and try again

### "GitHub Error: Not Found"
- Ensure repository is set to public (or token has access)
- Verify repository name is correct

### "Changes not updating"
- Hard refresh your browser (Ctrl+Shift+R)
- Clear browser cache
- Check GitHub to verify `catalogue-data.json` exists

### Image too large
- Maximum image size: 2MB
- Compress images before uploading
- Use free tools like TinyPNG

## 💡 Usage Examples

### Adding a Business
1. Go to Admin Panel → Manage Tiles
2. Enter business details
3. Upload logo/image
4. Click "Add Tile"
5. Changes automatically publish to GitHub

### Updating Contact Info
1. Go to Admin Panel → Contact Details
2. Update phone, email, address, website
3. Click "Publish Changes to GitHub"
4. All users see updates immediately

### Creating PDF
1. Go to Admin Panel → Preview & Download
2. Review the preview
3. Click "📥 Download as PDF"
4. Save to your computer

## 📞 Support

If you encounter issues:
1. Check browser console (F12) for error messages
2. Verify GitHub token permissions
3. Ensure repository is accessible
4. Try clearing localStorage and reloading

## 🎯 Features

✅ User panel with tiles and contact info  
✅ Admin authentication  
✅ Image upload support  
✅ Automatic GitHub publishing  
✅ Real-time global updates  
✅ PDF download  
✅ Responsive design  
✅ LocalStorage fallback  
✅ Data validation  
✅ Security measures  

---

**Last Updated:** 2026  
**Repository:** [prathamtiwari-tech/catalogue](https://github.com/prathamtiwari-tech/catalogue)
```
