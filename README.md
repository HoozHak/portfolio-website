# Portfolio Website

A modern, responsive portfolio website built with vanilla HTML, CSS, and JavaScript. Designed to showcase your full-stack development skills with a clean, professional interface.

## ✨ Features

- 🎨 Modern, gradient hero section with animations
- 📱 Fully responsive design (mobile, tablet, desktop)
- 🎭 Smooth scrolling and page transitions
- 💼 Sections for About, Skills, Projects, and Contact
- 🔗 Social media integration
- ⚡ Fast loading with no framework dependencies
- 🎯 SEO-friendly structure
- 🌐 Ready for GitHub Pages deployment

## 🚀 Free Hosting with GitHub Pages

This portfolio can be hosted **completely free** using GitHub Pages with your own custom domain!

### Deployment Steps

1. **Create a GitHub Repository**
   ```bash
   # Make sure you're in the project directory
   # Already initialized with git
   ```

2. **Add Your Files to Git**
   ```bash
   git add .
   git commit -m "Initial commit: Portfolio website"
   ```

3. **Create a GitHub Repository**
   - Go to [GitHub](https://github.com) and create a new repository
   - Name it whatever you like (e.g., `portfolio-website`)
   - **Do NOT** initialize with README (we already have one)

4. **Push to GitHub**
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   git branch -M main
   git push -u origin main
   ```

5. **Enable GitHub Pages**
   - Go to your repository on GitHub
   - Click **Settings** → **Pages**
   - Under "Source", select `main` branch
   - Click **Save**
   - Your site will be live at: `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`

### 🌐 Using a Custom Domain (FREE!)

You can use your own domain with GitHub Pages for free:

1. **Purchase a Domain** (from Namecheap, GoDaddy, Cloudflare, etc.)
   - Costs: ~$10-15/year for .com domains

2. **Configure DNS Settings**
   - Add these DNS records at your domain registrar:
   ```
   Type: A Record
   Host: @
   Value: 185.199.108.153
   
   Type: A Record
   Host: @
   Value: 185.199.109.153
   
   Type: A Record
   Host: @
   Value: 185.199.110.153
   
   Type: A Record
   Host: @
   Value: 185.199.111.153
   
   Type: CNAME Record
   Host: www
   Value: YOUR_USERNAME.github.io
   ```

3. **Add Custom Domain to GitHub**
   - In your repo: **Settings** → **Pages**
   - Enter your domain in "Custom domain"
   - Check "Enforce HTTPS" (after DNS propagates)

4. **Create CNAME File**
   - Create a file named `CNAME` in your project root
   - Add your domain: `yourdomain.com`
   - Commit and push

### Alternative Free Hosting Options

If you don't want to use GitHub Pages, here are other free options:

1. **Netlify** (netlify.com)
   - Drag & drop deployment
   - Free custom domain support
   - Automatic HTTPS

2. **Vercel** (vercel.com)
   - Git integration
   - Free custom domains
   - Automatic deployments

3. **Cloudflare Pages** (pages.cloudflare.com)
   - Free unlimited bandwidth
   - Fast global CDN
   - Custom domains

## 📝 Customization

### Update Your Information

1. **index.html**
   - Replace "Your Name" with your actual name
   - Update social media links (GitHub, LinkedIn, Twitter)
   - Add your email address
   - Update project information
   - Modify skills and technologies

2. **styles.css**
   - Change color scheme in CSS variables (lines 8-18)
   - Adjust fonts, spacing, or layout as needed

3. **script.js**
   - Customize animations and interactions
   - Integrate form submission with backend (see Form Integration below)

### Adding Projects

To add more projects, duplicate a `.project-card` block in `index.html`:

```html
<div class="project-card">
    <div class="project-image">
        <img src="your-image-url" alt="Project Name">
        <div class="project-overlay">
            <a href="live-demo-url" class="project-link" target="_blank">
                <i class="fas fa-external-link-alt"></i>
            </a>
            <a href="github-repo-url" class="project-link" target="_blank">
                <i class="fab fa-github"></i>
            </a>
        </div>
    </div>
    <div class="project-info">
        <h3>Project Name</h3>
        <p>Project description...</p>
        <div class="project-tags">
            <span>Tech1</span>
            <span>Tech2</span>
        </div>
    </div>
</div>
```

### Form Integration

The contact form currently shows an alert. To enable real submissions:

**Option 1: Formspree (Easiest)**
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST" id="contactForm">
```

**Option 2: EmailJS**
- Sign up at [EmailJS](https://www.emailjs.com/)
- Add their JavaScript SDK
- Update the form handler in `script.js`

**Option 3: Netlify Forms**
- Add `netlify` attribute to form
- Deploy on Netlify

## 🛠️ Local Development

To test locally:

```bash
# Using Python (if installed)
python -m http.server 8000

# Or using Node.js
npx http-server

# Then open: http://localhost:8000
```

## 📦 Project Structure

```
portfolio-website/
├── index.html          # Main HTML file
├── styles.css          # All CSS styles
├── script.js           # JavaScript functionality
├── .gitignore          # Git ignore rules
├── .nojekyll           # GitHub Pages configuration
├── package.json        # Project metadata
└── README.md           # This file
```

## 🎨 Technologies Used

- HTML5
- CSS3 (Flexbox, Grid, Animations)
- Vanilla JavaScript (ES6+)
- Font Awesome Icons
- GitHub Pages (Hosting)

## 📱 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## 📄 License

MIT License - feel free to use this template for your own portfolio!

## 🤝 Contributing

Found a bug or have a suggestion? Feel free to open an issue or submit a pull request!

## 📧 Contact

Update the contact section with your information and let people reach out to you!

---

**Built with ❤️ and hosted for FREE on GitHub Pages**
