# Deer Springs Ranch Map - GitHub Pages Deployment Guide

## Quick Start

This guide will help you deploy the Deer Springs Ranch interactive map to GitHub Pages so property owners can access it online.

## Step 1: Create a GitHub Account (if needed)

1. Go to https://github.com
2. Click "Sign up"
3. Follow the registration process

## Step 2: Create a New Repository

1. Log in to GitHub
2. Click the "+" icon in the top-right corner
3. Select "New repository"
4. Repository settings:
   - **Repository name**: `dsr-property-map` (or your preferred name)
   - **Description**: "Deer Springs Ranch Property Map for Association Members"
   - **Public** or **Private**: Choose based on your needs
     - Public: Anyone can view the map
     - Private: Only invited members can view (requires GitHub Pro)
   - **DO NOT** initialize with README (we already have one)
5. Click "Create repository"

## Step 3: Upload Files

### Option A: Web Interface (Easiest)

1. On your new repository page, click "uploading an existing file"
2. Drag and drop ALL files from the `dsr_map_data` folder:
   - index.html
   - README.md
   - All .geojson files
3. Add a commit message: "Initial map deployment"
4. Click "Commit changes"

### Option B: Git Command Line (Advanced)

```bash
# Navigate to your dsr_map_data folder
cd /path/to/dsr_map_data

# Initialize git repository
git init

# Add all files
git add .

# Commit
git commit -m "Initial map deployment"

# Add remote (replace USERNAME and REPO with yours)
git remote add origin https://github.com/USERNAME/REPO.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Step 4: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" tab
3. Click "Pages" in the left sidebar
4. Under "Source":
   - Select "Deploy from a branch"
   - Branch: Select "main"
   - Folder: Select "/ (root)"
5. Click "Save"

## Step 5: Access Your Map

After a few minutes (usually 1-2 minutes), your map will be live at:

```
https://[your-username].github.io/[repository-name]/
```

Example: `https://bartbattista.github.io/dsr-property-map/`

## Updating the Map

When you need to update the map with new data:

1. Export updated layers from QGIS to your GeoPackage
2. Convert to GeoJSON (use the Python script if needed)
3. Upload the new .geojson files to GitHub:
   - Go to the file in your repository
   - Click the pencil icon (Edit)
   - Drag and drop the new file
   - Commit changes
4. Changes will appear within 1-2 minutes

## Custom Domain (Optional)

If you want to use a custom domain like `map.deerspringsranch.org`:

1. In repository Settings → Pages → Custom domain
2. Enter your domain name
3. Configure DNS records with your domain provider:
   - Add CNAME record pointing to: `[username].github.io`
4. Enable "Enforce HTTPS"

## Sharing with Property Owners

Share the URL with association members via:
- Email announcement
- HOA website
- Printed materials with QR code
- Association newsletter

## Security Considerations

### For Public Repositories:
- Map is viewable by anyone with the URL
- No sensitive personal information should be included
- Consider removing detailed owner names if privacy is a concern

### For Private Repositories (GitHub Pro):
- Only invited collaborators can view
- More suitable for detailed ownership information
- Requires GitHub Pro subscription ($4/month)

## Maintenance

- **Regular updates**: Update culvert locations, new infrastructure quarterly
- **Data validation**: Verify accuracy of point locations before publishing
- **Backup**: Keep a copy of the GeoPackage in your local QGIS project

## Troubleshooting

### Map not displaying:
- Check that index.html is in the root directory
- Verify all .geojson files are uploaded
- Check browser console for errors (F12)

### Slow loading:
- GitHub Pages has bandwidth limits
- Consider optimizing large parcel data if needed
- Current file sizes are well within limits

### Changes not appearing:
- Wait 2-3 minutes for GitHub Pages to rebuild
- Clear your browser cache (Ctrl+Shift+R)
- Check GitHub Actions for build status

## Need Help?

- GitHub Pages Documentation: https://docs.github.com/pages
- Leaflet.js Documentation: https://leafletjs.com/reference.html
- Contact: Your GIS administrator

---

**Last Updated**: January 2026
**Created by**: Bartholomew Battista, PE - Cliffside Engineering PLLC
