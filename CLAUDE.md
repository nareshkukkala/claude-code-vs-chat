# Claude Code vs Claude Chat — Project Memory

## What This Project Is

A single static HTML page comparing Claude Code (developer CLI) and Claude Chat (web interface). Deployed to GitHub Pages and Vercel.

## Tech Stack

- **Single file:** `index.html` — all CSS inlined, zero dependencies, no build step
- **Style:** Purple gradient (#667eea → #764ba2) with glassmorphism cards
- **Layout:** CSS Grid, responsive (single-column below 640px)

## File Structure

```
index.html              # The entire page — edit this to change content/style
.claude/
  launch.json           # Dev server configs (Python HTTP Server on port 3000)
docs/
  superpowers/
    specs/              # Design spec
    plans/              # Implementation plan
```

## Local Development

```bash
python3 -m http.server 3000
# then open http://localhost:3000
```

## Deployment

| Target | URL | How |
|--------|-----|-----|
| Vercel | https://claude-code-vs-chat-indol.vercel.app | `vercel deploy --prod` |
| GitHub Pages | https://nareshkukkala.github.io/claude-code-vs-chat | Auto on push to `main` |
| GitHub Repo | https://github.com/nareshkukkala/claude-code-vs-chat | `git push origin main` |

Vercel auto-deploys on every push to `main` once the GitHub integration is connected.

## Making Changes

1. Edit `index.html`
2. Test locally: `http://localhost:3000`
3. Commit and push: `git add index.html && git commit -m "..." && git push`
4. Vercel deploys automatically

## Design Decisions

- **No framework** — plain HTML/CSS keeps it simple and fast
- **All CSS inline** — no external requests, works offline, no CDN dependency
- **Glassmorphism** — `backdrop-filter: blur(16px)` on cards and table
- **Accessibility** — semantic HTML (`<main>`, `<section>`, `<h2>`), `aria-hidden` on decorative emoji, `aria-label` on ✓/✗ table cells, `:focus-visible` on buttons

## CTA Button URLs

- "Get Claude Code →" → `https://claude.ai/download`
- "Open Claude Chat →" → `https://claude.ai`
