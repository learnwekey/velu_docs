# Velu documentation

This repository contains the product documentation for Velu. Pages are written
in MDX, site-wide behavior is configured in `velu.json`, and Velu publishes the
connected repository.

## Preview locally

Velu requires Node.js 18 or later.

```bash
npm install -g @veluai/velu   # one-time
velu dev .                    # start the local site
```

Open `http://localhost:8358`. The site reloads as you edit MDX content or
`velu.json`.

## What's in here

| Path | What it is |
|---|---|
| `velu.json` | Site config — name, colors, logo, and the `navigation` tree |
| `index.mdx`, `quickstart.mdx` | Introduction and first-success workflow |
| `getting-started/` | Product workflow, local tooling, validation, and publishing guides |
| `essentials/`, `components/`, `ai-tools/` | Authoring and product guides |
| `openapi.json` | OpenAPI spec → an auto-generated API reference |
| `favicon.svg` | Your site's favicon |

## Editing

- **Write content** in `.mdx` files using Markdown syntax and built-in Velu
  components. See `essentials/content-overview.mdx`.
- **Add a page**: create a new `.mdx` file, then reference its path under
  `navigation` in `velu.json`. Paths are relative to the repository root and
  omit the extension.
- **Customize** colors, logo, fonts, tabs, and the footer in `velu.json`.

Run `velu validate .` to validate the configuration and referenced pages before you
push.

## Deploy

Push to this repo. Velu rebuilds and redeploys on every push — no extra steps.
