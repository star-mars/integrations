# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the **Premagic Integrations** section — a set of static HTML/CSS pages that document and showcase Premagic's platform integrations with event management tools (Cvent, etc.). These pages are designed to live on or link from www.premagic.com.

## Architecture

```
integration/
├── index.html          # Master integrations listing page (all integrations)
├── styles.css          # Shared stylesheet for all integration pages
├── cvent/
│   └── index.html      # Cvent integration detail (child page)
└── Premagic Integration Document.pdf  # Source document for Cvent integration content
```

**Page hierarchy**: Master page (`index.html`) links to child pages (e.g., `cvent/index.html`). Child pages have breadcrumbs back to the master. New integrations follow this pattern: create a new directory with its own `index.html` that references `../styles.css`.

## Design System (Premagic Brand)

All pages follow the Premagic design system established in `/Users/ketan/Documents/Premagic/event/styles.css`. Key values:

- **Font**: Poppins (Google Fonts), weights 400–800
- **Primary colors**: Deep Blue `#1f0f61`, Coral `#ff6550`, Gradient `linear-gradient(154.5deg, #ff957d, #d9629f, #2b4bc3)`
- **Text colors**: Dark `#1a1a2e`, Medium `#4a4a68`, Light `#6b6b8a`
- **Backgrounds**: Light Blue `#f1f4ff`, Gray-100 `#f8f9fc`
- **Shadows**: sm/md/lg using `rgba(31, 15, 97, ...)`
- **Container**: 1200px max-width, 24px horizontal padding
- **Card radius**: 16px, button radius: 8px
- **Section padding**: 80px vertical (60px mobile)
- **Responsive breakpoints**: 768px (tablet), 480px (mobile)

## Component Patterns

- **Navbar**: Fixed, white background, Premagic logo left, nav links + CTA right
- **Hero**: Light blue background, centered text, gradient badge pill, decorative radial gradient pseudo-elements
- **Feature cards**: White bg, 32px padding, 16px radius, shadow-sm, hover lifts -4px
- **Integration cards**: White bg with 1px border, logo pair with `+` connector, tags, "Learn more" link with arrow
- **Coming soon cards**: Dashed border, gray background, no hover effect, gradient "Coming Soon" badge
- **CTA sections**: Deep blue background, centered white text, coral primary + ghost secondary buttons
- **Footer**: Gray-100 background, logo + tagline left, nav links right

## Adding a New Integration

1. Create directory: `integration/<platform-name>/`
2. Create `index.html` using `cvent/index.html` as template
3. Update hero logos, breadcrumb, content from source documentation
4. Add a card entry in `integration/index.html` inside `.integrations-grid`
5. Use brand logos via `https://logo.clearbit.com/<domain>` or official logo URLs
6. To convert a "coming soon" card to live: remove `.coming-soon` class, add the `<a>` link, remove the coming-soon badge

## External Assets

- **Premagic logo**: `https://premagic.com/images/premagic-logo.svg` (header/footer), `https://premagic.com/images/premagic-logo-icon.svg` (icon only)
- **Partner logos**: Sourced via `https://logo.clearbit.com/<domain>` for consistency
- **Icons**: Inline SVG using Feather icon style (24px, stroke-width 2, no fill)

## Related Projects in Parent Directory

- `/Users/ketan/Documents/Premagic/event/` — Competitor comparison pages (Premagic vs Snoball, Premagic vs InGo) deployed via Netlify
- `/Users/ketan/Documents/Premagic/Homepage/` — Homepage assets

## Content Source

The Cvent integration content is sourced from `Premagic Integration Document.pdf` (4 pages). Key content areas: poster widget embedding, auto-generated personalized posters, campaign distribution, full attendee sync, bi-directional data flow, AI-powered photo distribution, and the referral flywheel concept.
