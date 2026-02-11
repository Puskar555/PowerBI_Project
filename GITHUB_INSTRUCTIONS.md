# GitHub Upload Instructions

Step-by-step guide to upload your Power BI project to GitHub.

---

## METHOD 1: Using GitHub Desktop (Easiest)

### Step 1: Download GitHub Desktop
1. Go to https://desktop.github.com/
2. Download and install GitHub Desktop
3. Sign in with your GitHub account

### Step 2: Create Repository on GitHub.com
1. Go to https://github.com
2. Click the "+" icon → "New repository"
3. Name: `powerbi-sales-analysis` (or your choice)
4. Description: "Sales Analytics Dashboard with Power BI - Customer Insights & Campaign ROI"
5. Choose: **Public** (for portfolio) or **Private**
6. ✅ Check "Add a README file" - UNCHECK THIS (we already have one)
7. Choose license: MIT License (recommended for portfolio)
8. Click "Create repository"

### Step 3: Clone to Your Computer
1. On your new repo page, click green "Code" button
2. Click "Open with GitHub Desktop"
3. Choose where to save it on your computer
4. Click "Clone"

### Step 4: Copy Your Files
1. Copy ALL files from the `powerbi-sales-analysis` folder I created
2. Paste them into the cloned repository folder on your computer
3. Your folder should look like:
   ```
   powerbi-sales-analysis/
   ├── README.md
   ├── FINAL_EXAM_5.pbix
   ├── .gitignore
   ├── documentation/
   ├── images/
   └── data/
   ```

### Step 5: Commit and Push
1. Open GitHub Desktop
2. You'll see all your files listed in "Changes"
3. In the bottom left:
   - Summary: "Initial commit: Sales Analytics Dashboard"
   - Description: "Added Power BI file and documentation"
4. Click "Commit to main"
5. Click "Push origin" (top right)

**DONE!** Your project is now on GitHub.

---

## METHOD 2: Using Git Command Line

### Prerequisites
- Install Git: https://git-scm.com/downloads
- Have a GitHub account

### Step 1: Create Repository on GitHub
Same as Method 1, Step 2

### Step 2: Navigate to Project Folder
```bash
# Open terminal/command prompt
# Navigate to where you want to save the project
cd Desktop
# Or wherever you want
```

### Step 3: Get Your Files
Option A - If you have the folder I created:
```bash
# Copy the powerbi-sales-analysis folder to your Desktop or preferred location
# Then navigate into it:
cd powerbi-sales-analysis
```

Option B - Download from this chat:
```bash
# Download all the files I created
# Then create the folder structure
```

### Step 4: Initialize Git
```bash
git init
git add .
git commit -m "Initial commit: Sales Analytics Dashboard"
```

### Step 5: Connect to GitHub
```bash
# Replace YOUR-USERNAME with your GitHub username
git remote add origin https://github.com/YOUR-USERNAME/powerbi-sales-analysis.git
git branch -M main
git push -u origin main
```

### Step 6: Enter Credentials
- Username: Your GitHub username
- Password: Your Personal Access Token (NOT your GitHub password)

**Getting Personal Access Token:**
1. GitHub.com → Settings → Developer settings
2. Personal access tokens → Tokens (classic)
3. Generate new token
4. Select scopes: `repo`
5. Copy the token and use as password

---

## METHOD 3: Upload Directly on GitHub.com (Quick but Limited)

### Steps:
1. Create new repository on GitHub.com
2. Click "uploading an existing file"
3. Drag and drop ALL your files
4. **Problem**: Can't upload folders directly
5. **Workaround**: Upload files one by one OR use Method 1 or 2

**Not Recommended** - too tedious for multiple folders

---

## What to Do AFTER Uploading

### 1. Add Screenshots
- Take screenshots of your Power BI dashboards
- Save as PNG files
- Upload to `images/screenshots/` folder
- Update README.md with screenshot links

### 2. Update README.md
Replace placeholders:
```markdown
## 👤 Author
**Your Name**
- GitHub: [@your-username](https://github.com/your-username)
- LinkedIn: [Your LinkedIn](https://linkedin.com/in/your-profile)
```

### 3. Add Topics (Tags)
On your repo page:
1. Click ⚙️ (settings icon) next to "About"
2. Add topics: `power-bi`, `data-analytics`, `dax`, `business-intelligence`, `dashboard`
3. Save changes

### 4. Enable GitHub Pages (Optional)
If you want a website for your project:
1. Repo Settings → Pages
2. Source: Deploy from branch
3. Branch: main, folder: root
4. Save

---

## Common Issues & Solutions

### Issue: "Permission Denied"
**Solution**: Use Personal Access Token instead of password

### Issue: "Large file warning" for .pbix
**Solution**: 
- .pbix files are usually <50MB (fine)
- If >100MB, use Git LFS:
  ```bash
  git lfs install
  git lfs track "*.pbix"
  git add .gitattributes
  ```

### Issue: "Repository not found"
**Solution**: Check URL has correct username and repo name

### Issue: Changes not showing
**Solution**: 
```bash
git status  # Check what's tracked
git add .   # Add all files
git commit -m "Update"
git push
```

---

## Folder Structure Verification

Before uploading, verify your folder looks like this:

```
powerbi-sales-analysis/
│
├── 📄 README.md                   ✅ Main project description
├── 📊 FINAL_EXAM_5.pbix          ✅ Your Power BI file
├── 🚫 .gitignore                 ✅ Tells Git what to ignore
│
├── 📁 documentation/
│   ├── data-model.md             ✅ Data model documentation
│   ├── measures-guide.md         ✅ DAX measures explained
│   └── model-diagram.txt         ✅ ASCII diagram
│
├── 📁 images/
│   └── screenshots/              ✅ (Empty - add your screenshots)
│       ├── overview.png          📷 Add this
│       ├── product-perf.png      📷 Add this
│       └── customer-insights.png 📷 Add this
│
└── 📁 data/
    └── (Empty - add sample data if allowed)
```

---

## Making It Portfolio-Ready

### 1. Add Professional README
✅ Already created - just customize the Author section

### 2. Take Good Screenshots
- Full screen, no personal info visible
- Show different pages
- Highlight key insights
- Use high resolution (1920x1080)

### 3. Add Description
On GitHub repo page, add:
> "Interactive Power BI dashboard analyzing sales performance, customer behavior, and marketing ROI using DAX measures and star schema data modeling"

### 4. Pin the Repository
- Go to your GitHub profile
- Click "Customize your pins"
- Select this repository
- Pin it to the top

### 5. Add to LinkedIn
- LinkedIn → Add to Profile → Projects
- Name: Sales Analytics Dashboard
- URL: Your GitHub repo link
- Description: Brief project summary

---

## Quick Checklist

Before sharing your GitHub link:

- [ ] All files uploaded
- [ ] README.md has your name/links
- [ ] Screenshots added
- [ ] Repository is public (if for portfolio)
- [ ] Topics/tags added
- [ ] Repository description filled
- [ ] .gitignore file included
- [ ] Documentation is complete

---

## Your GitHub URL Will Be:

```
https://github.com/YOUR-USERNAME/powerbi-sales-analysis
```

Share this link on:
- Resume
- LinkedIn
- Portfolio website
- Job applications

---

## Need Help?

If you get stuck:
1. Check GitHub's official guides: https://guides.github.com/
2. Ask me specific questions about any step
3. GitHub Desktop has built-in help

**Next Steps:**
1. Choose your method (GitHub Desktop recommended for beginners)
2. Follow the steps
3. Let me know when you're ready to upload and I can guide you
