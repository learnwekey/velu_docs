# Your documentation, powered by Velu

This repository is your documentation site, built with [Velu](https://getvelu.com).
Edit the Markdown, push to GitHub, and Velu builds and deploys your site
automatically — there's no build step to run yourself.

## Preview locally

Velu requires Node.js 20.9 or later.

```bash
npm install -g @aravindc26/velu   # one-time
velu run                          # start the local site
```

Open `http://localhost:4321`. The site reloads as you edit Markdown content or
`velu.json`.

## What's in here

| Path | What it is |
|---|---|
| `velu.json` | Site config — name, colors, logo, and the `navigation` tree |
| `index.mdx`, `quickstart.mdx` | Introduction and first-success workflow |
| `getting-started/` | Product workflow, local tooling, linting, and publishing guides |
| `essentials/`, `ai-tools/` | Grouped content pages |
| `openapi.json` | OpenAPI spec → an auto-generated API reference |
| `favicon.svg` | Your site's favicon |

## Editing

- **Write content** in Markdown, plus Velu components (Callout, CodeGroup, Card,
  and more) — see `essentials/markdown.mdx` for examples.
- **Add a page**: create a new `.md` or `.mdx` file, then reference its path under
  `navigation` in `velu.json`. Paths are relative to the repo root with no
  extension.
- **Customize** colors, logo, fonts, tabs, and the footer in `velu.json`.

Run `velu lint` to validate the configuration and referenced pages before you
push.

## Deploy

Push to this repo. Velu rebuilds and redeploys on every push — no extra steps.
