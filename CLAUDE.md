# CLAUDE.md - AI Assistant Guide for TER-revamp

> This file provides context and guidelines for AI assistants working with this codebase.
> Last updated: 2026-02-19

## Project Overview

**Repository:** TER-revamp
**Status:** Active Development
**Description:** Professional luxury event design website for Tasteful Studio, a San Diego-based company offering curated event environments, tent, table, chair, lighting, and event equipment rentals across Southern California (San Diego, Los Angeles, Palm Springs).

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
| `pages/` | All subpages (10 total) |
| `css/styles.css` | Main stylesheet (~1,280 lines) |
| `js/main.js` | JavaScript for interactivity (~266 lines) |
| `images/` | Logos (SVG) and product images (WebP) |
| `docs/` | Internal pricing guides and reference documents |
| `robots.txt` | Search engine crawling rules |
| `sitemap.xml` | Site structure for search engines (5 pages indexed) |

---

## Codebase Structure

```
TER-revamp/
├── CLAUDE.md                      # AI assistant guidelines
├── robots.txt                     # SEO crawling instructions
├── sitemap.xml                    # Site map (5 pages, priority-ranked)
├── index.html                     # Homepage
├── css/
│   └── styles.css                 # Main stylesheet (CSS variables, components, responsive)
├── js/
│   └── main.js                    # Mobile menu, form validation, scroll effects, FAQ accordion
├── images/
│   ├── logo.svg                   # Main logo (dark green/blue)
│   ├── logo-white.svg             # White logo for dark backgrounds
│   ├── hero-bg.webp               # Homepage hero background (~107 KB)
│   ├── category-tents.webp        # Homepage category card (~253 KB)
│   ├── category-tables.webp       # Homepage category card (~99 KB)
│   ├── category-lighting.webp     # Homepage category card (~50 KB)
│   ├── package-elegant.webp       # Package card image (~78 KB)
│   ├── package-estate.webp        # Package card image (~68 KB)
│   └── package-grand.webp         # Package card image (~125 KB)
├── pages/
│   ├── packages.html              # Signature environments/packages
│   ├── corporate.html             # Corporate events
│   ├── experiences.html           # Premium experiences & concierge services
│   ├── contact.html               # Contact form and info with FAQ
│   ├── about.html                 # About the company
│   ├── tent-rentals.html          # Tent rentals (SEO landing page)
│   ├── table-chair-rentals.html   # Table/chair rentals (SEO landing page)
│   ├── lighting-rentals.html      # Lighting rentals (SEO landing page)
│   ├── lounge-furniture-rentals.html  # Lounge furniture (SEO landing page)
│   └── wedding-rentals.html       # Wedding rentals (SEO landing page)
└── docs/
    ├── event-equipment-pricing-guide.html  # Print-friendly pricing reference
    ├── event-infrastructure-guide.html     # Infrastructure specifications
    ├── package-cost-analysis.tsv           # Tab-separated cost data
    └── package-pricing-sheets.csv          # CSV pricing data
```

---

## Technology Stack

- **Language:** HTML5, CSS3, JavaScript (ES6+)
- **Framework:** None (vanilla HTML/CSS/JS — no jQuery, no Bootstrap)
- **Styling:** Custom CSS with CSS Variables for theming
- **Fonts:** Google Fonts (Playfair Display for headings, Montserrat for body)
- **Images:** WebP format with lazy loading
- **Icons:** Inline SVG only (no icon libraries)
- **SEO:** Schema.org structured data, Open Graph, Twitter Cards
- **Store Integration:** Booqable (placeholder — not yet active)

---

## Color Scheme

The site uses a green and navy/blue color palette defined as CSS variables in `css/styles.css` (lines 8-30):

