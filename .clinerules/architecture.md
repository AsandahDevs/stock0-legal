# Architecture Rules — stock0-legal (Static HTML Pages)

## Project Overview

Stock0-legal hosts the publicly accessible legal and support pages for the stock0 mobile application. It is a collection of static, standalone HTML files with embedded CSS — no build tools, frameworks, or server-side rendering.

## Pages & Structure

1. **File-per-page**: Each legal/support page is a single standalone `.html` file at the repository root. No subdirectories or nested routing.
   - `index.html` — Privacy Policy (POPIA-compliant)
   - `delete-account.html` — Account Deletion Instructions
   - `support.html` — Support / Contact page
2. **Self-contained styling**: All CSS is embedded inline via `<style>` tags within each HTML file. No external stylesheets, CSS preprocessors, or CSS-in-JS.
3. **No JavaScript**: Pages are purely informational — no JavaScript, no interactivity, no analytics scripts. If a dynamic behaviour is required (e.g., form submission), add it minimally and with progressive enhancement.

## Content & Compliance

4. **POPIA compliance**: The Privacy Policy (`index.html`) must reflect the current data-handling practices of the stock0 app. Any change to data collection, advertising (personalised vs. non-personalised), or third-party SDKs in the app must be mirrored here.
5. **Single source of truth**: Legal text content lives only in these HTML files. Do not duplicate privacy or support content in the app codebase (`stockO-UI`). The app should link to these hosted pages.
6. **Contact information**: All contact details (email, support channels) must be consistent across all three pages. Use a single source for email addresses.

## Quality & Maintenance

7. **Responsive design**: All pages must render legibly on mobile and desktop viewports. Use the existing `max-width` container pattern with `meta viewport` tag. Avoid fixed widths.
8. **Version tracking**: All pages include an "Effective Date" or "Last Updated" line. Update this whenever content changes.
9. **Hosting**: These pages are hosted via GitHub Pages (or similar static hosting). No backend, no API endpoints. Ensure all internal links between pages use relative paths.
10. **GitHub Pages / CNAME**: If a custom domain is configured, maintain the `CNAME` file at repository root. Keep the publishing source set to the `main` branch root.