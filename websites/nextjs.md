# Next.js Landing Page Prompt

Generate a complete, professional Next.js landing page in one shot by providing your content upfront.

---

## Step 1: Create Your Content

Before running the prompt, create these folders and files in your project:

### Content Files

```
content/
├── site.md
├── hero.md
├── features.md
├── testimonials.md
└── faq.md
```

### Images Folder

```
images/
├── logo.svg
├── hero.png
├── feature-1.png
├── feature-2.png
├── feature-3.png
├── avatar-1.jpg
├── avatar-2.jpg
├── avatar-3.jpg
└── og-background.png (optional)
```

---

## Content File Templates

### content/site.md

```markdown
# Site Configuration

name: Your Product Name
tagline: Your catchy one-liner
description: A longer description for SEO (1-2 sentences)
url: https://yoursite.com
primary_color: #6366f1
secondary_color: #8b5cf6
```

### content/hero.md

```markdown
# Hero Section

headline: Build Something Amazing Today
subheadline: Transform the way you work with our powerful platform. Join thousands of teams already achieving more.

cta_primary_text: Get Started Free
cta_primary_link: /signup

cta_secondary_text: See How It Works
cta_secondary_link: #features

image: hero.png
```

### content/features.md

```markdown
# Features

## Lightning Fast Performance
icon: Zap
image: feature-1.png
Built for speed from the ground up. Your pages load in milliseconds, keeping users engaged and improving SEO rankings.

## Bank-Grade Security
icon: Shield
image: feature-2.png
Enterprise-level security with end-to-end encryption, SOC 2 compliance, and regular security audits to protect your data.

## Seamless Integrations
icon: Plug
image: feature-3.png
Connect with 100+ tools you already use. Slack, GitHub, Jira, and more—all working together effortlessly.

## Real-Time Analytics
icon: BarChart3
image: feature-4.png
Make data-driven decisions with comprehensive dashboards and insights updated in real-time.

## 24/7 Support
icon: HeadphonesIcon
image: feature-5.png
Our dedicated support team is always available to help you succeed, no matter your timezone.

## Developer Friendly
icon: Code
image: feature-6.png
Clean APIs, extensive documentation, and SDKs for every major language. Built by developers, for developers.
```

### content/testimonials.md

```markdown
# Testimonials

## Sarah Johnson
role: CEO at TechCorp
company: TechCorp
avatar: avatar-1.jpg
rating: 5
This platform completely transformed how our team collaborates. We've seen a 40% increase in productivity since switching.

## Michael Chen
role: Lead Developer
company: StartupXYZ
avatar: avatar-2.jpg
rating: 5
The best developer experience I've ever had. Clean APIs, great docs, and the support team is incredibly responsive.

## Emily Rodriguez
role: Product Manager
company: Enterprise Co
avatar: avatar-3.jpg
rating: 5
Finally, a tool that actually delivers on its promises. Our entire organization relies on it daily.
```

### content/faq.md

```markdown
# FAQ

## How do I get started?
Simply sign up for a free account and you'll be guided through our quick setup wizard. Most teams are up and running in under 5 minutes.

## Is there a free trial?
Yes! We offer a 14-day free trial with full access to all features. No credit card required.

## Can I cancel anytime?
Absolutely. There are no long-term contracts or cancellation fees. You can upgrade, downgrade, or cancel at any time.

## Do you offer team plans?
Yes, we have plans designed for teams of all sizes—from startups to enterprises. Contact us for volume discounts.

## Is my data secure?
Security is our top priority. We use end-to-end encryption, regular security audits, and are SOC 2 Type II certified.

## What integrations do you support?
We integrate with 100+ popular tools including Slack, GitHub, Jira, Notion, and many more. Check our integrations page for the full list.
```

---

## Step 2: Run the Prompt

Once your content and images are ready, use this prompt:

```
Create a complete Next.js 16 landing page using the content files in the /content folder and images in the /images folder.

## Tech Stack
- Next.js 16 with App Router
- TypeScript
- Tailwind CSS v4
- Lucide React for icons

## File Structure to Generate

app/
├── layout.tsx
├── page.tsx
├── globals.css
├── opengraph-image.tsx
├── twitter-image.tsx
├── sitemap.ts
├── robots.ts
└── components/
    ├── Header.tsx
    ├── Hero.tsx
    ├── Features.tsx
    ├── Testimonials.tsx
    ├── FAQ.tsx
    ├── CTA.tsx
    └── Footer.tsx

## Instructions

1. Read content/site.md for site-wide configuration (name, colors, SEO)
2. Read content/hero.md and use images/hero.png for the hero section
3. Read content/features.md and map icons to Lucide React components
4. Read content/testimonials.md and use images/avatar-*.jpg for avatars
5. Read content/faq.md for the FAQ accordion

## SEO Requirements

### layout.tsx
- Export metadata with title template, description, keywords from site.md
- Set metadataBase to the URL from site.md
- Include openGraph and twitter card configuration
- Use next/font/google for Inter font

### page.tsx
- Add JSON-LD structured data for Organization schema
- Use values from site.md for the structured data

### opengraph-image.tsx & twitter-image.tsx
- Generate dynamic OG images using ImageResponse API
- Use gradient background with primary/secondary colors from site.md
- Display the site name and tagline
- Size: 1200x630 for OG, 1200x600 for Twitter

### sitemap.ts & robots.ts
- Use the URL from site.md
- Standard sitemap with homepage
- Allow all crawlers

## Component Requirements

### Header.tsx
- Sticky header with blur backdrop
- Logo (from images/logo.svg) on left
- Navigation links: Features, Testimonials, FAQ (smooth scroll)
- CTA button on right
- Mobile hamburger menu with slide-out drawer

### Hero.tsx
- Use exact content from hero.md
- Gradient text for headline (primary to secondary color)
- Two CTA buttons as specified
- Hero image from images/hero.png
- Animated background gradient or grid pattern

### Features.tsx
- Section title: "Features" with subtitle
- 3-column grid (responsive: 1 col mobile, 2 col tablet, 3 col desktop)
- Each feature card from features.md with:
  - Lucide icon (map icon name to component)
  - Title
  - Description
  - Subtle hover animation (lift + shadow)

### Testimonials.tsx
- Section title: "What Our Customers Say"
- 3-column grid of testimonial cards
- Each card with:
  - Quote text
  - Star rating (filled stars from rating field)
  - Avatar image
  - Name, role, company
  - Subtle card styling with border

### FAQ.tsx
- Section title: "Frequently Asked Questions"
- Accordion with animated expand/collapse
- Questions and answers from faq.md
- Plus/minus icon toggle
- Only one item open at a time

### CTA.tsx
- Full-width section with gradient background
- Headline: "Ready to Get Started?"
- Subtext about free trial
- Large CTA button
- Optional: email input form

### Footer.tsx
- Logo and site description
- Link columns:
  - Product: Features, Pricing (href="#"), Integrations (href="#")
  - Company: About (href="#"), Blog (href="#"), Careers (href="#")
  - Support: Help Center (href="#"), Contact (href="#"), Status (href="#")
- Social icons: Twitter, GitHub, LinkedIn
- Copyright with current year

## Styling

### Tailwind Config
- Extend with primary/secondary colors from site.md
- Add animation utilities for fade-in, slide-up

### Design System
- Consistent spacing: py-20 lg:py-32 for sections
- Container: max-w-7xl mx-auto px-4 sm:px-6 lg:px-8
- Cards: bg-white rounded-2xl shadow-sm border border-gray-100
- Buttons: 
  - Primary: bg-primary text-white rounded-full px-8 py-3
  - Secondary: border-2 border-primary text-primary rounded-full
- Gradients: Use primary/secondary for text and backgrounds

### Responsive Design
- Mobile-first approach
- Breakpoints: sm:640px, md:768px, lg:1024px, xl:1280px
- Stack all grids on mobile
- Adjust font sizes responsively

### Animations
- Use Tailwind animate utilities
- Intersection Observer for scroll-triggered animations
- Smooth transitions: transition-all duration-300

## Image Handling
- All images use next/image component
- Proper alt text derived from content
- Lazy loading by default
- Proper width/height or fill mode

## Accessibility
- Semantic HTML (section, nav, main, footer)
- Proper heading hierarchy (h1, h2, h3)
- ARIA labels for interactive elements
- Keyboard navigation for accordion and mobile menu
- Focus visible outlines

Generate all files with complete, production-ready code. The site should look polished and professional immediately.
```

---

## Image Guidelines

For best results, prepare these images:

| Image | Recommended Size | Format | Notes |
|-------|-----------------|--------|-------|
| logo.svg | 40x40 or scalable | SVG | Square or horizontal |
| hero.png | 1200x800 | PNG/WebP | Main hero illustration |
| feature-*.png | 400x400 | PNG/SVG | Icons or illustrations |
| avatar-*.jpg | 200x200 | JPG/WebP | Square, cropped faces |
| og-background.png | 1200x630 | PNG | Optional for OG images |

---

## Quick Start

```bash
# 1. Create new Next.js project
npx create-next-app@latest my-landing --typescript --tailwind --eslint --app

# 2. Navigate to project
cd my-landing

# 3. Create content structure
mkdir -p content images

# 4. Add your content files (copy templates above)
# 5. Add your images to /images folder

# 6. Run the prompt above with your AI assistant
# 7. Review and adjust generated code

# 8. Install additional dependencies
npm install lucide-react

# 9. Start development server
npm run dev
```
