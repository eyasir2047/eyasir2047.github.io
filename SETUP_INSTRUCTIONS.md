# Website Setup Instructions

Your academic homepage has been configured with your personal information! Follow these steps to complete the setup and publish your website.

## 📸 Step 1: Add Your Profile Photo

1. **Prepare your photo:**
   - Use a professional headshot or profile photo
   - Recommended size: 512x512 pixels or larger (square format works best)
   - Supported formats: JPG, PNG, or WebP
   - File should be clear and professional

2. **Add the photo to your website:**
   - Copy your profile photo to the `images/` folder
   - Rename it to `profile.jpg` (or `profile.png` if PNG format)
   - The path should be: `eyasir2047.github.io/images/profile.jpg`

   **Command to copy (example):**
   ```bash
   cp /path/to/your/photo.jpg "eyasir2047.github.io/images/profile.jpg"
   ```

3. **Alternative:** If you don't have a photo ready yet, you can use a placeholder:
   - The website will work without a photo, but the image will show as broken
   - You can add it later and push an update

## 🎨 Step 2: Optional - Add Project Images

To make your projects more visually appealing, you can add screenshots:

1. Add images to the `images/` folder with these names:
   - `zerobin.png` - Screenshot of your ZeroBin project
   - `hpc.png` - Screenshot of your HPC/Distributed ML project

2. These images will automatically display in the project boxes on your homepage

## 🚀 Step 3: Test Locally (Recommended)

Before publishing, test your website locally to ensure everything looks good:

### Prerequisites
You need to install Jekyll and its dependencies:

**On macOS:**
```bash
# Install Ruby (if not already installed)
brew install ruby

# Add Ruby to your PATH (add to ~/.zshrc)
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc

# Install Jekyll and Bundler
gem install jekyll bundler
```

**On Linux:**
```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
gem install jekyll bundler
```

### Run Local Server

1. Navigate to your website directory:
   ```bash
   cd "/Users/eyasir2047/Desktop/After grad/portfolio/eyasir2047.github.io"
   ```

2. Install dependencies:
   ```bash
   bundle install
   ```

3. Start the local server:
   ```bash
   bash run_server.sh
   ```
   
   Or manually:
   ```bash
   bundle exec jekyll serve
   ```

4. Open your browser and visit:
   ```
   http://127.0.0.1:4000
   ```

5. The website will automatically reload when you make changes to the files

## 📤 Step 4: Publish to GitHub Pages

Once you're satisfied with your website:

### First-time Setup

1. **Create a new GitHub repository:**
   - Go to https://github.com/new
   - Repository name: `eyasir2047.github.io` (MUST match your username)
   - Make it **Public**
   - Do NOT initialize with README, .gitignore, or license
   - Click "Create repository"

2. **Push your website to GitHub:**
   ```bash
   cd "/Users/eyasir2047/Desktop/After grad/portfolio/eyasir2047.github.io"
   
   # Initialize git repository (if not already done)
   git init
   
   # Add all files
   git add .
   
   # Create first commit
   git commit -m "Initial commit: Personal academic homepage"
   
   # Add remote repository
   git remote add origin https://github.com/eyasir2047/eyasir2047.github.io.git
   
   # Push to GitHub
   git branch -M main
   git push -u origin main
   ```

3. **Enable GitHub Pages:**
   - Go to your repository settings: https://github.com/eyasir2047/eyasir2047.github.io/settings/pages
   - Under "Source", select branch: `main` and folder: `/ (root)`
   - Click "Save"
   - Your site will be published at: https://eyasir2047.github.io

4. **Wait 2-5 minutes** for GitHub Pages to build and deploy your site

### Updating Your Website

Whenever you make changes:

```bash
cd "/Users/eyasir2047/Desktop/After grad/portfolio/eyasir2047.github.io"

# Add changed files
git add .

# Commit changes
git commit -m "Update: describe your changes"

# Push to GitHub
git push
```

Your website will automatically update within a few minutes.

## 🔧 Optional Enhancements

### 1. Set Up Google Scholar (When Available)

Once you create a Google Scholar profile:

