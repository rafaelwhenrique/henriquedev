# Deploying to GitHub Pages

## Setup Formspree for Contact Form

1. Go to https://formspree.io
2. Sign up/login with GitHub
3. Create a new form
4. Copy your form endpoint (e.g., `f/abc123xyz`)
5. Open `index.html` and find this line:
   ```html
   <form id="contactForm" action="https://formspree.io/f/xyzabcde" method="POST">
   ```
6. Replace `f/xyzabcde` with your actual endpoint

## Deploy to GitHub Pages

### Step 1: Create Repository
- Go to https://github.com/new
- Name it: `henriquedev`
- Description: "Portfolio of Rafael Henrique"
- Set to **Public**
- Click "Create repository"

### Step 2: Push Your Code
```bash
cd c:\dev\portfolio

# Initialize git (if not already done)
git init

# Add remote repository
git remote add origin https://github.com/rafaelwhenrique/henriquedev.git

# Add all files
git add .

# Commit
git commit -m "Initial portfolio deployment"

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages
- Go to https://github.com/rafaelwhenrique/henriquedev/settings
- Scroll to "Pages" section
- Under "Source", select **Branch: main**
- Click **Save**

### Step 4: Verify Deployment
Your portfolio will be live at: **https://rafaelwhenrique.github.io/henriquedev/**

Wait about 1-2 minutes for GitHub to deploy.

## Files to Deploy

Only these files are needed:
- `index.html` (main file - contains all HTML, CSS, and JavaScript)
- Optional: `.nojekyll` (tells GitHub Pages to use all files)

### Create .nojekyll file:
```bash
touch .nojekyll
git add .nojekyll
git commit -m "Add .nojekyll for GitHub Pages"
git push
```

## Troubleshooting

### Contact form not sending emails?
- Check your Formspree form endpoint is correct in the HTML
- Verify you confirmed the form in Formspree's dashboard
- Check your email spam folder for Formspree verification email

### Site not showing up?
- Go to repo Settings → Pages and verify Branch is set to `main`
- Check the repository is **Public**
- Wait 2-3 minutes for deployment

### Dark/Light mode or language not persisting?
- This uses localStorage (browser storage) - works on deployed site
- Clear browser cache if testing locally and then on deployed version

## Local Testing

Before pushing to GitHub, test locally:

```bash
# Using Python 3
python -m http.server 8000

# Or using Node.js (if installed)
npx http-server

# Then open http://localhost:8000/index.html
```

Test:
- ✅ Language switching (Portuguese/English)
- ✅ Dark/Light mode toggle
- ✅ Animations render smoothly
- ✅ Contact form opens/closes
- ✅ All links work

## Future Updates

To update your portfolio:

```bash
# Make changes to index.html

# Commit and push
git add index.html
git commit -m "Update portfolio content"
git push
```

Changes will be live within seconds!

## Adding Projects

To add projects to your portfolio, edit `index.html` and find this section:

```javascript
const projects = [];
```

Add projects like this:

```javascript
const projects = [
    {
        title: "E-commerce Store",
        description: "Loja virtual para venda de produtos",
        description_en: "Online store for selling products",
        emoji: "🛍️",
        technologies: ["PHP", "MySQL", "HTML5", "CSS3"],
        github: "https://github.com/rafaelwhenrique/ecommerce",
        demo: "https://example-store.com"
    },
    {
        title: "Tic Tac Toe Game",
        description: "Jogo da velha com Python",
        description_en: "Tic tac toe game in Python",
        emoji: "🎮",
        technologies: ["Python", "CLI"],
        github: "https://github.com/rafaelwhenrique/tictactoe"
    }
];
```

Push your changes and they'll be live instantly!

## Custom Domain (Optional)

To use your own domain:
1. Add a `CNAME` file with your domain name
2. Update DNS settings at your domain provider
3. See GitHub Pages docs for detailed steps