```css
/* Primary - Dark Green */
--color-green-dark: #1a4d3e;
--color-green-medium: #2d6a4f;
--color-green-light: #40916c;

/* Accent - Navy/Royal Blue */
--color-purple-dark: #1a2a5e;
--color-purple-medium: #2541b2;
--color-purple-light: #4169e1;

/* Neutrals */
--color-white: #ffffff;
--color-off-white: #f8f9fa;
--color-gray-light: #e9ecef;
--color-gray-medium: #6c757d;
--color-gray-dark: #343a40;
--color-black: #1a1a1a;
```

**Note:** The CSS variable names still say "purple" but the actual values are navy/blue. This is intentional — changing the variable names would require updating all references across the codebase.

Functional aliases for convenience:
```css
--color-primary: var(--color-green-dark);
--color-secondary: var(--color-purple-medium);
--color-accent: var(--color-purple-light);
```

To change colors site-wide, edit the CSS variables at the top of `css/styles.css`.

---

## Typography

```css
--font-primary: 'Playfair Display', Georgia, serif;     /* Headings */
--font-secondary: 'Montserrat', 'Segoe UI', sans-serif; /* Body text */
```

Heading sizes: h1 (3rem), h2 (2.25rem), h3 (1.75rem), h4 (1.25rem)
Base font size: 16px (reduces to 15px on mobile)

---

## Navigation Structure

Main navigation is consistent across all pages:

| Label | Target | Notes |
|-------|--------|-------|
| Home | `index.html` | |
| Environments | `pages/packages.html` | Signature package offerings |
| Corporate | `pages/corporate.html` | Corporate event solutions |
| Experiences | `pages/experiences.html` | Premium concierge services |
| Contact | `pages/contact.html` | Quote request form |

The "Request Consultation" CTA button in the header links to the contact page.

**Important:** When adding or renaming navigation items, update the `<header>` and `<footer>` sections in ALL HTML files (index.html + 10 pages in pages/).

---

## Image Assets

All product images use **WebP format** for performance. Total image payload: ~778 KB.

| File | Size | Used On |
|------|------|---------|
| `images/logo.svg` | 1.5 KB | Header (all pages) |
| `images/logo-white.svg` | 1.5 KB | Footer (all pages) |
| `images/hero-bg.webp` | ~107 KB | Homepage hero background |
| `images/category-tents.webp` | ~253 KB | Homepage categories grid |
| `images/category-tables.webp` | ~99 KB | Homepage categories grid |
| `images/category-lighting.webp` | ~50 KB | Homepage categories grid |
| `images/package-elegant.webp` | ~78 KB | Packages page |
| `images/package-estate.webp` | ~68 KB | Packages page |
| `images/package-grand.webp` | ~125 KB | Packages page |

### Image Best Practices

- Use **WebP** format for all photos (not JPEG/PNG)
- Keep file sizes under 200 KB when possible
- Add `loading="lazy"` for below-fold images
- Add `fetchpriority="high"` for hero/above-fold images
- Include `width` and `height` attributes to prevent layout shift
- Use consistent aspect ratios for grid layouts

---

## Page-by-Page Guide

### index.html (Homepage)
- Hero section with full-screen background image and CTAs
- "The Tasteful Studio Standard" — 3 feature cards (collections, execution, consultation)
- "Curated Collections" — 3 category cards with image hover effects
- Testimonials — 3 cards with Google Review badges
- Service area callout (Southern California regions)
- CTA section with gradient background

### pages/packages.html (Environments)
- 3 signature environment packages: Elegant Reception, Grand Celebration (featured), Estate Affair
- Each card: image, guest count, description, includes list, CTA
- Venue-specific customization section (Rancho Valencia, Hotel del Coronado, etc.)
- Event infrastructure breakdown (standard vs. optional)

### pages/corporate.html (Corporate Events)
- 3 corporate service categories: Brand Activations, Conferences, Company Celebrations
- 4-column solutions grid: Climate, Seating, Lighting, Stage
- 3 corporate packages: Executive Session, Corporate Showcase, Grand Gala
- Trust statistics: 500+ events, 100+ clients, 15+ years
- Infrastructure section

