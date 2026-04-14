# CLAUDE.md

## Project overview

Static product catalog site hosted on GitHub Pages at albin54.github.io. Contains HTML product pages organized by category with supporting assets (images, PDFs).

## Structure

- `products/` — product pages organized by category (cameras, headphones, keyboards, laptops, monitors, smartphones, speakers, tablets, tvs, watches)
- Each category has: HTML product pages, an `assets/` folder (images), a `files/` folder (PDFs), and a `sitemap.xml`
- `sitemap.xml` — root sitemap index pointing to per-category sitemaps and pages-sitemap
- `pages-sitemap.xml` — sitemap for standalone pages (about, contact-us)

## Conventions

- When adding or removing product pages, always update the corresponding category `sitemap.xml` and the root `sitemap.xml` lastmod dates
- Sitemap `lastmod` dates use `YYYY-MM-DD` format
- Product page filenames use kebab-case (e.g., `galaxy-s24.html`, `nothing-phone-3.html`)
- Assets follow the pattern `{product-name}-main.jpg`, `{product-name}-thumb.png`, `{product-name}-gallery-N.jpg`
- PDF files follow the pattern `{product-name}-specs.pdf`, `{product-name}-manual.pdf`

## PDF generation

No PDF libraries are installed in this repo. Use the Python venv at `~/Code/test/env` which has `reportlab` and `pypdf` available:
```
~/Code/test/env/bin/python -c "from reportlab.pdfgen import canvas; ..."
```
