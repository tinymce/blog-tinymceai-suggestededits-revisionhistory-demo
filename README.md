# TinyMCE AI + Suggested Edits + Revision History Demo

This repo contains a lightweight, single-page TinyMCE demo showing [Suggested Edits](https://www.tiny.cloud/tinymce/features/suggested-edits/), [Revision History](https://www.tiny.cloud/tinymce/features/revision-history/), and [TinyMCE AI](https://www.tiny.cloud/tinymce/features/ai-content-editor/) working together, with AI-generated edits tagged as AI-assisted in both the review and version trail. This attribution shipped in TinyMCE 8.7 — see [What's New in TinyMCE 8.7](https://www.tiny.cloud/blog/whats-new-tinymce-8-7/) and the companion blog post, "How to Use TinyMCE AI with Suggested Edits and Revision History," for the full walkthrough.

## What's in here

- `index.html` — the demo page. There's no build step and no dependencies to install.
- `imgs/` — image assets used in the editor content and author avatars.

## Prerequisites

- Comfort with HTML and JavaScript.
- A TinyMCE API key with premium features, including TinyMCE AI. [Get a free 14-day API key](https://www.tiny.cloud/auth/signup/) if you don't have one.
- TinyMCE 8.7 or later — AI attribution for Suggested Edits and Revision History landed in 8.7.

## Setup

1. Clone this repo:

   ```shell
   git clone https://github.com/tinymce/blog-tinymceai-suggestededits-revisionhistory-demo.git
   cd blog-tinymceai-suggestededits-revisionhistory-demo
   ```

2. Open `index.html` and replace `no-api-key` in the TinyMCE script URL with your own API key.

## Run the demo locally

The editor content includes hosted images, so serve the folder rather than opening `index.html` directly from the file system. The quickest way is the [`http-server`](https://www.npmjs.com/package/http-server) npm package:

```shell
npm install -g http-server
```

Then, from this folder:

```shell
http-server
```

**Use `http://localhost:8080/`, not `http://127.0.0.1:8080/`.** `http-server` will print both, but `127.0.0.1` isn't an approved domain on the TinyMCE dashboard by default, while `localhost` is. You can add `127.0.0.1` to your approved domains if you'd rather use it, but `localhost` works out of the box.

## How it works

- `revisionhistory_fetch` reads from a mock revisions array rather than a live backend, so the page runs with no server-side setup. Each revision carries a `revisionId`, `createdAt`, `author`, and `content`.
- `user_id` and `fetch_users` identify whoever is currently editing, shared between Suggested Edits and Revision History.
- Adding `metadata: { source: 'ai' }` to a revision marks it AI-assisted and shows the AI badge in Revision History. Suggested Edits does this automatically for any edit made through TinyMCE AI — no extra configuration needed.
- Toggle `revisionhistory_ai_attribution` or `suggestededits_ai_attribution` to `false` to hide the AI badge in either plugin independently.

See the full guide, "How to Use TinyMCE AI with Suggested Edits and Revision History," on the [TinyMCE blog](https://www.tiny.cloud/blog/) for a step-by-step walkthrough of adding TinyMCE AI to an existing Suggested Edits + Revision History setup.

## License

MIT
