# Rentify Website Design Prompt (v3)

## Overview

Rentify is a platform that transforms rental in the UAE by offering a platform that facilitates rental management. Create a responsive home page that works across devices from mobile (375px) to desktop (1280px). This is a professional, clean, stunning website design that balances the bold, editorial aesthetic of contemporary web design with the trustworthy, clean feel of the existing Rentify mobile app.

The website must include:

- Global navigation with links to: Home, For Tenants, For Landlords, About, and Contact
- Footer with logo, navigation links, and social media (Instagram, LinkedIn, X)
- Images of real people throughout the page (sourced from Pexels, Unsplash, or Pixabay)
- All copy provided in the Content section (must be included verbatim)

---

## Design Direction

### Conceptual Position

**"Editorial Fintech"** — The confident clarity of a banking app meets the visual energy of a lifestyle magazine. Trustworthy but not boring. Bold but not chaotic.

### Core Aesthetic Principles

**Layout Architecture:**

- Bold, asymmetric compositions with deliberate imbalance
- Card-based modular system with generous rounded corners (20-30px radius)
- Overlapping layers creating depth — text over images, shapes intersecting
- Strong geometric foundations (circles, rectangles, organic curves) as framing devices
- Floating elements that break rigid grid systems

**Color & Space:**

- Vibrant, saturated color blocking
- High contrast between bold color fields and white/light backgrounds
- Negative space as an active design element, not just emptiness
- Single bold colors per section/card rather than gradients

**Typography as Structure:**

- Oversized headlines as primary compositional anchors
- Text overlaid directly on photography, becoming part of the image
- Type size creating hierarchy through extreme scale contrast

**Image Treatment:**

- Photography with cut-out subjects placed on solid color fields
- Images cropped by geometric shapes (circles, organic blobs, rounded rectangles)
- Real photos mixed with graphic elements (icons, illustrations, abstract shapes)

**Graphic Devices:**

- Playful decorative elements (dots, small icons, geometric patterns) scattered as accents
- Curved wave dividers between sections
- Thin lines creating frames or separating space

**Overall Vibe:**
Contemporary editorial meets social media aesthetic — confident, energetic, Gen Z-optimized, playful but credible. Instagram-story-meets-magazine-spread.

---

## Brand Guidelines

### Logo

Three logo versions available in the `assets/` directory:

- **Dark backgrounds**: `assets/logo-on-dark.svg`
- **Light backgrounds**: `assets/logo-on-light.svg`
- **Sub-brand (Rentify Pay)**: `assets/rentify-pay-logo.svg` — use whenever Rentify Pay is mentioned

### Typography

**Font Families:**

```css
/* Import from Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Rubik:wght@400;700;800&family=Plus+Jakarta+Sans:wght@400;600;800&display=swap');
```

- **Headlines and display text**: Rubik Extrabold (800)
- **Body text**: Plus Jakarta Sans Regular (400)
- **UI elements and labels**: Plus Jakarta Sans Extrabold (800)

**Typography Scale (Fluid):**

```css
:root {
  --text-display: clamp(2.5rem, 8vw, 5rem);      /* 40px → 80px */
  --text-h1: clamp(2rem, 5vw, 3.5rem);           /* 32px → 56px */
  --text-h2: clamp(1.5rem, 4vw, 2.5rem);         /* 24px → 40px */
  --text-h3: clamp(1.25rem, 3vw, 1.75rem);       /* 20px → 28px */
  --text-body: clamp(1rem, 2vw, 1.125rem);       /* 16px → 18px */
  --text-small: clamp(0.875rem, 1.5vw, 1rem);    /* 14px → 16px */
  --text-label: clamp(0.75rem, 1.2vw, 0.875rem); /* 12px → 14px */
}
```

### Colors

```css
:root {
  /* Brand Colors */
  --color-primary: #10BC7D;        /* CTAs, active states, success, checkmarks */
  --color-primary-light: #4BE7A3;  /* Large backgrounds, hover states, accents, button backgrounds */
  --color-dark: #030712;           /* Headlines, primary text, illustrations */
  --color-gray: #6B7280;           /* Secondary text, borders, captions */
  --color-light: #F3F4F6;          /* Card backgrounds, section backgrounds */
  --color-white: #FFFFFF;          /* Page background, card surfaces */

  /* Shadows */
  --shadow-card: 0 4px 24px rgba(3, 7, 18, 0.08);
  --shadow-elevated: 0 8px 32px rgba(3, 7, 18, 0.12);
  --shadow-subtle: 0 2px 8px rgba(3, 7, 18, 0.06);
}
```