### pages/experiences.html (Premium Experiences)
- 3 experience cards: Full-Service Planning, Personal Concierge, Custom Design
- 4-step process section
- Concierge services details
- Styling & design services

### pages/about.html (About Us)
- Company story with image
- Statistics: 1000+ events, 10+ years, 500+ reviews, 100% satisfaction
- Values cards: Quality, Customer Focus, Reliability, Integrity
- Service area checklist

### pages/contact.html (Contact)
- Contact info sidebar (phone, email, hours, social links)
- 9-field quote request form with client-side validation
- FAQ accordion section

### SEO Landing Pages (5 pages)
These pages target specific rental search queries:
- `pages/tent-rentals.html`
- `pages/table-chair-rentals.html`
- `pages/lighting-rentals.html`
- `pages/lounge-furniture-rentals.html`
- `pages/wedding-rentals.html`

Each follows the same pattern: hero, feature cards, rental details, infrastructure, CTA. They include Schema.org Product structured data.

---

## JavaScript Functionality (js/main.js)

The JS file initializes 6 modules on `DOMContentLoaded`:

| Function | Purpose |
|----------|---------|
| `initMobileMenu()` | Hamburger menu toggle with CSS transform animation |
| `initStickyHeader()` | Adds `.scrolled` class to header after 50px scroll |
| `initSmoothScroll()` | Smooth anchor link scrolling with header offset |
| `initScrollAnimations()` | IntersectionObserver-based fade-in animations |
| `initContactForm()` | Form validation, error states, simulated submit |
| `initFaqAccordion()` | Collapsible FAQ items (one open at a time) |

### Contact Form Details
- **Validation:** Client-side only (required fields, email regex)
- **Submit behavior:** Shows "Sending..." state, then "Message Sent!" after 1 second (simulated)
- **Error handling:** Red border/shadow on invalid fields, clears on input
- **Backend:** Not connected — form requires backend integration (see Contact Form Setup below)

### Active Nav Highlighting
- `setActiveNavLink()` compares `window.location.pathname` to nav link hrefs and adds `.active` class

---

## CSS Architecture (css/styles.css)

### Major Sections

| Lines (approx.) | Section |
|-----------------|---------|
| 7-58 | CSS Variables (colors, fonts, spacing, shadows) |
| 60-80 | Accessibility (skip link) |
| 82-137 | Reset & base styles |
| 150-257 | Header & navigation |
| 261-326 | Button components |
| 328-398 | Hero section |
| 400-438 | Section layout components |
| 440-488 | Features grid |
| 490-565 | Categories grid with image overlays |
| 567-644 | Testimonials |
| 646-666 | CTA section |
| 774-818 | Contact page (form + info grid) |
| 864-952 | Footer |
| 954-1148 | Responsive breakpoints |
| 1150-1192 | Utility classes |
| 1193-1280 | FAQ accordion |

### Responsive Breakpoints

| Breakpoint | Target | Key Changes |
|-----------|--------|-------------|
| `1024px` | Tablets | Footer to 2 columns, about-content to 1 column |
| `768px` | Mobile | Single-column grids, mobile menu visible, font-size to 15px |
| `480px` | Small phones | Hero title 1.75rem, full-width stacked buttons |

### Animations

- `@keyframes fadeInUp` — opacity 0→1, translateY 30px→0 (0.6s)
- Category card hover: image scale(1.1) over 0.6s
- Feature card hover: translateY(-8px)
- FAQ accordion: max-height transition (0.4s ease)
- Button hover: box-shadow transition (0.3s)

---

## SEO & Performance

### Structured Data
- **Homepage:** Schema.org `EventPlanningService` with contact, hours, service areas
- **Rental pages:** Schema.org `Product` with pricing and descriptions

### Meta Tags (all pages)
- Open Graph (og:title, og:description, og:image, og:url)
- Twitter Cards (twitter:card, twitter:title, twitter:description)
- Viewport meta for responsive
- Favicon using logo.svg

