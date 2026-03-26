# Great Loop Books — greatloopbooks.com

A Jekyll site for Great Loop book recommendations, organized by region, category, and reading level. Managed with GitHub + Obsidian, deployed automatically to GitHub Pages.

---

## 📖 Adding a New Book

1. In Obsidian, create a new file in the `_books/` folder
2. Name the file with the book's slug, e.g. `my-new-book.md`
3. Copy the frontmatter template from `_books/TEMPLATE-README.md`
4. Fill in what you know — not everything is required
5. Save and commit to GitHub — the site rebuilds automatically

### Minimum required frontmatter:
```yaml
---
title: "Book Title"
summary: "One sentence description."
categories:
  - memoirs
amazon_url: "https://amzn.to/XXXXX"
---
```

### Your Amazon affiliate tag:
Set once in `_config.yml`:
```yaml
amazon_affiliate_tag: "greatloopbooks-20"
```
Update all Amazon links to use short affiliate URLs from your Associates dashboard.

---

## 🗂️ Site Structure

```
greatloopbooks/
├── _books/              ← One .md file per book
├── _layouts/
│   ├── default.html     ← Base HTML with header/footer
│   ├── book.html        ← Individual book detail page
│   └── page.html        ← Simple content page
├── _includes/
│   └── book-card.html   ← Reusable book card component
├── assets/
│   └── css/main.css     ← All styles
├── books/index.html     ← All books listing with filters
├── book-club/index.html ← Dreamers Book Club reading list
├── by-region/index.html ← Books organized by Loop region
├── for-kids/index.html  ← Books for young readers
├── index.html           ← Homepage
├── _config.yml          ← Site settings
├── Gemfile              ← Ruby dependencies
└── CNAME                ← Custom domain setting
```

---

## 🏷️ Frontmatter Reference

| Field | Required | Notes |
|-------|----------|-------|
| `title` | ✅ | Full book title |
| `author` | — | Author name(s) |
| `summary` | ✅ | 1–2 sentence description for listing pages |
| `description` | — | Fuller write-up for the book's own page |
| `amazon_url` | — | Use shortened affiliate link |
| `bookshop_url` | — | Add when you set up Bookshop.org |
| `categories` | ✅ | See options below |
| `regions` | — | See options below |
| `age_group` | — | `adult`, `teen`, `middle-grade`, `early-reader`, `picture-book`, `all-ages` |
| `book_club` | — | `true` if it's been a Dreamers Club pick |
| `book_club_month` | — | e.g. `"March 2026"` |
| `featured` | — | `true` to show on homepage |
| `featured_month` | — | `"YYYY-MM"` for auto-display in that month |
| `by_looplife` | — | `true` for books written by Alison |
| `cover_image` | — | URL or `/assets/images/books/filename.jpg` |

### Category options:
`dreaming-planning` · `memoirs` · `boat-life` · `kids` · `journals` · `reference` · `fiction` · `regional`

### Region options:
`general` · `norfolk-new-york` · `erie-canal` · `canada` · `great-lakes` · `river-system` · `florida-keys-bahamas` · `florida-east-coast` · `georgia-carolinas`

---

## 📅 Setting the Featured Book of the Month

**Manual approach** — set `featured: true` on any book. Those books always show in the Featured section.

**Auto by month** — set `featured_month: "2026-04"` on a book and it will automatically be highlighted during April 2026. Set multiple books with the same month to feature 2–3 at once.

The homepage uses whichever method finds books first:
1. Month-specific books (`featured_month` matches current month)
2. Fallback: all books with `featured: true`

---

## 🔖 Adding Bookshop.org (When Ready)

1. Sign up at [bookshop.org/affiliates](https://bookshop.org/affiliates)
2. For each book, find its Bookshop.org URL and add it to the `bookshop_url` field
3. The "Buy on Bookshop.org" button will automatically appear on those book pages

---

## 🖼️ Cover Images

Best options (in order of ease):

1. **Open Library** — `https://covers.openlibrary.org/b/isbn/[ISBN]-L.jpg`  
   Free, no permission needed. Works for most books with an ISBN.

2. **Local file** — save to `assets/images/books/filename.jpg`, then use `/assets/images/books/filename.jpg`

3. **Amazon Product Advertising API** — official API access to Amazon images. More setup, but great for a book-focused affiliate site.

---

## 🧭 Pages Summary

| Page | URL | Description |
|------|-----|-------------|
| Homepage | `/` | Featured books, book club spotlight, region nav |
| All Books | `/books/` | Filterable grid of all books |
| Book Club | `/book-club/` | Dreamers Club reading archive |
| By Region | `/by-region/` | Books grouped by Loop region |
| For Kids | `/for-kids/` | Books sorted by age group |
| Each Book | `/books/[slug]/` | Individual book detail page |

---

## Run it locally

Here are the exact commands to run from inside your `greatloopbooks` folder:

**First time only — install dependencies:**
```bash
bundle install
```

**Start the local server:**
```bash
bundle exec jekyll serve
```

Then open **http://localhost:4000** in your browser.

---

**Useful variations:**

```bash
# Auto-rebuild when you save files (watches for changes)
bundle exec jekyll serve --livereload

# If port 4000 is already in use
bundle exec jekyll serve --port 4001

# Show more detail if something errors
bundle exec jekyll serve --verbose
```

---

**If you don't have Ruby/Jekyll installed yet**, here's the one-time setup depending on your OS:

**Mac:**
```bash
# Install Homebrew if you don't have it, then:
brew install ruby
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
gem install bundler
```

**Windows:**
Download and run the RubyInstaller from [rubyinstaller.org](https://rubyinstaller.org) — use the "Ruby+Devkit" version. Then in a new terminal:
```bash
gem install bundler
```

**Linux (Ubuntu/Debian):**
```bash
sudo apt-get install ruby-full build-essential
gem install bundler
```

---

Once `bundle exec jekyll serve` is running, any time you edit and save a `.md` book file or a layout, Jekyll rebuilds automatically and you just refresh the browser to see changes. The `--livereload` flag even does the refresh for you automatically.