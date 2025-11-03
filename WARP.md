# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

A vanilla HTML/CSS/JavaScript portfolio website designed for GitHub Pages deployment. No build tools or frameworks required—just static files served directly.

## Development Commands

### Local Development
```powershell
# Start local development server (Python)
python -m http.server 8000

# Alternative: Node.js server
npx http-server

# Visit: http://localhost:8000
```

### Testing
```powershell
# Currently no tests configured
npm test  # Will echo "No tests yet"
```

## Deployment

### GitHub Pages Deployment
This site is designed for free hosting on GitHub Pages:

```powershell
# Initial setup (if not already done)
git init
git add .
git commit -m "Initial commit"

# Push to GitHub
git remote add origin https://github.com/USERNAME/REPO_NAME.git
git branch -M main
git push -u origin main
```

After pushing, enable GitHub Pages in repository Settings → Pages → select `main` branch.

### Custom Domain Setup
To use a custom domain, create a `CNAME` file in the project root containing your domain name (e.g., `yourdomain.com`), then configure DNS records at your registrar:
- A Records pointing to GitHub Pages IPs (185.199.108-111.153)
- CNAME Record: www → YOUR_USERNAME.github.io

## Architecture & Structure

### File Organization
- **index.html** - Single-page application structure with all sections
- **styles.css** - All styles with CSS custom properties for theming
- **script.js** - Interactive features and animations
- **.nojekyll** - Disables Jekyll processing on GitHub Pages

### Design System
CSS variables (`:root` in `styles.css`, lines 8-18) define the color palette and design tokens:
- Primary: #6366f1 (indigo)
- Secondary: #8b5cf6 (purple)
- Hero gradient: 135deg from #667eea to #764ba2

### Key Architectural Patterns

#### Section-Based Layout
All content is organized into semantic HTML5 sections within a single page:
1. Hero - Landing section with gradient background
2. About - Stats and description
3. Skills - Categorized skill cards (Front-End, Back-End, Database, Tools)
4. Projects - Project cards with hover overlays
5. Contact - Contact form and methods

#### Responsive Navigation
Mobile-first hamburger menu that transforms into horizontal nav on desktop. Navigation includes smooth scrolling with scroll spy (active link highlighting based on viewport position).

#### Animation System
Two animation approaches:
1. **Intersection Observer** (`script.js`, lines 64-86) - Fade-in on scroll for sections
2. **CSS transitions** - Hover states and interactive effects
3. **Typing effect** - Hero subtitle animation on page load (lines 133-150)

#### Form Handling
Contact form (`#contactForm`) currently shows alert on submit. To enable real submissions, integrate with:
- **Formspree**: Update form action attribute
- **EmailJS**: Add SDK and modify submit handler
- **Netlify Forms**: Add `netlify` attribute and deploy on Netlify

### JavaScript Modules Overview

**script.js** is organized by feature:
- Lines 1-32: Mobile navigation toggle
- Lines 34-49: Smooth scrolling for anchor links
- Lines 51-62: Navbar background on scroll
- Lines 64-86: Intersection Observer for fade-in animations
- Lines 88-109: Active navigation link highlighting
- Lines 111-131: Contact form submission
- Lines 133-150: Typing effect for hero subtitle
- Lines 152-163: Project card hover effects
- Lines 165-177: Skill tag staggered animations
- Lines 179-181: Console welcome messages

### CSS Architecture

**styles.css** follows this structure:
- Lines 1-49: Reset, variables, and base styles
- Lines 50-116: Navigation and mobile menu
- Lines 118-211: Hero section with gradient
- Lines 213-254: About section with stats
- Lines 256-311: Skills grid and cards
- Lines 313-419: Projects grid and cards
- Lines 421-498: Contact section and form
- Lines 500-505: Footer
- Lines 507-517: Keyframe animations
- Lines 519-585: Responsive breakpoints (768px, 480px)

## Customization Guidance

### Personal Information
Update these placeholders in `index.html`:
- "Your Name" (lines 7, 16, 37, 260)
- Social media URLs (lines 47-55)
- Email address (line 233)
- Location (line 237)
- Stats in About section (lines 78-89)

### Adding Projects
Duplicate `.project-card` blocks (lines 151-172 in `index.html`). Each card requires:
- Project image URL
- Live demo link
- GitHub repository link
- Project title, description, and technology tags

### Color Scheme
Modify CSS variables in `styles.css` (lines 8-18) to rebrand. All colors reference these variables, ensuring consistent theming.

### Skills
Update skill categories and tags in Skills section (lines 96-143 in `index.html`). Each category has Font Awesome icon and skill tags.

## Dependencies

### External Resources
- **Font Awesome 6.4.0** (CDN) - Icon library for social links and section icons
- No npm packages in production build
- `package.json` only used for metadata and dev server script

### Browser Compatibility
Modern browsers with ES6+ support (Chrome, Firefox, Safari, Edge latest versions). Uses:
- CSS Grid and Flexbox
- Intersection Observer API
- CSS Custom Properties
- ES6 arrow functions and const/let

## Common Modifications

### Integrating Backend for Contact Form
Replace form alert (lines 111-131 in `script.js`) with actual API call:
```javascript
contactForm.addEventListener('submit', async (e) => {
    e.preventDefault();
    const formData = { /* ... */ };
    await fetch('YOUR_API_ENDPOINT', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(formData)
    });
});
```

### Disabling Animations
To disable typing effect or other animations, comment out relevant sections in `script.js` or remove animation CSS from `styles.css`.

### Adding Analytics
Insert tracking code before closing `</body>` tag in `index.html` (before line 264).
