# 📚 Great Loop Books — Book File Template

## How to Add a Book

Create a new `.md` file in the `_books/` folder. The filename becomes the URL slug.
Example: `_books/crossing-the-wake.md` → `greatloopbooks.com/books/crossing-the-wake/`

---

## Frontmatter Reference

Copy this template and fill in what you know. Everything marked `# optional` can be left out.

```yaml
---
title: "Full Book Title Here"
author: "Author Name"
cover_image: "/assets/images/books/your-filename.jpg"   # optional — see note on images below

# Short description shown on listing pages (1–2 sentences)
summary: "A brief, engaging description of the book."

# Longer description shown on the book's own page
description: |
  A fuller write-up of the book. Can be multiple paragraphs.
  Use this space to talk about why you recommend it.

# Buy links — add whichever apply
amazon_url: "https://amzn.to/XXXXX"
bookshop_url: ""              # optional — for Bookshop.org when you set that up
aglca_url: ""                  # optional — for AGLCA store links
other_buy_url: ""              # optional — for author's website, etc.
other_buy_label: "Buy from Author"  # optional — label for the above

# Categories (use as many as apply)
# Options: dreaming-planning, boat-life, memoirs, regional, kids, journals, reference, fiction
categories:
  - dreaming-planning
  - memoirs

# Loop region(s) this book covers — optional
# Options: general, erie-canal, great-lakes, river-system, florida-keys-bahamas,
#          florida-east-coast, georgia-carolinas, norfolk-new-york, canada
regions:
  - general

# Age recommendation — optional
# Options: adult, teen, middle-grade, early-reader, picture-book, all-ages
age_group: adult

# Book Club flags
book_club: true          # true if it's been a Dreamers Book Club pick
book_club_month: "March 2026"   # optional — month it was featured

# Spotlight / featured — optional
featured: false          # set true to show on homepage featured section
featured_month: ""       # YYYY-MM format for auto-display by month, e.g. "2026-03"

# Written by Alison / Loop Life Academy — optional
by_looplife: false

# Format info — optional
formats:
  kindle: true
  print: true
  audiobook: false

# Tags for filtering — optional, free-form
tags:
  - memoir
  - solo travel
  - women cruisers
---

Your extended notes or review can go here in the body of the file.
This will appear on the book's detail page below the description.
```

---

## Cover Image Note

**Can I copy images from Amazon?**
Technically the product images on Amazon are copyrighted. For a clean affiliate site, the best options are:

1. **Use the Amazon Product Advertising API** — gives official access to product images (requires approval, a bit of setup, but worth it for a dedicated book site).
2. **Link directly to the image URL** from Amazon — works but can break if Amazon changes their URLs.
3. **Open Library / Google Books covers** — many books have covers available from `covers.openlibrary.org/b/isbn/[ISBN]-L.jpg`. This is the easiest no-friction approach.
4. **Publisher press kits** — publishers often have hi-res cover images available for media use.

The template supports any image URL or a local file. Open Library is recommended as a starting point:
```yaml
cover_image: "https://covers.openlibrary.org/b/isbn/9781234567890-L.jpg"
```
