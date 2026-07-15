# TinyMCE AI Edits Revisions Demo

This folder contains a lightweight TinyMCE demo page showing:

- the TinyMCE editor with AI review and suggested edits
- the Revision History plugin
- a simple per-user draft save flow using browser `localStorage`
- a small test-user switcher for previewing different author identities

## Files

- `index.html` — the demo page
- `Fashion-model.jpg` — sample image asset used in the editor content
- `dockock.jpg` — Doc Ock avatar asset
- `shehulk.jpg` — She-Hulk avatar asset
- `spiderman.jpg` — Spider-Man avatar asset
- `spider-gwen.png` — Spider-Gwen avatar asset

## Local usage

Open the page in a browser, or serve the folder locally with a simple static server:

```sh
python3 -m http.server 8000
```

Then visit:

```text
http://127.0.0.1:8000/
```

## Notes

- The demo is intentionally browser-local for simplicity.
- Drafts are saved per user in the browser using `localStorage`.
- The TinyMCE cloud script in `index.html` requires a valid TinyMCE API key in production use.
