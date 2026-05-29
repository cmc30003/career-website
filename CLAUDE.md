# camrychapman.com — Project Notes

## Site Overview
Personal career website for Camry Chapman — Data Leadership & Institutional Research.
- Stack: pure HTML + CSS, no framework or build step
- Hosted: GitHub Pages at https://cmc30003.github.io/career-website/
- Custom domain: https://camrychapman.com
- Repo: https://github.com/cmc30003/career-website

## Pages
- index.html — Home
- work.html — Resume
- leadership.html — Leadership Philosophy
- blog.html — Blog index (post preview cards)
- articles.html — Articles & Reading
- reports.html — Reports / Dashboards
- consulting.html — Consulting services + Stripe packages
- posts/ — Individual full blog post pages

## Stripe Payments (Consulting Page)
Four payment links on consulting.html. Currently DISABLED in Stripe dashboard (pending verification).
To go live: log into Stripe → Payment Links → re-activate each link. No code changes needed.

Products & prices:
- Discovery & Assessment — $1,500
- Reporting Modernization — $2,500
- Data Literacy Workshop (Half Day) — $800
- Data Literacy Workshop (Full Day) — $1,500

## Blog Publishing Process

### Writing a new post — checklist
1. Write the post (can draft here and refine together)
2. Create file at: posts/your-post-slug.html
   - Copy the structure from posts/ai-website.html
   - Update: <title>, <meta name="description">, og:title, og:description, og:url
   - Update: <h2> post title, <p class="post-meta"> date, tags, and post body
   - Update: JSON-LD BlogPosting headline, description, datePublished, url
3. Add a preview card to blog.html (copy an existing article.post-placeholder block)
4. Add a card to the Blog section on index.html
5. Add the new URL to sitemap.xml (copy an existing <url> block, update <loc> and <lastmod>)
6. Commit and push → GitHub Pages deploys automatically (~2 min)
7. In Google Search Console → URL Inspection → paste new post URL → Request Indexing

### Post file template (key head tags to update)
```html
<meta name="description" content="YOUR DESCRIPTION" />
<meta property="og:title" content="YOUR POST TITLE" />
<meta property="og:description" content="YOUR DESCRIPTION" />
<meta property="og:url" content="https://camrychapman.com/posts/YOUR-SLUG.html" />
<meta property="og:image" content="https://camrychapman.com/files/headshot-web.jpg" />
<title>YOUR POST TITLE | Camry Chapman</title>
```

### LinkedIn Sharing
Each post is shareable on LinkedIn with a rich preview card because of Open Graph meta tags.
To share: copy the post URL (e.g. https://camrychapman.com/posts/ai-website.html) and paste into a LinkedIn post. LinkedIn reads the og: tags to build the preview automatically.

## CSS Notes
- style.css is the single stylesheet for all pages
- Posts subfolder uses ../style.css (one level up)
- Key classes: .container, .hero, .section, .card, .post-placeholder, .post-body, .post-meta, .back-link
- Colors: --navy, --blue, --deep-blue, --accent (green), --soft-gray

## Git Workflow
- Branch: main
- Push directly to main → triggers GitHub Pages rebuild (~2 min)
- Hard refresh (Ctrl+Shift+R) after push to bypass browser cache
- If push rejected: run `git pull` first, then `git push`
