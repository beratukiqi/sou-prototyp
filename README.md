# My App

Static site hosting versioned HTML exports.

## Adding a new version

1. Create a new folder at the root: `v2/`, `v3/`, etc.
2. Put your exported HTML inside as `index.html` (e.g. `v2/index.html`).
3. Add an entry to `versions.json` at the **top** of the array (newest first):

   ```json
   {
     "id": "v2",
     "label": "v2",
     "date": "2026-06-01",
     "note": "What changed in this version"
   }
   ```

4. Commit and push. GitHub Pages will update in a minute or two.

The landing page reads `versions.json` and builds the list automatically. The first entry gets a "latest" badge.

## Fields

- `id` — folder name (required)
- `label` — display name (required)
- `date` — shown on the right (optional)
- `note` — small description under the label (optional)

## Local preview

Open `index.html` in a browser via a local server (not `file://`, or fetch will fail):

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```
