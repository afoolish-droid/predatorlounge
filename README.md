# Beware of Predators: Exploring Grooming through Fiction

A dark art project. Visitors press "Generate the Narrative," confirm "Are you sure?", and receive one of 20 stories set in the Sunset Dreams Lounge.

## How it works

- `site/index.html`: the page.
- `site/stories.js`: the 20 stories. Each visitor gets every story once, in random order, before any repeats (tracked per browser tab).
- `stories/`: plain-text source of the stories, for editing.
- `.github/workflows/pages.yml`: publishes `site/` to GitHub Pages on every push to `main`.

No server, database, or API key. Hosting on GitHub Pages is free.

## Setup

1. Create a GitHub repository and push this folder to it.
2. In the repo, go to **Settings → Pages** and set Source to **GitHub Actions**.
3. Push to `main` (or run the workflow from the **Actions** tab). The site goes live at `https://<username>.github.io/<repo>/`.

## Custom domain (GoDaddy)

1. In GitHub **Settings → Pages → Custom domain**, enter your domain and save.
2. In GoDaddy **DNS → Manage DNS** for the domain:
   - Delete any existing `A` record for `@` and GoDaddy's "Parked" record if present.
   - Add four `A` records for `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Add a `CNAME` record: name `www`, value `<your-github-username>.github.io`
3. Wait for DNS (up to an hour), then tick **Enforce HTTPS** in GitHub Pages settings.

## Editing or adding stories

Edit `site/stories.js` directly. Each entry is `{ "title": "...", "body": "..." }`, with paragraphs separated by a blank line (`\n\n`). Add as many as you like; the page picks up the count automatically.
