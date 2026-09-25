# ML Notes

A simple, self-contained note-taking site for ML studies — sections and
nested sub-sections, theory text, code snippets with syntax highlighting,
and screenshots, with one-click PDF export. No build step, no backend —
it's a single HTML file that runs entirely in your browser and saves to
`localStorage`.

## Features

- **Hierarchy** — unlimited nested sections/sub-sections, collapsible tree
- **Rich content per section** — Text (light markdown: `#`/`##`/`###`, `**bold**`, `*italic*`, `` `code` ``, `-` lists), Code (with language picker, syntax highlighting, and a one-click Copy button), Image (upload screenshots/diagrams, auto-compressed)
- **Search** — matches section titles, text content, code content, and tags; matching sections stay visible with their parent sections expanded
- **Tags** — add free-form tags to any section, shown as chips in the note view and included in search
- **Favorites** — star any section (⭐) from the sidebar or the note view; favorites are marked in the tree
- **Learning status** — mark each section Learning / Understood / Review, shown as a colored dot in the tree (existing sections default to Learning)
- **Storage usage** — the sidebar shows an approximate `localStorage` usage estimate and warns when it's getting full
- **PDF export** — export a single section (with its sub-sections, headings, status/tags, and page numbers) or the whole notebook
- **Backup / restore** — download everything (including tags, favorites, and status) as JSON, restore it later or on another device
- **Light/dark theme**, works on mobile

All data stays in your browser's `localStorage` — no backend, login, or sync.

## Run it locally

Just open `index.html` in a browser — or, for the starter notes to load
correctly (browsers block `fetch` on `file://`), serve the folder:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy on GitHub Pages

1. Create a new GitHub repository and push these three files (`index.html`,
   `notes-data.json`, `README.md`) to the root of the `main` branch:

   ```bash
   git init
   git add .
   git commit -m "ML Notes"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```

2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`,
   branch `main`, folder `/ (root)`, then **Save**.
4. After a minute, your site is live at:
   `https://<your-username>.github.io/<repo-name>/`

## How your data works

Everything you type is saved in your browser's `localStorage` — it's
private to you and persists across visits, but it does **not** sync
between devices or browsers on its own. To carry notes over:

- Click **Download backup (JSON)** to save a snapshot, and **Restore backup**
  to load it back in (on this device or another).
- Optionally, overwrite `notes-data.json` in the repo with an exported
  backup and push it — new visitors (or a browser with no saved notes yet)
  will load that as their starting point.

## Notes on storage limits

`localStorage` is typically capped around 5–10MB per site. Screenshots are
auto-compressed on upload to keep things light, but if you add a lot of
large images, periodically download a backup and consider trimming older
screenshots.
