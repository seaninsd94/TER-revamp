# CLAUDE.md - AI Assistant Guide for TER-revamp

> This file provides context and guidelines for AI assistants working with this codebase.
> Last updated: 2026-02-12

## Project Overview

**Repository:** TER-revamp
**Status:** Active Development
**Description:** Professional luxury event design website for Tasteful Studio, a San Diego-based company offering curated event environments, tent, table, chair, lighting, and event equipment rentals.

**Live Site:** https://www.tastefulstudio.com/

---

## Quick Reference

### Common Commands

```bash
# Start local development server (using Python)
python -m http.server 8000
# Then open http://localhost:8000

# Or using Node.js (if available)
npx serve .

# Or using PHP (if available)
php -S localhost:8000
```

### Key Files to Know

| File/Directory | Purpose |
|---------------|---------|
| `CLAUDE.md` | AI assistant guidelines (this file) |
| `index.html` | Homepage |
| `pages/` | Subpages (rentals, packages, about, contact) |
| `css/styles.css` | Main stylesheet with all styling |
| `js/main.js` | JavaScript for interactivity |
| `images/` | Logo and placeholder image locations |

---

## Codebase Structure

```
TER-revamp/
├── CLAUDE.md              # AI assistant guidelines
├── index.html             # Homepage
├── css/
│   └── styles.css         # Main stylesheet (CSS variables, components)
├── js/
│   └── main.js            # Mobile menu, form validation, scroll effects
├── images/
│   ├── logo.svg           # Main logo (dark green/purple)
│   ├── logo-white.svg     # White logo for dark backgrounds
│   └── [placeholder images - see Image Guide below]
└── pages/
    ├── packages.html      # Party packages page
    ├── corporate.html     # Corporate events page
    ├── about.html         # About the company
    └── contact.html       # Contact form and info
```

---

## Technology Stack

- **Language:** HTML5, CSS3, JavaScript (ES6+)
- **Framework:** None (vanilla HTML/CSS/JS)
- **Styling:** Custom CSS with CSS Variables
- **Fonts:** Google Fonts (Playfair Display, Montserrat)
- **Store Integration:** Booqable (embedded via HTML)
- **Icons:** Inline SVG

---

## Color Scheme

The site uses a green and purple color palette defined as CSS variables in `css/styles.css`:

```css
/* Primary - Dark Green */
--color-green-dark: #1a4d3e;
--color-green-medium: #2d6a4f;
--color-green-light: #40916c;

/* Accent - Purple */
--color-purple-dark: #4a1259;
--color-purple-medium: #6b2d7b;
--color-purple-light: #8b4a9c;

/* Neutrals */
--color-white: #ffffff;
--color-black: #1a1a1a;
```

To change colors site-wide, edit these variables in `css/styles.css` (lines 5-25).

---

## Image & Video Guide

### Hero Video (Desktop)

The homepage hero section supports an MP4 video background on desktop:

| File Path | Recommended Specs | Used On |
|-----------|-------------------|---------|
| `images/hero-video.mp4` | 1920x1080px, 10-30 sec loop, <10MB | Homepage hero (desktop only) |

**Video Tips:**
- Keep video short (10-30 seconds) and seamlessly loopable
- Compress to keep file size under 10MB for fast loading
- Video auto-plays muted with loop enabled
- On mobile, the static image fallback is shown instead

### Required Images

Replace these placeholder images with actual photos:

| File Path | Recommended Size | Used On |
|-----------|------------------|---------|
| `images/hero-bg.webp` | 1920x1080px | Homepage hero poster/fallback |
| `images/hero-bg-mobile.webp` | 768x1024px | Homepage hero (mobile) |
| `images/category-tents.jpg` | 600x800px | Homepage categories |
| `images/category-tables.jpg` | 600x800px | Homepage categories |
| `images/category-lighting.jpg` | 600x800px | Homepage categories |
| `images/category-equipment.jpg` | 600x800px | Homepage categories |
| `images/package-intimate.jpg` | 800x500px | Packages page |
| `images/package-backyard.jpg` | 800x500px | Packages page |
| `images/package-elegant.jpg` | 800x500px | Packages page |
| `images/package-corporate.jpg` | 800x500px | Packages page |
| `images/package-grand.jpg` | 800x500px | Packages page |
| `images/package-basic.jpg` | 800x500px | Packages page |
| `images/about-team.jpg` | 800x600px | About page |
| `images/service-area.jpg` | 800x600px | About page |

### How to Replace Images

1. Save your new image with the exact filename listed above
2. Place it in the `images/` folder
3. Ensure the image is optimized for web (compress JPEGs to ~80% quality)
4. Refresh the page to see changes

### Image Optimization Tips

- Use JPEG for photos, PNG for graphics with transparency
- Compress images using tools like TinyPNG, Squoosh, or ImageOptim
- Keep file sizes under 200KB when possible
- Use consistent aspect ratios for grid layouts

