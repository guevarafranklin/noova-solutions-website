# Noova Solutions — Astro Website

Small business website for Noova Solutions, an IT outsourcing company (staff augmentation + dedicated teams) with an AI product called Comerciafy. Built with Astro (SSG).

## Tech Stack

- Astro (static site generation, file-based routing)
- Scoped styles in .astro components + CSS custom properties in `src/styles/global.css`
- No heavy frameworks — use React/Svelte components ONLY for client-side interactivity (forms, modals, mobile nav toggle) with `client:load` or `client:visible`
- Astro Image component for all images (automatic WebP/AVIF optimization)

## Commands

- `npm run dev`: Start dev server
- `npm run build`: Production build
- `npm run preview`: Preview production build locally
- `npx astro add [integration]`: Add Astro integrations (sitemap, tailwind, etc.)

## Project Structure

```
src/pages/          → Routes: index, services, comerciafy, about, contact
src/layouts/        → BaseLayout.astro (head, meta, header, footer, Schema.org JSON-LD)
src/components/     → Navbar, Footer, Hero, ServiceCard, TestimonialCard, ContactForm, CTA, FeatureCard
src/content/        → Blog posts or content collections (if added later)
src/styles/         → global.css with CSS custom properties (colors, spacing, typography)
public/             → Favicon, fonts, static assets
```

## Content Source

All website copy is in `docs/website-content.md`. Read this file before building any page — it contains the exact headlines, body text, CTAs, form fields, meta descriptions, and page structure for every page.

## Design Guidelines

- Modern and approachable tone — not corporate, not startup-bro
- Mobile-first responsive layouts (Flexbox, Grid)
- Limited palette: 2-3 brand colors + neutrals defined as CSS custom properties
- Max 2 font families (1 display, 1 body)
- Every page has a clear CTA
- Generous whitespace, clear visual hierarchy
- Semantic HTML, WCAG 2.1 AA accessibility

## SEO Requirements

- Unique `<title>` and `<meta name="description">` per page (passed as props to BaseLayout)
- Proper heading hierarchy (single h1 per page)
- Alt text on all images
- Schema.org LocalBusiness JSON-LD in layout head
- Sitemap via `@astrojs/sitemap`
- Target: Lighthouse 90+ on all categories

## Architecture Rules

- One layout component handles all shared structure (head, nav, footer, meta)
- Pages are thin — they import layout + components and pass content as props
- Components are reusable across pages (ServiceCard used on home and services page)
- Keep JS minimal — if it can be done with CSS, do it with CSS
- No localStorage, no external API calls at build time unless adding a CMS later

## Important Notes

- This is a static site, NOT an app. No SSR unless explicitly requested.
- Comerciafy is a product, not an open-source tool — the product page describes it but does not implement it
- The site serves the Latin America and US market — content is in English but the business is based in San Salvador, El Salvador
- Contact form should be a static form (Netlify Forms, Formspree, or similar) — no backend needed
- When writing placeholder content, make it sound real and professional, never use Lorem ipsum