### Performance Optimizations
- WebP images (smaller than JPEG)
- `loading="lazy"` on below-fold images
- `fetchpriority="high"` on hero image
- `width`/`height` attributes on images (prevents CLS)
- CSS variables for efficient theming
- No external JS libraries

### Accessibility
- Skip-to-main-content link
- Semantic HTML5 elements (header, nav, main, section, footer)
- Alt text on all images
- ARIA labels on interactive elements (mobile menu toggle)
- Form labels properly associated with inputs
- Focus states on interactive elements

---

## Contact Information

| Field | Value | Search String |
|-------|-------|---------------|
| Phone | (858) 255-4766 | `8582554766` |
| Email | concierge@tastefulstudio.com | `concierge@tastefulstudio.com` |
| Location | San Diego, CA | |
| Service Areas | San Diego, Los Angeles, Palm Springs | |

### Business Hours
- Monday-Friday: 9am - 6pm
- Saturday: 10am - 4pm
- Sunday: By appointment

---

## Known Issues

| Issue | Location | Details |
|-------|----------|---------|
| Outdated contact info | `pages/about.html` | Still shows old phone (858) 255-1130 and email info@tastefuleventrentals.com |
| Brand name inconsistency | `pages/about.html` | Uses "Tasteful Environments" instead of "Tasteful Studio" |
| Social links placeholder | Footer (all pages) | Social media links point to `#` (not real URLs) |
| Form not connected | `pages/contact.html` | Contact form has client-side validation only, no backend |
| Sitemap incomplete | `sitemap.xml` | Only lists 5 pages; missing rental landing pages |

---

## Contact Form Setup

The contact form in `pages/contact.html` has client-side validation only. To make it functional:

### Option 1: Formspree (Easiest)
1. Sign up at formspree.io
2. Create a new form
3. Add `action="https://formspree.io/f/YOUR_FORM_ID" method="POST"` to the `<form>` tag

### Option 2: Netlify Forms
1. Host on Netlify
2. Add `data-netlify="true"` to the `<form>` tag

### Option 3: Custom Backend
1. Set up a server endpoint
2. Update `js/main.js` to POST form data to your endpoint

---

## Booqable Store Integration

The site is designed to direct visitors to the contact page for rental inquiries. Booqable integration is planned but not yet active.

**Example embed code (for future use):**
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

## Internal Documentation (docs/)

The `docs/` directory contains internal pricing and reference materials. These are not linked from the public site.

| File | Purpose |
|------|---------|
| `event-equipment-pricing-guide.html` | Print-friendly HTML pricing tables |
| `event-infrastructure-guide.html` | Infrastructure specs by venue type |
| `package-cost-analysis.tsv` | Tab-separated cost data for spreadsheets |
| `package-pricing-sheets.csv` | CSV pricing data |

---

## AI Assistant Guidelines

### When Working on This Codebase

1. **Use CSS variables** — All colors, fonts, spacing, and shadows are defined as variables. Never hardcode values that already have a variable.
2. **Keep it responsive** — Test changes at 1024px, 768px, and 480px breakpoints.
3. **Preserve the professional tone** — Upscale, elegant, trustworthy luxury brand voice.
4. **Use semantic HTML** — Proper headings hierarchy, landmarks, alt text, ARIA labels.
5. **Maintain consistency across pages** — Header and footer are duplicated in every HTML file. Changes must be applied to all 11 files.
6. **Use WebP for images** — Not JPEG or PNG. Include lazy loading and dimensions.
7. **No frameworks** — Keep everything vanilla HTML/CSS/JS. No jQuery, React, Bootstrap, Tailwind, etc.

### Things to Avoid

- Don't change the logo without explicit request
- Don't add JavaScript frameworks or CSS libraries
- Don't use external icon libraries (use inline SVG)
- Don't change the navigation structure without updating ALL 11 HTML files
- Don't reference old brand name "Tasteful Environments" in new content
- Don't use JPEG/PNG for new images (use WebP)
- Don't remove Schema.org structured data
- Don't remove accessibility features (skip link, ARIA labels, alt text)

