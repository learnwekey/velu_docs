# Documentation evidence gaps

This file tracks documentation that is intentionally deferred because its
behavior is unsupported by available evidence or confidence is too low to make
a public claim.

Every entry records the topic, the exact gap, and the evidence needed to close
it. Product confirmation alone does not establish UI labels, workflows,
defaults, permissions, limits, errors, or recovery behavior.

## Customize

### Selectable themes

**Exact gap:** `velu-cli-main` 0.2.27 implements built-in light and dark modes, but contains no selectable theme catalog, theme configuration field, or theme-selection workflow.

**Evidence needed:** The available themes, selection and preview workflow, publish behavior, defaults, plan or role restrictions, and migration behavior.

### Custom domains

**Exact gap:** `velu-cli-main` contains no custom-domain schema field, dashboard flow, DNS requirements, verification process, or provisioning implementation.

**Evidence needed:** The dashboard workflow, required DNS records, ownership verification, TLS provisioning, status and error states, limits, and cutover or rollback behavior.

### Custom CSS and JavaScript

**Exact gap:** `velu-cli-main` contains no author-facing custom-code field, file convention, editor, or CSS/JavaScript injection mechanism.

**Evidence needed:** The configuration surface, file or editor workflow, load order and scope, preview behavior, CSP and security restrictions, size limits, validation, and recovery from invalid code.

### Custom 404 pages

**Exact gap:** `velu-cli-main` generates a standard `404.html`, but exposes no configuration or authoring workflow for replacing its content.

**Evidence needed:** How a custom page is created or selected, supported content and components, preview and publish behavior, routing precedence, and fallback behavior.

### Hosted SEO and social-output parity

**Exact gap:** The production build code generates metadata, Open Graph images, `sitemap.xml`, and `robots.txt`, but the resulting files and host-injected site origin have not been inspected on a Velu-hosted preview.

**Evidence needed:** A hosted preview where page source, canonical URLs, social images, sitemap entries, robots directives, and the injected production origin can be checked against the documented behavior.

## Organize

### Default expansion for navigation groups

**Exact gap:** The 0.2.27 schema accepts `group.expanded` and the navigation normalizer retains it, but the sidebar model does not consume the value. Only ancestor groups of the active page open automatically.

**Evidence needed:** A product decision defining the intended default-expansion behavior and a runtime implementation or test that demonstrates it.

### Navigation accent colors

**Exact gap:** The schema accepts `anchor.color` and `product.color`, but the rendered anchor list and product switcher do not apply those values in 0.2.27.

**Evidence needed:** A product decision defining where each color appears and a runtime implementation or visual test demonstrating the supported format and behavior.

### Hidden pages

**Exact gap:** Page frontmatter `hidden: true` affects build-time indexing metadata, but 0.2.27 does not remove the page from navigation or load unlisted MDX pages for direct routing.

**Evidence needed:** A product decision defining whether hidden means “not in navigation,” “not indexed,” or both, plus an implementation and routing test for the intended authoring workflow.

Do not add deferred features to public navigation or describe the missing
behavior until the required evidence is available and the resulting guidance
can be tested.

## Phase 3

### Intent or natural-language search

**Exact gap:** The repo proves page search with Pagefind, but it does not prove
the separate intent-ranking or natural-language search behavior promised by the
product matrix.

**Evidence needed:** The backend or dashboard workflow for intent search,
ranking behavior, query matching rules, limits, and any hosted configuration.

### `skill.md` generation

**Exact gap:** The build output emits `const.json` and `llms.txt`, but there is
no `skill.md` generation path or override mechanism in the repo.

**Evidence needed:** The file format, generation rule, default location, hosted
URL, override behavior, and a sample output.

### Analytics

**Exact gap:** The repository contains no analytics schema, dashboard contract,
or render hook that would let us describe metrics with confidence.

**Evidence needed:** Metric definitions, filters, retention, human versus agent
classification, access control, and the dashboard pages or API that surface the
data.
