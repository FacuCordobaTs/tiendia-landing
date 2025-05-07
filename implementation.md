# SEO Implementation for Tiendia.app

## Overview
This document outlines the implementation of SEO features for the Tiendia.app landing page, built with Astro.

## Implemented Features

### 1. Sitemap Generation
- [x] Installed `@astrojs/sitemap` integration
- [x] Configured `astro.config.mjs` with site URL
- [x] Added sitemap to integrations array
- [x] Site URL set to "https://tiendia.app"

### 2. Meta Tags and Open Graph
- [x] Created reusable `<SEO />` component (`src/components/SEO.astro`)
- [x] Implemented dynamic title and description
- [x] Added Open Graph meta tags
- [x] Added Twitter Card meta tags
- [x] Implemented canonical URLs
- [x] Integrated SEO component in main layout
- [x] Added placeholder Open Graph image configuration

### 3. Structured Data (JSON-LD)
- [x] Added WebApplication schema
- [x] Implemented dynamic JSON-LD generation
- [x] Added basic application information
- [x] Included pricing information
- [x] Added FAQ structured data with common questions and answers

### 4. Additional SEO Files
- [x] Created `robots.txt` in public directory
- [x] Added sitemap reference in robots.txt

## Technical Details

### SEO Component
The SEO component (`src/components/SEO.astro`) handles all meta tags and structured data. It accepts the following props:
- `title`: Page title
- `description`: Meta description
- `image`: Open Graph image URL
- `canonicalURL`: Canonical URL for the page

### Configuration
The sitemap is configured in `astro.config.mjs`:
```javascript
export default defineConfig({
  site: 'https://tiendia.app',
  integrations: [sitemap()],
  // ... other config
});
```

### Usage
The SEO component is used in the main layout (`src/layouts/Layout.astro`):
```astro
<SEO 
  title={title}
  description={description}
  image="/og-image.png"
/>
```

### Open Graph Image
A placeholder Open Graph image needs to be created at `/public/og-image.png` with the following specifications:
- Dimensions: 1200x630 pixels
- Format: PNG
- Content: Dark background (#1a1a1a) with "Tiendia.app" text in white
- Location: `/public/og-image.png`

You can create this image using any image editing software or online tools like Canva.

## Remaining Tasks
- [ ] Create and optimize Open Graph image (placeholder created, needs final design)
- [ ] Implement hreflang tags for internationalization
- [ ] Add XML sitemap validation
- [ ] Implement breadcrumb structured data

## Testing and Validation

### Automated Testing
To validate the SEO implementation:

1. Build the project:
```bash
npm run build
```

2. Check the generated sitemap:
```bash
# The sitemap should be available at:
# dist/sitemap-index.xml
```

### Manual Validation
Use the following tools to validate SEO elements:

1. **Meta Tags Preview**:
   - Visit [Meta Tags Preview](https://metatags.io/)
   - Enter your URL to preview how your site appears in social media

2. **Google Rich Results Test**:
   - Visit [Google Rich Results Test](https://search.google.com/test/rich-results)
   - Enter your URL or paste your JSON-LD code
   - Verify that both the WebApplication and FAQPage schemas are properly recognized

3. **Twitter Card Validator**:
   - Visit [Twitter Card Validator](https://cards-dev.twitter.com/validator)
   - Enter your URL to preview Twitter card appearance

4. **Facebook Sharing Debugger**:
   - Visit [Facebook Sharing Debugger](https://developers.facebook.com/tools/debug/)
   - Enter your URL to preview Facebook sharing appearance

## Notes
- The implementation follows Astro's best practices for SEO
- All meta tags are dynamically generated based on page content
- Structured data is implemented using JSON-LD format
- The sitemap is automatically generated during build time
- The robots.txt file allows all crawlers and references the sitemap
- FAQ structured data has been added to improve search engine visibility 