# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

> **Current Spec Version:** `prompt v3.md` — Always use this as the source of truth for implementation details.

## Project Overview

This is the Rentify website (2026 version) — a responsive marketing website for a UAE-based rental platform that enables monthly rent payments, online rental agreements, and rewards programs. The website serves both tenants and landlords with custom user journeys.

## Design Philosophy

**"Editorial Fintech"** — The website bridges trustworthy fintech aesthetics with bold editorial design. It must maintain brand consistency with the Rentify mobile app while being more expressive for marketing purposes.

### Key Design Principles

- Bold, asymmetric compositions with overlapping elements
- Card-based layouts with generous rounded corners (20-30px)
- Vibrant color blocking (#10BC7D primary, #4BE7A3 accents)
- Oversized headlines as compositional anchors
- Text overlaid on photography
- Cut-out subjects on solid color fields
- Playful decorative elements (dots, icons, geometric patterns)
- Wave dividers between sections

## Brand System

### Typography
- **Headlines**: Rubik Extrabold (800) — never substitute
- **Body text**: Plus Jakarta Sans Regular (400)
- **UI/Labels**: Plus Jakarta Sans Extrabold (800)
- Import: `@import url('https://fonts.googleapis.com/css2?family=Rubik:wght@400;700;800&family=Plus+Jakarta+Sans:wght@400;600;800&display=swap');`

### Colors (NEVER deviate)
```css
--color-primary: #10BC7D;        /* CTAs, success, checkmarks */
--color-primary-light: #4BE7A3;  /* Large backgrounds, hover states */
--color-dark: #030712;           /* Headlines, primary text */
--color-gray: #6B7280;           /* Secondary text, borders */
--color-light: #F3F4F6;          /* Card backgrounds */
--color-white: #FFFFFF;          /* Page background */
```

### Critical Brand Rules
- Primary CTA: Pill-shaped, #4BE7A3 background, #030712 text
- Secondary CTA: Outlined, #030712 border, transparent background
- Button radius: Fully rounded (pill shape, 100px+ radius)
- Card radius: Minimum 16-24px
- **ALWAYS** use #030712 text on green backgrounds — never white (accessibility requirement)
- Icons: Solar style (outlined, rounded, elegant) — 1px stroke @ 16px, 1.5px stroke @ 24px
- Illustrations: Milano style (sketchy black outlines + green accents, maximum 2 colors)

## Implementation Architecture

### Single-File Structure
The website is designed as a **single HTML file** with embedded CSS and JavaScript:

- Mobile-first responsive CSS with fluid typography using `clamp()`
- CSS custom properties for all design tokens
- Flexbox and CSS Grid for layouts
- JavaScript for:
  - Mobile menu toggle (hamburger navigation)
  - **Custom Path interactive journey selector** (show/hide content based on Tenant/Landlord selection)
  - Scroll animations (fade-in-up for content blocks)
  - Smooth scroll for anchor links

### Responsive Breakpoints
- Mobile: 375px – 767px
- Tablet: 768px – 1023px
- Desktop: 1024px – 1280px (max container width: 1280px)

### Fluid Spacing
```css
--space-section: clamp(4rem, 10vw, 8rem);      /* Between major sections */
--space-block: clamp(2rem, 5vw, 4rem);         /* Between content blocks */
--space-element: clamp(1rem, 2vw, 1.5rem);     /* Between elements */
--container-padding: clamp(1.5rem, 5vw, 4rem); /* Side margins */
```

### Fluid Typography
```css
--text-display: clamp(2.5rem, 8vw, 5rem);      /* 40px → 80px */
--text-h1: clamp(2rem, 5vw, 3.5rem);           /* 32px → 56px */
--text-h2: clamp(1.5rem, 4vw, 2.5rem);         /* 24px → 40px */
--text-h3: clamp(1.25rem, 3vw, 1.75rem);       /* 20px → 28px */
--text-body: clamp(1rem, 2vw, 1.125rem);       /* 16px → 18px */
--text-small: clamp(0.875rem, 1.5vw, 1rem);    /* 14px → 16px */
--text-label: clamp(0.75rem, 1.2vw, 0.875rem); /* 12px → 14px */
```

## Content Structure

The complete website content specification is in `prompt v2.md`. All copy must be included verbatim.

### Primary Sections (in order)
1. **Global Nav** — Sticky nav with Home, How it Works, Rewards, Why, Help
2. **Hero** — "Rent the Simple Way" with highlights and app screenshots
3. **Rentify Pay** — Product explanation with Rentify Pay logo
4. **Custom Path** — Interactive journey selector (Tenant/Landlord)
   - Tenant paths: New apartment, migrate existing, convert cheques
   - Landlord path: Upfront payment explanation
5. **Rewards** — "Rewards That Add Up" with redemption details
6. **Trust Centre** — Security, compliance, insurance
7. **Partners** — Banking partners and ecosystem benefits
8. **About** — Founder story with office photo
9. **Help** — Reni assistant, WhatsApp, Email
10. **Download App** — iOS/Android download CTA
11. **Footer** — Enhanced nav with social links

### Logo Usage
- Dark backgrounds: Use `assets/logo-on-dark.svg`
- Light backgrounds: Use `assets/logo-on-light.svg`
- Rentify Pay sections: Use `assets/rentify-pay-logo.svg`
- All logo files are in the `assets/` directory

## Asset Handling & Implementation Details

### Device Mockups
Create **iPhone 17** device frames with white screens as placeholders throughout the site:
- Use CSS or SVG to create the device frame
- Inner screen should be pure white (#FFFFFF)
- Client will provide final app screenshots later
- Used in: Hero (3 devices), Rentify Pay, all Custom Path steps, Rewards, Download App sections

### Logo Placeholders
For Trust Centre (2 logos) and Partners (3 logos) sections:
- Create light gray ellipses: `background: #E5E7EB`
- Add subtle border: `border: 1px solid #D1D5DB`
- Center the text "Logo" using `--color-gray` (#6B7280)
- Keep proportions appropriate for brand logos (roughly 120px × 40px)

### Reni Avatar
Use `assets/reni-avatar.png` in the Help section for the "Ask Reni" virtual assistant feature.

### Real Photography
Source actual images from **Pexels, Unsplash, or Pixabay** and use their URLs directly:
- Choose images showing young professionals, families, modern apartments
- Represent diverse, authentic UAE rental market demographic
- Clean, contemporary aesthetic aligned with brand
- Use direct URLs (no local storage needed)
- Ensure proper attribution if required by license

**Example sections needing photography:**
- Hero section (people using app, happy tenants/landlords)
- About section (team/founders in office setting)
- Feature sections (lifestyle imagery)

### Links & CTAs

**"Start Now" Buttons:**
- Link to `#download-app` (anchor link to Download App section)

**Social Media:**
- Instagram: `https://instagram.com`
- LinkedIn: `https://linkedin.com`
- X: `https://x.com`

**Download Buttons:**
- App Store: `href=""` (empty, client will provide later)
- Google Play: `href=""` (empty, client will provide later)

**Contact:**
- WhatsApp: `href="https://wa.me/"` (empty phone number for now)
- Email: `href="mailto:support@rentify.ae"`

### Interactive Custom Path Section
The Custom Path section requires JavaScript interactivity:

1. **Initial Selection:** Tenant vs. Landlord (radio button style)
2. **Conditional Content:** Show/hide different journey paths based on selection
3. **All paths present in HTML:** Toggle visibility with CSS classes controlled by JavaScript
4. **Tenant sub-paths:** New apartment, migrate existing, or convert cheques
5. **Implementation approach:**
   - Use `data-path` attributes on content sections
   - JavaScript toggles `.active` or `.visible` classes
   - CSS handles the show/hide transitions
   - Ensure smooth transitions and proper ARIA states for accessibility

## Accessibility Requirements (WCAG AA)

### Mandatory Rules
- One `<h1>` per page, semantic heading hierarchy (h1 → h2 → h3)
- All images need descriptive `alt` text or `alt=""` + `aria-hidden="true"` for decorative
- Every form input needs visible `<label>`
- Touch targets: minimum 44×44px
- Focus states: 3px solid outline with 3px offset — never remove
- Layout must not break at 200% zoom

### Contrast Requirements
- #030712 on #FFFFFF: 19.5:1 ✅ Excellent
- #030712 on #4BE7A3: 7.2:1 ✅ Good (large text)
- #FFFFFF on #10BC7D: 2.9:1 ⚠️ Large text/icons only

**Critical**: Always use #030712 (dark) text on green backgrounds.

## Motion & Interaction

```css
--ease-out: cubic-bezier(0.33, 1, 0.68, 1);
--ease-in-out: cubic-bezier(0.65, 0, 0.35, 1);
--duration-fast: 150ms;
--duration-normal: 250ms;
--duration-slow: 400ms;
```

- Button hover: `translateY(-2px)` with green shadow
- Scroll animations: Subtle fade-in-up for content blocks
- Keep animations professional — not playful or bouncy

## Reference Assets

- **benchs/** directory contains visual references:
  - `ref-main.png` — Primary design inspiration
  - `ref-1` through `ref-10` — Layout and typography references
  - `app-sample-*.png` — Existing mobile app screens for brand consistency
- **Image sourcing**: Use Pexels, Unsplash, or Pixabay for real people photography

## Anti-Patterns (NEVER DO)

### Visual
- Purple gradients or any gradient backgrounds
- Generic stock photos (handshakes, pointing at screens)
- Thin or light headline font weights
- Sharp corners on cards (minimum 16px radius)
- White text on green backgrounds
- Perfectly centered/symmetrical layouts everywhere
- Using fonts other than Rubik and Plus Jakarta Sans
- Using green colors other than #10BC7D or #4BE7A3

### Technical
- Fixed pixel font sizes (use clamp())
- Layouts breaking below 375px
- Touch targets smaller than 44×44px
- Removing focus outlines
- Images without alt attributes
- Placeholder-only form fields
- Multiple HTML files (this is a single-file project)

### Brand
- Colorful multi-hued illustrations (Milano style: black + green only, max 2 colors)
- Square or sharp-cornered CTA buttons (must be pill-shaped)
- Generic icon sets (use Solar-style outlined icons)

## Working with This Project

### Making Changes
1. The primary design specification is in **`prompt v3.md`** — treat as source of truth
2. When creating/editing the HTML file, ensure all content from `prompt v3.md` is included verbatim
3. Use fluid responsive units (clamp, rem, vw) — never fixed pixels
4. Test at all three breakpoints: 375px, 768px, 1280px
5. Verify color contrast and accessibility before completing work
6. Implement Custom Path interactivity with JavaScript (not optional)

### Content Updates
- All marketing copy lives in `prompt v3.md` (Content Structure & Copy section)
- Comments in copy (//Comment:) are instructions, not content to display
- Never modify or "improve" the provided copy — use exactly as written

### Asset Management
- **Local assets:** Logo files and Reni avatar are in `assets/` directory
- **External images:** Use direct URLs from Pexels, Unsplash, or Pixabay
- **Device mockups:** Create iPhone 17 frames with CSS/SVG (white screens)
- **Logo placeholders:** Gray ellipses with "Logo" text for partner logos

### Design Validation Checklist
Before considering work complete:
- All text passes WCAG AA contrast
- All interactive elements have visible focus states
- Typography uses only Rubik and Plus Jakarta Sans
- Primary CTAs use #4BE7A3 background with #030712 text
- At least one asymmetric/overlapping element per major section
- Semantic HTML with proper heading hierarchy
- All copy from `prompt v3.md` is included
- Buttons are pill-shaped (100px+ border-radius)
- Touch targets minimum 44×44px
- **Custom Path section is fully interactive with JavaScript**
- iPhone 17 device mockups with white screens throughout
- Real photography from Pexels/Unsplash/Pixabay with URLs
- Reni avatar (assets/reni-avatar.png) used in Help section
- Logo files from assets/ directory used correctly
- Partner logo placeholders (gray ellipses) in Trust Centre and Partners
- All "Start Now" buttons link to #download-app
- Social media links point to respective platforms
- Contact links (WhatsApp, email) are properly formatted

## Brand Continuity: App-to-Web

The website must feel like the **same product family** as the mobile app. Reference the app screenshots in `benchs/app-sample-*.png` to maintain visual consistency.

### Must Stay Consistent
- Button styles (pill-shaped CTAs)
- Color palette (no additional colors)
- Typography system (Rubik + Plus Jakarta Sans)
- Illustration style (Milano: sketchy black + green)
- Icon style (Solar: outlined, rounded)
- Card backgrounds and shadows

### Can Be More Expressive
- Larger, bolder headline sizes
- Asymmetric layouts and overlapping elements
- Cut-out photography
- Decorative geometric shapes
- More dramatic use of #4BE7A3 for large backgrounds
- Wave dividers and organic shapes
- Text overlapping images
- Floating badges and grid-breaking elements

## JavaScript Requirements

The website requires JavaScript for core functionality (not optional):

1. **Mobile Navigation:** Hamburger menu toggle for mobile/tablet
2. **Custom Path Journey Selector:** Interactive Tenant/Landlord path selection
   - Toggle between Tenant and Landlord views
   - Show/hide different sub-paths based on user selection
   - Smooth transitions between content states
3. **Scroll Animations:** Fade-in-up effects for content blocks entering viewport
4. **Smooth Scrolling:** Anchor link navigation (e.g., "Start Now" → #download-app)

**Implementation Notes:**
- Keep JavaScript minimal and performant
- Use vanilla JS (no frameworks required)
- Ensure proper ARIA states for accessibility
- Add `.no-js` fallback class for graceful degradation
