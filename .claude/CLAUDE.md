# GreatLoopBooks.com — Project Context

A Jekyll/GitHub Pages site curating books for America's Great Loop boating community. Managed with GitHub + Obsidian, auto-deployed via GitHub Actions.

---

## Site Structure

```
greatloopbooks/
├── _books/              ← One .md file per book — this is the main collection
├── _layouts/
│   ├── default.html
│   ├── book.html        ← Individual book detail page
│   └── page.html
├── _includes/
│   └── book-card.html
├── assets/css/main.css
├── books/index.html     ← All books listing with filters
├── book-club/index.html ← Dreamers Book Club reading list
├── by-region/index.html
├── for-kids/index.html
├── index.html
├── _config.yml
├── Gemfile
└── CNAME
```

---

## Key Config

- **Amazon affiliate tag**: `greatloopbooks-20` (set in `_config.yml`)
- **Affiliate URL format**: `https://www.amazon.com/dp/[ASIN]?tag=greatloopbooks-20`
- **Custom domain**: greatloopbooks.com
- **Deploy**: push to main → GitHub Actions rebuilds automatically

---

## Book Files

- Live in `_books/[slug].md`
- Slug becomes the URL: `_books/crossing-the-wake.md` → `/books/crossing-the-wake/`
- Required fields: `title`, `summary`, `categories`
- See `.claude/agents/library-curator.md` for the full frontmatter reference and writing guidelines

---

## Running Locally

```bash
# First time
bundle install

# Start server
bundle exec jekyll serve

# With live reload
bundle exec jekyll serve --livereload
```

Local preview: http://localhost:4000

---

## Editorial Voice

- Warm, conversational, written for fellow boaters and Loop dreamers
- No em dashes
- No marketing language or hype
- Summaries are 1–2 sentences, present tense
- Descriptions explain what kind of reader will love the book and its Loop relevance

---

## Featured Books Logic

- `featured: true` → always shows in homepage featured section
- `featured_month: "YYYY-MM"` → auto-displays during that month only
- Homepage checks month-specific books first, falls back to `featured: true`

---

## Agent

The **library-curator** agent handles all book additions and audits.
Invoke it with `@agent-library-curator` in Claude Code, or just describe a book task and Claude will delegate automatically.