### Common Tasks

**Change phone number:**
- Search for `8582554766` and replace in all files (~10 occurrences)

**Change email:**
- Search for `concierge@tastefulstudio.com` and replace in all files (~6 occurrences)

**Add a new page:**
1. Copy an existing page as a template
2. Update the nav links in ALL 11 HTML files (index.html + 10 pages)
3. Update footer links in all files
4. Add to `sitemap.xml`

**Change a color:**
- Edit the CSS variable in `css/styles.css` (lines 8-30)
- All components reference these variables, so the change cascades automatically

**Add a new image:**
- Convert to WebP format
- Place in `images/` directory
- Add `loading="lazy"` and `width`/`height` attributes in HTML
- Keep file size under 200 KB

---

## Deployment

This is a static site (no build step required) and can be hosted on:
- **Netlify** — Drag and drop deployment
- **GitHub Pages** — Free hosting from repo
- **Vercel** — Easy deployment with CLI
- **Any web host** — Upload files via FTP/SFTP

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Images not showing | Check file path and filename (case-sensitive). Images are .webp, not .jpg |
| Styles not updating | Hard refresh (Ctrl+Shift+R) or clear browser cache |
| Mobile menu not working | Ensure `js/main.js` is loaded and no JS errors in console |
| Form not submitting | Form needs a backend (see Contact Form Setup above) |
| Colors look wrong | Check CSS variables at top of `css/styles.css` — they cascade everywhere |
| Page not in sitemap | Add entry to `sitemap.xml` manually |
| Nav link not highlighting | Check `setActiveNavLink()` in `js/main.js` — compares pathname to hrefs |

---

## Changelog

| Date | Changes |
|------|---------|
| 2026-02-19 | Updated CLAUDE.md with comprehensive codebase documentation |
| 2026-02-12 | Pricing: update package cost analysis with new unit costs |
| 2026-02-12 | Branding: update logo with lowercase italic "studio" |
| 2026-02-12 | Images: convert all references from .jpg to .webp |
| 2026-02-12 | Mobile: fix horizontal overflow and responsive grids |
| 2026-02-12 | Perf/SEO/A11y: implement Lighthouse optimizations |
| 2026-02-12 | Branding: revert to original shield logo with Tasteful Studio text |
| 2026-02-12 | Rebranded from "Tasteful Environments" to "Tasteful Studio" |
| 2026-02-12 | Updated contact info: concierge@tastefulstudio.com, (858) 255-4766 |
| 2026-01-29 | Complete website build: homepage, packages, corporate, experiences, about, contact |
| 2026-01-29 | Added SEO landing pages: tent, table/chair, lighting, lounge, wedding rentals |
| 2026-01-29 | Added professional SVG logo (green/purple) |
| 2026-01-29 | Booqable embed placeholder and documentation |
| 2026-01-27 | Initial CLAUDE.md created |

---

## File Quick Reference

For quick edits, here are the key locations:

- **Colors:** `css/styles.css` lines 8-30
- **Typography:** `css/styles.css` lines 32-40
- **Spacing/shadows:** `css/styles.css` lines 42-58
- **Responsive 1024px:** `css/styles.css` ~line 954
- **Responsive 768px:** `css/styles.css` ~line 980
- **Responsive 480px:** `css/styles.css` ~line 1100
- **FAQ styles:** `css/styles.css` ~line 1193
- **Navigation:** Each HTML file, `<header>` section
- **Footer:** Each HTML file, `<footer>` section
- **Phone number:** Search `8582554766`
- **Email:** Search `concierge@tastefulstudio.com`
- **JS initialization:** `js/main.js` lines 6-14
- **Form validation:** `js/main.js` lines 124-195
- **FAQ accordion:** `js/main.js` lines 229-262
