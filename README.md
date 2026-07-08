# 10000ideas — Prototype Build

A static HTML/CSS/JS prototype for **10000ideas.com** — a Pinterest-style business idea discovery site with an AI search bar, an AI chatbot assistant, and a CMS dashboard for managing content. Built as a test/demo project — no backend, no real database, no real AI calls. All data is dummy/hardcoded for demonstration.

## What's in this project

### Public site (visitor-facing)
| File | Purpose |
|---|---|
| `index.html` | Homepage — hero, AI search bar, trending ideas masonry grid |
| `browse.html` | Browse Ideas — full masonry grid with category filters |
| `idea.html` | Idea Detail — single idea page, loaded via `?id=` query param |
| `about.html` | How It Works — 3-step process, platform stats |

### Admin
| File | Purpose |
|---|---|
| `cms-dashboard.html` | CMS — dashboard, analytics, ideas table, idea editor, blog posts, media library, submissions, members, AI features, site settings, integrations |

### Supporting docs
| File | Purpose |
|---|---|
| `docs/site-architecture-mindmap.pdf` | Visual site flow: CMS → Homepage → Browse/About → Idea Detail |
| `docs/suggestions-to-improve.pdf` | 9 concrete suggestions for turning this into a real product |

## How to run

No build step, no server required.

1. Download all files, keeping them in the same folder.
2. Open `index.html` directly in a browser (double-click, or drag into a browser tab).
3. Click through the nav to reach Browse, an Idea Detail page, About, or the CMS dashboard.

Every page is fully self-contained (CSS and JS are inlined) — none of them depend on an external file to render, so they also work if shared or opened individually.

## Design system

Reused across every page for visual consistency:

- **Colors:** obsidian background (`#0A0D13`), navy surfaces, gold accent (`#E8A33D`), ember accent (`#FF6A3D`)
- **Type:** DM Serif Display (headings), DM Sans (body), JetBrains Mono (labels/data)
- **Layout:** Pinterest-style CSS-column masonry for idea cards, responsive down to mobile

## Features implemented

- **AI search** (homepage) — keyword-matched dummy results with a fake "match %" score
- **AI chatbot** — floating widget on every public page, canned responses for common questions (budget, Startup India registration, franchise ideas)
- **CMS dashboard** — stats, analytics charts, ideas table with status chips (live/draft/review/flagged), idea editor with AI-enhance buttons, submissions queue, members table, functional **Site Settings** (general/branding/SEO/access tabs, saves to browser storage) and **Integrations** (connect/disconnect service cards)

## Known limitations (this is a prototype, not production)

- No real backend — all data is hardcoded in `shared.js`/inline scripts, nothing persists except CMS Site Settings (saved to `localStorage` for the demo)
- AI search and AI chatbot are keyword-matched mockups, not real model calls
- Idea Detail uses a query param (`idea.html?id=3`) instead of clean per-idea URLs
- Images are CSS gradient placeholders, not real photography
- No authentication — CMS login page is not implemented; the dashboard is open

See `docs/suggestions-to-improve.pdf` for the full list of what a production build would need next.

## Open item

One requirement from the original brief — a specific **matching algorithm** — was referenced but never shared in this conversation. The AI search currently uses a simple keyword-lookup as a placeholder. If you have that spec, send it and it can be wired into `aiSearch()` in place of the current logic.
