# Velu documentation audit handoff

Saved July 4, 2026 for the next documentation session.

## Agreed sources of truth

- Use `velu-cli-main` as the current product codebase and primary source.
- Use the published `@veluai/velu@0.2.25` package as the published baseline and shipped product experience.
- When the two conflict, `velu-cli-main` takes precedence for current behavior.
- Product evidence includes implementation, schemas, runtime behavior, integration protocols, comments, Velu-specific UI copy, and starter templates.
- Do not infer that a hosted feature is unsupported merely because its dashboard or backend implementation is not inside the CLI package.
- Do not invent UI labels, limits, permissions, error states, or workflows not stated by either source.
- Do not convert explicit fixtures into Velu product claims. Examples include the Mintlify deployment API component demo and the DummyJSON OpenAPI starter specification.

## Correction to the previous audit

The earlier classification of dashboard editing, publishing, repository synchronization, and hosted deployment as broadly unsupported was too restrictive and is withdrawn. These areas must be reassessed using the combined evidence model above.

## Confirmed audit items to revisit

- Reconcile documentation written for `0.2.25` with the current `velu-cli-main` version and behavior.
- Correct the documented behavior of `velu validate`.
- Expand the Pages guide with supported frontmatter and SEO fields.
- Document `TryItBar`, `ApiField`, `ApiClient`, and `ApiSidebar` as author-usable components unless the core registry changes.
- Correct the claim that `Image.src` is statically enforced by `velu validate`.
- Correct the `Update.rss` description: the prop is ignored and RSS generation includes all literal `Update` entries.
- Cover missing CLI, local-preview, Markdown-export, `llms.txt`, RSS, search, Ask AI, contextual-action, and feedback behavior where appropriate.
- Keep Components nested under Create Content rather than making Components a separate top-level tab.

## Next action

Redo the Phase 1 and Phase 2 audit using this combined evidence model before changing documentation.
