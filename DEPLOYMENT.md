# 🚀 Deployment Guide

This guide provides step-by-step instructions for deploying the portfolio to various platforms.

## 📋 Prerequisites

- Git repository with your portfolio code
- Modern web browser
- GitHub account (for GitHub Pages)

## 🌐 Deployment Options

### 1. GitHub Pages (Recommended)

#### Step 1: Push to GitHub
```bash
git add .
git commit -m "Initial portfolio commit"
git push origin main
```

#### Step 2: Enable GitHub Pages
1. Go to your repository on GitHub
2. Click on "Settings"
3. Scroll down to "Pages" section
4. Under "Source", select "Deploy from a branch"
5. Choose "main" branch and "/ (root)" folder
6. Click "Save"

#### Step 3: Access Your Site
- Your site will be available at: `https://yourusername.github.io/repository-name`
- It may take a few minutes to deploy

### 2. Netlify

#### Step 1: Prepare for Netlify
1. Create a `netlify.toml` file in your project root:
```toml
[build]
  publish = "."
  command = ""

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

#### Step 2: Deploy
1. Go to [netlify.com](https://netlify.com)
2. Sign up/Login with GitHub
3. Click "New site from Git"
4. Choose your repository
5. Deploy settings:
   - Build command: (leave empty)
   - Publish directory: `.`
6. Click "Deploy site"

### 3. Vercel

#### Step 1: Install Vercel CLI
```bash
npm install -g vercel
```

#### Step 2: Deploy
```bash
vercel
```

#### Step 3: Follow Prompts
- Link to existing project: No
- Project name: your-portfolio-name
- Directory: ./
- Override settings: No

### 4. Firebase Hosting

#### Step 1: Install Firebase CLI
```bash
npm install -g firebase-tools
```

#### Step 2: Initialize Firebase
```bash
firebase login
firebase init hosting
```

#### Step 3: Configure
- Public directory: `.`
- Single-page app: No
- Overwrite index.html: No

#### Step 4: Deploy
```bash
firebase deploy
```

## 🔧 Configuration Files

### For Vercel (vercel.json)
```json
{
  "version": 2,
  "builds": [
    {
      "src": "*.html",
      "use": "@vercel/static"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "/$1"
    }
  ]
}
```

### For Netlify (netlify.toml)
```toml
[build]
  publish = "."
  command = ""

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

## 📱 Custom Domain (Optional)

### GitHub Pages
1. Go to repository Settings > Pages
2. Add custom domain in "Custom domain" field
3. Create CNAME record pointing to `yourusername.github.io`

### Netlify/Vercel
1. Go to domain settings in your dashboard
2. Add custom domain
3. Follow DNS configuration instructions

## 🔍 Testing Your Deployment

### Checklist
- [ ] All images load correctly
- [ ] Links work properly
- [ ] Responsive design works on mobile
- [ ] Animations function smoothly
- [ ] Contact form works (if applicable)
- [ ] CV download works

### Performance Testing
- Use Google PageSpeed Insights
- Test on different devices
- Check browser compatibility

## 🚨 Troubleshooting

### Common Issues

#### Images Not Loading
- Check file paths are correct
- Ensure images are in the right directory
- Verify image file names match exactly

#### Styling Issues
- Clear browser cache
- Check CSS file is properly linked
- Verify no syntax errors in CSS

#### Deployment Fails
- Check build logs for errors
- Ensure all files are committed
- Verify configuration files are correct

## 📞 Support

If you encounter issues:
1. Check the platform's documentation
2. Review build logs for errors
3. Test locally before deploying
4. Contact platform support if needed

---

**Happy Deploying! 🚀** 