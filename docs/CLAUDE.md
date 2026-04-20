# Noova Solutions — Astro Website

Small business website for Noova Solutions, an IT outsourcing company offering staff augmentation, dedicated teams, custom software development, and IT consulting. Also has an AI product called Comerciafy (comerciafy.com) linked externally. Built with Astro (SSG).

## Commands

- `npm run dev`: Start dev server
- `npm run build`: Production build
- `npm run preview`: Preview production build locally
- `npx astro add [integration]`: Add Astro integrations

## Tech Stack

- Astro (static site generation, file-based routing)
- Scoped styles in .astro components + CSS custom properties in `src/styles/global.css`
- No heavy frameworks — use React/Svelte ONLY for client-side interactivity (mobile nav toggle, Google Calendar embed) with `client:load` or `client:visible`
- Astro Image component for all images

## Project Structure

```
src/pages/
  index.astro          → Home (landing page)
  services.astro       → Services (staff aug, dedicated teams, software dev, consulting)
  work.astro           → About Us / company story
  contact.astro        → Contact (Google Calendar scheduling)
src/layouts/
  BaseLayout.astro     → Head, meta tags, Navbar, Footer, Schema.org JSON-LD
src/components/        → Navbar, Footer, Hero, ServiceCard, TestimonialCard, ValueCard, ProcessStep, TeamMember, FAQ, CTA
src/styles/
  global.css           → CSS custom properties (colors, spacing, typography)
src/assets/            → Logo, images, brand assets (processed by Astro)
public/                → Favicon, og-image, static files
docs/
  website-content.md   → All page copy, headlines, CTAs, meta descriptions
```

## Content Source

All website copy is in `docs/website-content.md`. Read this file before building any page. It contains exact headlines, body text, CTAs, form fields, meta descriptions, and section structure for every page.

## Navigation

- Logo: Noova Solutions (links to /)
- Services (links to /services)
- AI Agents (EXTERNAL link to https://comerciafy.com — opens in new tab with target="_blank" rel="noopener noreferrer")
- Work (links to /work)
- Contact (links to /contact)
- CTA Button: "Schedule a Call" (links to /contact)

AI Agents is NOT a page. It is an external nav link only.

## Contact Page — Google Calendar

The contact page uses an embedded Google Calendar Appointment Scheduling widget as the primary contact method. Embed via iframe using the URL: https://calendar.google.com/calendar/appointments/schedules/[SCHEDULE_ID]. Make the iframe responsive. Secondary contact options: email and LinkedIn.

## Design Guidelines

- Modern and approachable tone — not corporate, not startup-bro
- Mobile-first responsive layouts (Flexbox, Grid)
- Limited palette: 2-3 brand colors + neutrals as CSS custom properties
- Max 2 font families (1 display, 1 body)
- Every page has a clear CTA leading to /contact
- Generous whitespace, clear visual hierarchy
- Semantic HTML, WCAG 2.1 AA accessibility

## SEO

- Unique title and meta description per page (passed as props to BaseLayout)
- Single h1 per page, proper heading hierarchy
- Alt text on all images
- Schema.org LocalBusiness JSON-LD in layout head
- Sitemap via @astrojs/sitemap
- Open Graph tags per page (og:title, og:description, og:image)
- Target: Lighthouse 90+ all categories

## Important Rules

- This is a static site (SSG). No SSR.
- Comerciafy is an external product at comerciafy.com — never build a page for it, only link to it
- All "Schedule a Call" CTAs link to /contact
- All Comerciafy CTAs link to https://comerciafy.com (new tab)
- Contact form is NOT needed — Google Calendar embed replaces it
- Content is in English, business is based in San Salvador, El Salvador
- Never use Lorem ipsum — use real copy from docs/website-content.md
- Brand assets are in src/assets/ — use them for logo, icons, etc.