1. Find your Google Scholar ID from your profile URL:
   ```
   https://scholar.google.com/citations?user=YOUR_SCHOLAR_ID
   ```

2. Add it to GitHub Secrets:
   - Go to: Settings → Secrets and variables → Actions → New repository secret
   - Name: `GOOGLE_SCHOLAR_ID`
   - Value: Your Scholar ID

3. Update `_config.yml`:
   ```yaml
   google_scholar_stats_use_cdn: true
   ```
   
4. Add your Scholar URL in `_config.yml` under author section:
   ```yaml
   googlescholar: "https://scholar.google.com/citations?user=YOUR_SCHOLAR_ID"
   ```

5. Enable GitHub Actions:
   - Go to the "Actions" tab in your repository
   - Click "I understand my workflows, go ahead and enable them"

### 2. Set Up Google Analytics (Optional)

Track your website visitors:

1. Create a Google Analytics account: https://analytics.google.com/
2. Get your Measurement ID (format: G-XXXXXXXXXX)
3. Add it to `_config.yml`:
   ```yaml
   google_analytics_id: "G-XXXXXXXXXX"
   ```

### 3. Generate Custom Favicon

Create a custom favicon for your website:

1. Use a favicon generator: https://redketchup.io/favicon-generator
2. Upload your logo or initials
3. Download all generated files
4. Copy them to the `images/` folder, replacing existing files

### 4. Add Custom Domain (Optional)

If you want to use a custom domain (e.g., abrarayasir.com):

1. Buy a domain from a registrar (Namecheap, GoDaddy, etc.)
2. Add a `CNAME` file to your repository root with your domain:
   ```
   abrarayasir.com
   ```
3. Configure DNS settings at your registrar:
   - Add a CNAME record pointing to `eyasir2047.github.io`
4. Enable HTTPS in GitHub Pages settings

## 📝 Content Updates

### Adding New Projects

Edit `_pages/about.md` and add a new project in the "Selected Projects" section:

```markdown
**Your Project Name** <span style="float: right;">*Date Range*</span>

[GitHub](https://github.com/yourusername/project) | [Live Demo](https://your-demo.com)

- Description of your project
- Key technologies used
- Results achieved
```

### Adding News Items

Add new entries at the top of the "News" section:

```markdown
- *2026.XX*: &nbsp;🎉 Your news item here
```

### Updating Experience

Add new positions in the "Experience" section following the existing format.

## 🆘 Troubleshooting

### Website Not Showing Up
- Wait 5-10 minutes after first push
- Check GitHub Actions tab for build errors
- Ensure repository name is exactly `eyasir2047.github.io`
- Verify GitHub Pages is enabled in settings

### Images Not Loading
- Check file paths are correct
- Ensure images are in the `images/` folder
- Verify image file extensions match what's in the code
- Try clearing browser cache

### Local Server Not Starting
- Ensure Ruby and Jekyll are installed
- Run `bundle install` first
- Check for port conflicts (default: 4000)
- Try `bundle exec jekyll serve --trace` for detailed errors

### Changes Not Appearing
- Clear browser cache (Cmd+Shift+R on Mac, Ctrl+Shift+R on Windows)
- Wait a few minutes for GitHub Pages to rebuild
- Check git status to ensure changes were committed and pushed

## 📞 Need Help?

If you encounter any issues:

1. Check the Jekyll documentation: https://jekyllrb.com/docs/
2. Review GitHub Pages docs: https://docs.github.com/en/pages
3. Check the original template issues: https://github.com/RayeRen/acad-homepage.github.io/issues

## ✅ Checklist

- [ ] Add profile photo to `images/profile.jpg`
- [ ] (Optional) Add project screenshots
- [ ] Test website locally
- [ ] Create GitHub repository `eyasir2047.github.io`
- [ ] Push code to GitHub
- [ ] Enable GitHub Pages
- [ ] Verify website is live at https://eyasir2047.github.io
- [ ] (Optional) Set up Google Analytics
- [ ] (Optional) Configure Google Scholar integration
- [ ] Share your website URL!

---

**Your website will be live at:** https://eyasir2047.github.io

Good luck with your academic homepage! 🚀