---

## Booqable Store Integration

The site is configured to direct visitors to the contact page for rental inquiries. If you want to add a Booqable store embed in the future, you can create a new page or add it to an existing page.

**Example embed code:**
```html
<!-- Script embed method -->
<script src="https://yourstore.booqable.shop/embed.js"></script>
<div data-booqable-store></div>

<!-- OR iframe method -->
<iframe
  src="https://yourstore.booqable.shop"
  width="100%"
  height="800"
  frameborder="0"
  style="border: none; min-height: 800px;">
</iframe>
```

---

## Contact Form Setup

The contact form in `pages/contact.html` currently has client-side validation only. To make it functional:

### Option 1: Formspree (Easiest)
1. Sign up at https://formspree.io
2. Create a new form
3. Add `action="https://formspree.io/f/YOUR_FORM_ID" method="POST"` to the `<form>` tag

### Option 2: Netlify Forms
1. Host on Netlify
2. Add `data-netlify="true"` to the `<form>` tag

### Option 3: Custom Backend
1. Set up a server endpoint
2. Update `js/main.js` to POST form data to your endpoint

---

## Development Workflow

### Local Development

1. Clone the repository
2. Open a terminal in the project folder
3. Start a local server: `python -m http.server 8000`
4. Open `http://localhost:8000` in your browser
5. Edit files and refresh to see changes

### Making Changes

1. Edit HTML files directly for content changes
2. Edit `css/styles.css` for styling changes
3. Edit `js/main.js` for behavior changes
4. Test on multiple screen sizes (responsive design)

### Deployment

This is a static site and can be hosted on:
- **Netlify** - Drag and drop deployment
- **GitHub Pages** - Free hosting from repo
- **Vercel** - Easy deployment with CLI
- **Any web host** - Upload files via FTP

---

## Page-by-Page Guide

### index.html (Homepage)
- Hero section with background image
- "Why Choose Us" features grid
- Rental categories grid with hover effects
- Testimonials carousel
- CTA section

### pages/packages.html
- Package cards with pricing
- "Most Popular" badge on featured package
- Custom quote CTA

### pages/corporate.html
- Corporate event solutions overview
- Service categories with images
- Corporate advantages section
- Statistics and trust indicators

### pages/about.html
- Company story section
- Statistics grid
- Values cards
- Service area with map-ready section

### pages/contact.html
- Contact information sidebar
- Multi-field quote request form
- FAQ accordion section

---

## AI Assistant Guidelines

### When Working on This Codebase

1. **Maintain the color scheme** - Use the defined CSS variables
2. **Keep it responsive** - Test changes at mobile/tablet/desktop sizes
3. **Preserve the professional tone** - Upscale, elegant, trustworthy
4. **Use semantic HTML** - Proper headings, landmarks, alt text
5. **Comment significant changes** - Especially in CSS

### Things to Avoid

- Don't change the logo without explicit request
- Don't remove Booqable integration points
- Don't add JavaScript frameworks (keep it vanilla)
- Don't use external icon libraries (use inline SVG)
- Don't change the navigation structure without updating all pages

### Common Tasks

**Change phone number:**
- Search for `8582554766` and replace all instances

**Change email:**
- Search for `concierge@tastefulstudio.com` and replace

**Add a new page:**
1. Copy an existing page as a template
2. Update the nav links in all HTML files
3. Update footer links

**Change a color:**
- Edit the CSS variable in `css/styles.css` (top of file)

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Images not showing | Check file path and filename (case-sensitive) |
| Styles not updating | Hard refresh (Ctrl+Shift+R) or clear cache |
| Mobile menu not working | Ensure `js/main.js` is loaded |
| Form not submitting | Set up form backend (see Contact Form Setup) |
| Booqable not loading | Check embed code and Booqable account status |

---

## Changelog

| Date | Changes |
|------|---------|
| 2026-02-12 | Rebranded from "Tasteful Environments" to "Tasteful Studio" |
| 2026-02-12 | Updated contact info: concierge@tastefulstudio.com, (858) 255-4766 |
| 2026-01-29 | Complete website build: homepage, rentals, packages, about, contact |
| 2026-01-29 | Added professional SVG logo (green/purple) |
| 2026-01-29 | Booqable embed placeholder and documentation |
| 2026-01-27 | Initial CLAUDE.md created |

---

## File Quick Reference

For quick edits, here are the key line locations:

- **Colors:** `css/styles.css` lines 5-30
- **Mobile breakpoint:** `css/styles.css` line 768 (`@media`)
- **Navigation:** Each HTML file, `<header>` section
- **Footer:** Each HTML file, `<footer>` section
- **Phone number:** Search `8582554766`
- **Email:** Search `concierge@tastefulstudio.com`
