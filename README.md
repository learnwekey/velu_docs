# Your documentation, powered by Velu

This repository is your documentation site, built with [Velu](https://getvelu.com).
Edit the Markdown, push to GitHub, and Velu builds and deploys your site
automatically — there's no build step to run yourself.

## Preview locally

```bash
npm install -g @veluai/velu   # one-time
velu dev                      # start the live preview
```

Open the URL it prints. The preview live-reloads as you edit content or
`velu.json`.

## What's in here

| Path | What it is |
|---|---|
| `velu.json` | Site config — name, colors, logo, and the `navigation` tree |
| `index.mdx`, `quickstart.mdx`, `development.mdx` | Top-level pages |
| `essentials/`, `ai-tools/` | Grouped content pages |
| `api-reference/openapi.json` | OpenAPI spec → an auto-generated API reference |
| `favicon.svg` | Your site's favicon |

## Editing

- **Write content** in Markdown, plus Velu components (Callout, CodeGroup, Card,
  and more) — see `essentials/markdown.mdx` for examples.
- **Add a page**: create a new `.mdx` file, then reference its path under
  `navigation` in `velu.json`. Paths are relative to the repo root with no
  extension (e.g. `"essentials/markdown"` → `essentials/markdown.mdx`).
- **Customize** colors, logo, fonts, tabs, and the footer in `velu.json`.

Run `velu validate` to check your config and content before you push.

## Deploy

Push to this repo. Velu rebuilds and redeploys on every push — no extra steps.