### Icons

Streamline's Solar icon set style — outlined, rounded, and elegant. If 16px, 1px stroke weight; If 20px, 1.25. If 24px, 1.5px; and so on.

### Illustrations

Streamline's Milano Library style:

- High-contrast, sketchy, hand-drawn aesthetic
- Black outlines (#030712) with single green accent (#10BC7D)
- **Maximum two colors per illustration**
- Rounded, friendly, approachable feel

---

## Brand Continuity: App-to-Web Bridge

The website must feel like the **same product family** as the mobile app while being more expressive for marketing purposes.

### MUST Stay Consistent with App:

| Element                 | Specification                                         |
| ----------------------- | ----------------------------------------------------- |
| Primary CTA             | Pill-shaped, #4BE7A3 background, #030712 text         |
| Secondary CTA           | Outlined, #030712 border, transparent background      |
| Success/checkmark color | #10BC7D only                                          |
| Illustration style      | Sketchy black outlines + green accents (Milano style) |
| Typography              | Rubik + Plus Jakarta Sans — no substitutions          |
| Icon style              | Outlined, rounded, elegant                            |
| Card backgrounds        | White or #F3F4F6 with subtle shadows                  |
| Button radius           | Fully rounded (pill shape, 100px+ radius)             |

### CAN Be More Expressive on Website:

- Larger, bolder headline sizes
- Asymmetric layouts and overlapping elements
- Cut-out photography with people
- Decorative geometric shapes and blob backgrounds
- More dramatic use of #4BE7A3 for large color blocks
- Wave dividers and organic shapes between sections
- Text overlapping images
- Floating badges and breaking-grid elements

---

## Responsive Design Requirements

### Breakpoints

- **Mobile**: 375px – 767px
- **Tablet**: 768px – 1023px
- **Desktop**: 1024px – 1280px

### Fluid Spacing System

```css
:root {
  --space-section: clamp(4rem, 10vw, 8rem);      /* Between major sections */
  --space-block: clamp(2rem, 5vw, 4rem);         /* Between content blocks */
  --space-element: clamp(1rem, 2vw, 1.5rem);     /* Between elements */
  --container-padding: clamp(1.5rem, 5vw, 4rem); /* Side margins */
  --container-max: 1280px;                        /* Max content width */
}
```

### Layout Behavior by Breakpoint

**Navigation:**

- Mobile (375-767px): Hamburger menu, logo left-aligned
- Tablet (768-1023px): Full horizontal nav
- Desktop (1024-1280px): Full horizontal nav with comfortable spacing

**Hero Section:**

- Mobile: Stack vertically — headline, subhead, CTA, then image below
- Tablet: Side-by-side asymmetric (60/40 split)
- Desktop: More dramatic asymmetry, larger cut-out image, overlapping text

**Feature Cards:**

- Mobile: Single column, full-width cards
- Tablet: 2-column grid
- Desktop: 2-3 column grid with featured/larger cards

**Content Sections:**

- Mobile: Single column, simplified decorative elements
- Tablet: Two-column layouts where appropriate
- Desktop: Full asymmetric compositions with all decorative elements

### Touch & Click Targets

- All interactive elements: minimum 44×44px
- Buttons: minimum height 48px on mobile, 52px on tablet+
- Minimum 8px gap between adjacent tappable elements

---

## Motion & Interaction

```css
:root {
  --ease-out: cubic-bezier(0.33, 1, 0.68, 1);
  --ease-in-out: cubic-bezier(0.65, 0, 0.35, 1);
  --duration-fast: 150ms;
  --duration-normal: 250ms;
  --duration-slow: 400ms;
}
```

### Button Interactions

```css
.btn-primary {
  transition: transform var(--duration-fast) var(--ease-out),
              box-shadow var(--duration-fast) var(--ease-out);
}
.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(16, 188, 125, 0.3);
}
```

### Scroll Animations

- Subtle fade-in-up for content blocks as they enter viewport
- Staggered reveals for card groups
- Keep animations fast and professional — not playful or bouncy

---

## Accessibility Requirements

### Color Contrast (WCAG AA Compliance)

| Combination        | Ratio  | Status                   |
| ------------------ | ------ | ------------------------ |
| #030712 on #FFFFFF | 19.5:1 | ✅ Excellent             |
| #030712 on #F3F4F6 | 15.1:1 | ✅ Excellent             |
| #030712 on #4BE7A3 | 7.2:1  | ✅ Good (large text)     |
| #030712 on #10BC7D | 6.5:1  | ✅ Good                  |
| #FFFFFF on #10BC7D | 2.9:1  | ⚠️ Large text/icons only |

**Rule**: Always use #030712 (dark) text on green backgrounds, never white.

### Focus States

```css
:focus-visible {
  outline: 3px solid var(--color-primary);
  outline-offset: 3px;
  border-radius: 4px;
}
/* Never remove focus outlines — enhance them */
```

### Semantic HTML Structure

```html
<header role="banner">
  <nav aria-label="Main navigation">...</nav>
</header>
<main>
  <section aria-labelledby="hero-heading">
    <h1 id="hero-heading">...</h1>
  </section>
  <section aria-labelledby="tenants-heading">
    <h2 id="tenants-heading">...</h2>
  </section>
</main>
<footer role="contentinfo">...</footer>
```

### Heading Hierarchy

- One `<h1>` per page (hero headline)
- `<h2>` for major section titles
- `<h3>` for subsections within
- Never skip heading levels

### Images

- Meaningful images: Descriptive alt text
- Decorative images: `alt=""` and `aria-hidden="true"`
- Icons with meaning: Include accessible label or `aria-label`

### Forms

- Every input has a visible, associated `<label>`
- Clear error messages with `aria-describedby`
- No placeholder-only fields

### Text Resizing

- Use relative units (rem, em, clamp)
- Layout must not break at 200% zoom

---

## Image Assets & Implementation Details

### Real Photography
Source actual images from **Pexels, Unsplash, or Pixabay** and use their URLs directly. Choose images that show:
- Young professionals and families (UAE rental market demographic)
- Modern apartments and lifestyle settings
- Diverse, authentic representations of people
- Clean, contemporary aesthetic aligned with the brand

### Device Mockups
Create iPhone 17 device frames with **white screens** as placeholders. The client will provide final app screenshots later. Use CSS to create the device frame or SVG for the phone outline.

### Logo Placeholders
For Trust Centre and Partners sections where logos are needed:
- Create light gray ellipses (`background: #E5E7EB`)
- Include subtle border (`border: 1px solid #D1D5DB`)
- Center the text "Logo" inside using `--color-gray`

### Reni Avatar
Use `assets/reni-avatar.png` for the Reni chatbot assistant in the Help section.

### Links & CTAs
- **"Start Now" buttons**: Link to `#download-app` (anchor link to Download App section)
- **Social media**:
  - Instagram: `https://instagram.com`
  - LinkedIn: `https://linkedin.com`
  - X: `https://x.com`
- **Download buttons**:
  - iOS: `href=""` (empty for now, client will provide)
  - Android: `href=""` (empty for now, client will provide)
- **WhatsApp**: `href="https://wa.me/"` (empty phone number for now)
- **Email**: `href="mailto:support@rentify.ae"`

---

## Content Structure & Copy

> **IMPORTANT**: All copy below must be included verbatim in the design. Notice that there are comments that are not actually content, but instructions for you.

---

### GLOBAL NAV

//Comment: Sticky element on scroll that has links to jump to Home, How it Works, Rewards, Why (takes to Trust Centre section), and Help. Then, second area with links to social media, contact (links to Help section)

### HERO

#### **Rent the Simple Way**

**Monthly rent payments, rewards and secure transactions made simple.**

[Start Now]

#### Highlights

- Pay rent monthly with secure, transparent payment options and earn rewards
- Create, renew, and manage rental agreements online
- Instant receipts, reminders, and customer support
- Designed for tenants, landlords, and agents across the rental ecosystem

//Comment: Create 3 iPhone 17 device mockups with white screens

---

### RENTIFY PAY

#### Rent, On Your Own Terms

Powered by Rentify Pay //Comment: Use assets/rentify-pay-logo.svg here
No cheques. No stress. No confusion.

//Comment: Create 1 iPhone 17 device mockup with white screen

Rentify Pay is built to fit into real life whether you're paying rent, managing a property, or collecting payments.

Everything happens in one place, making rent payments smoother, more transparent, and easier to manage for tenants and landlords.

[Start Now]

---

### CUSTOM PATH

#### Choose Your Journey

**I am a:**

🔘 Tenant  🔘 Landlord //Comment: Single option selection — use JavaScript to show/hide paths based on selection. All paths present in HTML, toggled with CSS/JS.

---

#### //Comment: User chooses Tenant

**What are you looking for?**

🔘 A new apartment to pay monthly

🔘 Migrate existing rental to Rentify for monthly payments

🔘 Convert quarterly or bi-annual cheques to secure digital payments

//Comment: Single option selection — JavaScript toggle for different content

---

#### //Comment: Tenant chooses New apartment or migrate existing

##### How it works

**1. Download and Sign Up**

//Comment: iPhone 17 device with white screen

Get the Rentify app and select Tenant.

**2. Submit Documents**

//Comment: iPhone 17 device with white screen

Upload these for eligibility review:

- Emirates ID
- Passport
- Salary certificate
- 3-month bank statement
- 3 recent salary slips

**3. Get Approved**

//Comment: iPhone 17 device with white screen

Our banking partner reviews your application in 2–3 working days.

**4. Start Paying Monthly**

//Comment: iPhone 17 device with white screen

Once approved, we coordinate with your landlord. You're all set to pay rent monthly through the app. It's secure, simple, and stress-free.

**💰 Bonus:** Get a 100 AED Noon voucher on your first payment + ongoing cashback rewards.

---

#### //Comment: Tenant chooses convert cheques

##### How it works

**Step 1: Download the Rentify app**

//Comment: iPhone 17 device with white screen

Sign up and choose Tenant.

**Step 2: Share your details**

Upload a few basic documents so we can assess eligibility:

//Comment: iPhone 17 device with white screen

- Emirates ID
- Passport
- Tenancy contract

**Step 3: We take it from here**

**That's it.**

---

#### //Comment: User chooses Landlord

##### Why Rentify?

**Get paid upfront. Zero follow-ups. Full transparency.**

//Comment: iPhone 17 device with white screen

You receive the entire annual rent immediately—while your tenant pays monthly. No changes to your lease, no collection stress.

[Next]

---

#### //Comment: Landlord continuation

##### How It Works

**1. Download and Register**

//Comment: iPhone 17 device with white screen

Sign up as a "Landlord" in the Rentify app.

**2. Add Property Details**

//Comment: iPhone 17 device with white screen

Provide:

- Emirates ID
- Property listing
- Title deed
- IBAN details

**3. Verify Your Tenant**

//Comment: iPhone 17 device with white screen

Your tenant applies through Rentify with their tenancy agreement and Ejari.

**4. Get Paid in Full**

//Comment: iPhone 17 device with white screen

Our banking partner deposits the full annual rent directly to your account.

**Done.**

No monthly chasing. No delays. Just guaranteed rent and complete peace of mind.

---

### REWARDS

#### Rewards That Add Up

Rent is your biggest monthly expense. It should give something back.

//Comment: iPhone 17 device with white screen

With Rentify, every rent payment earns you points that can be redeemed across everyday categories from shopping and dining to travel and services.

#### How Rewards Work

//Comment: iPhone 17 device with white screen

- Pay rent monthly through Rentify
- Earn points on every successful payment
- Redeem rewards from 200+ partner brands

Rewards are built into the rental experience — no extra steps, no separate apps.

[Start Now]

---

### TRUST CENTRE

#### Security

Your data and payments are protected with industry-standard security and encryption.

//Comment: 2 logo placeholders (gray ellipses with "Logo" text)

#### Compliance and Data Privacy

We follow local regulations and strict privacy practices to protect your information.

#### Insurance and Risk

Built-in safeguards help protect both tenants and landlords across the rental lifecycle.

[Start Now]

---

### PARTNERS

#### Banking & Payments

Integrated with leading banking and payment partners to support smooth, secure monthly transactions.

//Comment: 3 logo placeholders (gray ellipses with "Logo" text)

#### Ecosystem Benefits

Access value-added services such as registrations, agreements, digital tools, and reward programmes that support the entire rental cycle.

[Start Now]

---

### ABOUT

#### Our Story

Rentify was built to make renting simpler by replacing fragmented, outdated systems with a secure digital foundation.

//Comment: Large photo of team/founders in office setting (source from Pexels/Unsplash/Pixabay)

We enable monthly rent payments, online agreements, built-in rewards, and fast settlements — creating modern infrastructure for renting at scale.

---

### HELP

**We're Always Here for You**

#### Ask Reni

Your virtual assistant for rent-related questions. Available anytime.

//Comment: Use assets/reni-avatar.png

#### WhatsApp

Chat instantly with our support team.

//Comment: Icon button with link to https://wa.me/ (empty phone number)

#### Email

Reach out for detailed or account-specific support.

//Comment: Icon button with link to mailto:support@rentify.ae

---

### DOWNLOAD APP

#### Get Started Now

Manage your rent, agreements, rewards, and support — all in one place.

//Comment: iPhone 17 device with white screen

Available on iOS and Android.

[Download now] //Comment: Two buttons — App Store (href="") and Play Store (href="")

---

### FOOTER

//Comment: A more visually appealing version of the header/global nav with logo, all navigation links, social media icons, and copyright

---

## Anti-Patterns (DO NOT)

### Visual

- ❌ Purple gradients or any gradient backgrounds
- ❌ Generic stock photos (handshakes, pointing at screens)
- ❌ Thin or light headline font weights
- ❌ Sharp corners on cards (minimum 16px radius)
- ❌ More than 2 green shades per section
- ❌ Perfectly centered/symmetrical layouts everywhere
- ❌ Flat, evenly-spaced grids without variation
- ❌ White text on green backgrounds (use dark text)

### Technical

- ❌ Fixed pixel font sizes
- ❌ Layouts that break below 375px
- ❌ Touch targets smaller than 44×44px
- ❌ Removing focus outlines
- ❌ Images without alt attributes
- ❌ Placeholder-only form fields
- ❌ Using fonts other than Rubik and Plus Jakarta Sans

### Brand

- ❌ Any green other than #10BC7D or #4BE7A3
- ❌ Colorful multi-hued illustrations
- ❌ Square or sharp-cornered CTA buttons
- ❌ Generic icon sets (use Solar-style outlined icons)

---

## Quality Checklist

Before considering the design complete, verify:

- [ ] All text passes WCAG AA contrast requirements
- [ ] All interactive elements have visible focus states
- [ ] Layout works correctly at 375px, 768px, and 1280px
- [ ] All images have appropriate alt text
- [ ] Typography uses only Rubik and Plus Jakarta Sans
- [ ] Primary CTAs use #4BE7A3 background with #030712 text
- [ ] At least one asymmetric/overlapping element per major section
- [ ] Semantic HTML with proper heading hierarchy (h1 → h2 → h3)
- [ ] All copy from Content section is included
- [ ] Navigation includes all required links
- [ ] Footer includes logo, links, social icons, and copyright
- [ ] Illustrations follow Milano style (black + green only)
- [ ] Buttons are pill-shaped with 100px+ border-radius
- [ ] Cards have 16-24px border-radius
- [ ] Touch targets are minimum 44×44px
- [ ] Interactive Custom Path section works with JavaScript
- [ ] Real photography sourced from Pexels/Unsplash/Pixabay with proper URLs
- [ ] iPhone 17 device mockups with white screens
- [ ] Reni avatar from assets/reni-avatar.png is used

---

## Reference Images

The following reference images in `benchs/` inform the visual direction:

- **ref-main**: Primary inspiration — bold asymmetric layout, oversized typography overlapping cut-out photography, floating geometric elements, vibrant color blocking
- **ref-1 through ref-10**: Supporting references showing card layouts, typography treatments, color blocking, and editorial compositions
- **app-sample-3, app-sample-5**: Existing Rentify app screens showing brand consistency requirements (button styles, illustration style, color usage, typography)

The website should feel like a "grown-up sibling" of the app — same DNA, but more expressive and editorial for marketing purposes.

---

## Technical Implementation Notes

### Single-File Implementation

Create as a single HTML file with embedded CSS and JavaScript.

### JavaScript Requirements

- Mobile menu toggle (hamburger navigation)
- Custom Path interactive journey selector (show/hide content based on user selection)
- Scroll animations (fade-in-up for content blocks)
- Smooth scroll for anchor links

### CSS Architecture

- Use CSS custom properties (variables) for all colors, spacing, and typography
- Mobile-first responsive approach
- Use `clamp()` for fluid typography and spacing
- Flexbox and CSS Grid for layouts

### Performance

- Lazy load images below the fold
- Use modern image formats where possible
- Minimize JavaScript — CSS-only solutions preferred where possible
- External image URLs (no local storage needed)

### Browser Support

- Modern browsers (Chrome, Firefox, Safari, Edge)
- Graceful degradation for older browsers
