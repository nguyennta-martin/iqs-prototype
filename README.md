# IQS Prototype

Static UI prototype for the IQS (Intelligent Quotation System) — generated in
Claude Web and hosted on GitHub Pages so the client always has **one stable link**.

- **Live URL:** https://nguyennta-martin.github.io/iqs-prototype/
- **What it is:** a single self-contained `index.html` (all CSS/JS inlined, mock
  data only — no backend, no API calls, no secrets).
- **What it is *not*:** not a working system. It's a clickable mockup for client
  feedback. Real behaviour lives in the actual IQS build, not here.

## Updating the prototype

When Claude Web produces a new version, replace `index.html` and push. The URL
never changes — only the content behind it does.

### Option A — GitHub web UI (no terminal)
1. Open this repo on github.com.
2. **Add file → Upload files**, drop in the new HTML (rename it to `index.html`).
3. **Commit changes** to `main`. Live in ~1 minute.

### Option B — Local (Mac or Windows)
```bash
cd iqs-prototype        # wherever you cloned it
cp <new_version>.html index.html
git add index.html
git commit -m "Update prototype"
git push
```

> Keep the filename `index.html` at the repo root, or the site's base URL 404s.

## Hosting notes

- **Pages source:** Deploy from branch `main`, folder `/ (root)`
  (repo → Settings → Pages).
- **`.nojekyll`** — serves the HTML as-is; disables Jekyll so `{{ }}`/`{% %}` in
  the file can't be mis-parsed.
- **`noindex` meta tag** — keeps the prototype out of search engines. The link is
  public-but-unlisted, not login-gated. Don't put anything confidential in it.

## Cross-machine (Mac / Windows)

- `.gitattributes` normalizes line endings (`eol=lf`) so switching laptops
  doesn't create phantom diffs. If you see a one-time "everything changed" diff
  after cloning, run `git add --renormalize .` once and commit.
- `.gitignore` excludes JetBrains (`.idea/`), OS cruft, and Claude Code
  (`.claude/`) files.
