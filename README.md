# Layer 7 - GitHub Pages Site

A modern, responsive website built with HTML and Tailwind CSS, featuring Layer 7's brand colors and Raleway typography.

## 🎨 Brand Colors

- **Dark Purple**: `#140a23`
- **Mid Purple**: `#1f1257`
- **Bright Purple**: `#a867f7`
- **Black**: `#000000`
- **White**: `#ffffff`

## 🚀 Deployment Strategy

This project uses a two-environment deployment strategy:

- **`dev` branch**: Development in GitHub Codespaces (local preview with hot reload)
- **`main` branch**: Production deployment to GitHub Pages (live site)

# 🚀 Deployment Strategy

This project uses a two-environment deployment strategy:

- **`dev` branch**: Development in GitHub Codespaces (local preview with hot reload)
- **`main` branch**: Production deployment to GitHub Pages (live site)

## 📦 Setup Instructions

### 1. Enable GitHub Pages

1. Go to your repository Settings
2. Navigate to "Pages" in the left sidebar
3. Under "Source", select "GitHub Actions"
4. Save the settings

### 2. Branch Setup

Create the `dev` branch if it doesn't exist:

```bash
git checkout -b dev
git push -u origin dev
```

### 3. Local Development in Codespaces

Your Codespace is pre-configured for instant development:

**Option 1: Python Server (Recommended)**
```bash
python3 -m http.server 8000
```

**Option 2: Live Server Extension**
1. Right-click on `index.html`
2. Select "Open with Live Server"
3. The site opens automatically with hot reload

**Option 3: npx http-server**
```bash
npx http-server -p 3000
```

The Codespace will automatically forward ports. Click the popup notification or go to the **Ports** tab to open your preview.

## 🔄 Deployment Workflow

### Developing in Codespaces (Dev Branch)

1. **Open your Codespace**
   - Go to your repository on GitHub
   - Click "Code" → "Codespaces" → Open your codespace

2. **Start the dev server**
   ```bash
   python3 -m http.server 8000
   ```

3. **Make your changes**
   - Edit HTML/CSS files in the Codespace editor
   - Save files and refresh browser to see changes
   - The dev branch is automatically checked out

4. **Commit and push changes**
   ```bash
   git add .
   git commit -m "Your commit message"
   git push origin dev
   ```

5. **Preview in Codespaces**
   - Your changes are immediately visible in the forwarded port
   - No deployment wait time - instant feedback!

### Deploying to Production

1. Once dev changes are verified in Codespaces, merge `dev` into `main`:

```bash
git checkout main
git merge dev
git push origin main
```

2. GitHub Actions will automatically deploy to production
3. Your site will be live at `https://yourusername.github.io/yourrepo/`

**Key Difference:**
- **Dev Branch**: Changes are previewed instantly in Codespaces (no deployment)
- **Main Branch**: Changes trigger automatic deployment to GitHub Pages (live site)

## 📁 Project Structure

```
.
├── .devcontainer/
│   └── devcontainer.json       # Codespaces configuration
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions deployment workflow
├── index.html                  # Main homepage
├── about.html                  # Sample about page
├── input.css                   # Your Tailwind theme config (optional)
├── README.md                   # This file
└── DEPLOYMENT.md               # Detailed deployment guide
```

## 📚 Documentation & Resources

- **[WORKFLOW.md](WORKFLOW.md)** - Visual workflow diagrams and branch strategy
- **[CODESPACES_GUIDE.md](CODESPACES_GUIDE.md)** - Quick start guide for GitHub Codespaces
- **[DEPLOYMENT.md](DEPLOYMENT.md)** - Detailed deployment workflow and troubleshooting
- **[dev.sh](dev.sh)** - Helper script for common tasks (run `./dev.sh` in terminal)

### Helper Script Usage

Make development easier with the included helper script:

```bash
# Interactive menu
./dev.sh

# Or use directly:
./dev.sh server    # Start dev server
./dev.sh status    # Check git status  
./dev.sh commit    # Quick commit & push
./dev.sh deploy    # Deploy to production
```

---

## 🎨 Using Tailwind CSS

This project uses Tailwind CSS via CDN for simplicity. The configuration includes:

- **Custom Colors**: All Layer 7 brand colors accessible as `layer7-dark`, `layer7-mid`, `layer7-bright`, etc.
- **Custom Font**: Raleway font family configured as the default sans-serif
- **Responsive Design**: Mobile-first approach with breakpoint utilities

### Example Usage

```html


  Heading



This uses Raleway
```

## 🔧 Adding Tailwind Plus Components

To use Tailwind Plus components:

1. Copy the component code from Tailwind UI
2. Paste into your HTML file
3. Adjust colors to use Layer 7 brand colors:
   - Replace `indigo` or `purple` with `layer7-bright`
   - Replace dark backgrounds with `layer7-dark` or `layer7-mid`

## 🌐 Environment URLs

- **Development (Codespaces)**: 
  - Accessed via forwarded ports in your Codespace
  - Instant preview at `https://YOUR_CODESPACE_NAME-8000.preview.app.github.dev/`
  - No deployment required - changes visible immediately
  
- **Production (GitHub Pages)**: 
  - Live site at `https://yourusername.github.io/yourrepo/`
  - Deployed automatically when you push to `main` branch

## 📝 Customization

### Updating Brand Colors

Edit the `tailwind.config` section in `index.html`:

```javascript
tailwind.config = {
    theme: {
        extend: {
            colors: {
                'layer7': {
                    'dark': '#140a23',
                    // Add more colors here
                }
            }
        }
    }
}
```

### Adding New Pages

1. Create a new HTML file (e.g., `about.html`)
2. Copy the structure from `index.html`
3. Update the content
4. Link to it from your navigation

## 🤝 Contributing

1. Create a feature branch from `dev`
2. Make your changes
3. Test locally
4. Push to `dev` for testing
5. Once verified, merge to `main` for production
