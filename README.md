# Marazon AI Solution — Website

Marketing site for **Marazon AI Solution** (marazonai.com). Hosted on **Netlify**, deployed automatically from this GitHub repo: every push to `main` goes live in under a minute.

## Tech stack

Deliberately simple — **no framework, no build step, no dependencies**:

- Hand-written **HTML + CSS + vanilla JavaScript**
- CSS lives inside each page's `<style>` block; JS in a `<script>` at the bottom
- **Google Fonts** loaded via one `<link>` tag in the `<head>`
- **Netlify Forms** handles the contact form (no server code — submissions appear in Netlify dashboard → Forms → "contact")

Anyone who knows basic HTML can edit this site with any text editor.

## File map

```
MarazonAI/
├── index.html          ← the entire main site (95% of edits happen here)
├── blog/index.html     ← blog listing page (self-contained, own CSS)
├── assets/logo.png     ← brand logo (nav + footer + social share image)
├── favicon.ico, favicon-*.png, apple-touch-icon.png,
│   android-chrome-*.png, site.webmanifest    ← browser/phone icons
├── sitemap.xml         ← page list for search engines
└── robots.txt          ← search engine permissions
```

## Inside index.html (top to bottom)

1. **`<head>`** — SEO: title, meta description/keywords, Open Graph + Twitter share tags, and a JSON-LD structured-data block for Google.
2. **`<style>`** — all CSS, organized with comment banners (`── NAV ──`, `── HERO ──`, `── SERVICES ──`, …).
   **Brand colors** are CSS variables at the very top in `:root` — change them once, the whole site recolors:
   - `--navy: #0B1C2C` (background canvas)
   - `--blue: #4A9ED6` (Core Brand Blue accent)
   - `--orange: #FF7F27` (accent orange)
3. **Page sections in order:** nav → mobile menu → hero (headline, stats strip, pills, buttons) → services → process → why Marazon → about us → contact form → footer.
4. **`<script>`** — four small functions: hamburger menu, scroll fade-in animations, counting stat numbers, contact-form AJAX submit.

## Brand typography (keep edits on-brand)

| Font | Used for |
|---|---|
| **Bebas Neue** | Hero headline only |
| **Poppins** | All other headings and body text |
| **Chakra Petch** | Small labels, pills/tags, numbers |

## How to make a typical edit

1. **Change text:** open `index.html`, search (Ctrl+F) for the sentence, edit, save.
2. **Preview locally:** double-click the file to open it in a browser. (The contact form only submits on the live Netlify site; everything else works locally.)
3. **Publish:** commit and push to `main`. Netlify deploys automatically.
   *No tools installed?* Edit the file directly on github.com (pencil icon) and commit — same result.

## Adding a blog post

Open `blog/index.html` — there is a commented-out **post card template** with instructions in the file. Copy it, fill in your title/excerpt/date, and create a matching HTML page for the article body (use the blog page's own styles as the starting point). Then add the new article URL to `sitemap.xml`.

## Responsive / mobile

Mobile layout is controlled by `@media (max-width: 900px)` (and one `480px`) block near the bottom of each page's `<style>`. If an edit looks right on desktop but wrong on a phone, look there.

## Contact form (Netlify Forms)

The form in `index.html` is tagged `data-netlify="true"` with a honeypot anti-spam field. Submissions appear in **Netlify dashboard → Forms → "contact"**. Set the email notification target there (currently intended: support@marazonai.com).
