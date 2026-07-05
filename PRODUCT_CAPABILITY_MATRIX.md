# Velu Product Capability Matrix

This is the Phase 0 evidence inventory for documentation work. It prevents
sample content, marketing copy, and planned features from being presented as
supported product behavior.

## Status definitions

- **Verified**: supported by the public npm package, schema, product behavior,
  or a working repository check.
- **Partially verified**: the local implementation exists, but hosted behavior
  or a user flow still needs evidence.
- **Product confirmed**: the product owner confirms the hosted capability is
  available, but its exact UI, defaults, permissions, limits, and error
  behavior still require evidence before detailed documentation is published.
- **Needs product evidence**: requires access to the hosted platform,
  dashboard, backend, API specification, or owning product repository.
- **Conflict**: published wording and the inspected implementation do not yet
  agree.
- **Package limitation**: the current published package does not enforce or
  expose the complete intended behavior.
- **Fixture only**: sample or test content that must not be described as a Velu
  product API.

## Public package baseline

- Documentation repository at the current workspace revision.
- Public package: `@veluai/velu` 0.2.25, confirmed against the npm registry on
  July 4, 2026.
- Node.js requirement: 18 or later.
- Public commands: `velu init`, `velu dev`, `velu validate`, and `velu update`.
- Default local URL: `http://localhost:8358`; set `PORT` to override it.
- Navigated authored pages resolve to `.mdx` files.
- The public CLI does not expose a standalone production-build command.

## Package contract decision

- The product owner selected `@veluai/velu` as the authoritative package.
- Phase 1 and Phase 2 target `@veluai/velu` 0.2.25.
- Claims from `@aravindc26/velu` are not carried forward unless independently
  supported by the current package or hosted product evidence.

## Confirmed product decisions

- The documentation serves both developers and dashboard-oriented authors.
- Docs-as-code is the recommended workflow, with Codex and Claude Code as
  first-class authoring tools.
- Users sign up and enter the dashboard before choosing the terminal/agent
  workflow or dashboard editor.
- The dashboard editor does not require a Git repository. A connected
  documentation repository is required for docs-as-code, Git-based automation,
  and self-updating documentation.
- All hosted features named in the documentation plan are currently
  available.
- The Writing API is not a product feature and its draft page is deleted.
- MDX Tabs and Mermaid are deferred and will not be documented in the current
  pass.

## Core authoring and local tooling

| Capability | Status | Evidence | Documentation action |
| --- | --- | --- | --- |
| Scaffold a project | Verified | Public package documentation: `velu init` | Documented in Phase 1. |
| Run locally | Verified | Package README and CLI: `velu dev [directory]` | Documented with port 8358 and the `PORT` environment variable. |
| Validate a project | Verified | CLI: `velu validate [directory]` | Documented as the pre-publish check, including its validation categories. |
| Detect every unknown configuration field | Package limitation | Installed 0.2.25 accepted the legacy `url` field even though the packaged schema disallows it | Keep `$schema` configured for editor checks and document the validator limitation. |
| Build a static site from the CLI | Verified as not exposed | Public CLI command registry contains no build command | Removed old static-build guidance; production builds remain a hosted workflow. |
| Node.js requirement | Verified | Package README requires Node.js 18+ | Documented in installation and quickstart. |
| MDX content | Verified | Navigation resolution appends `.mdx`; compiler enables Markdown and GitHub Flavored Markdown | Documented in Phase 2; `.md` files are not presented as navigable source pages. |
| Live reload | Verified | Public package documentation | Documented in Phase 1. |
| Dashboard publishing without Git | Product confirmed | Product owner confirms the dashboard and web editor are available without connecting a repository | Documented as a standalone quickstart and publishing workflow; verify exact UI labels and states while drafting. |
| Git-triggered production deployment | Product confirmed | Repository connection and hosted deployment are part of the product flow | Verify supported Git providers, production branch behavior, and deployment states while drafting. |
| Preview deployments | Product confirmed | Product owner confirms availability; this is a hosted workflow | Verify platform flow, permissions, URL lifetime, and branch behavior while drafting. |

## Site configuration

| Capability | Status | Evidence | Documentation action |
| --- | --- | --- | --- |
| Project name | Verified | `velu.json` schema | Documented as required. |
| Primary/light/dark colors | Verified | Schema and runtime | Documented with inheritance and examples. |
| Font family | Verified | Schema; Google Fonts runtime loading | Documented with network implications. |
| Favicon | Verified | Schema and dev server | Documented with project-relative paths and formats. |
| Light/dark logos | Verified | Schema and runtime | Documented in string and object forms. |
| Navbar links and primary CTA | Verified | Schema and runtime | Documented with button and GitHub variants. |
| Footer links and socials | Verified | Schema and runtime | Documented with recognized social icons and four-column maximum. |
| SEO metatags and indexing | Verified | Schema and production build implementation | Documented from code; verify the resulting hosted output before freezing the page. |
| Open Graph thumbnails | Verified | Schema and production build implementation | Documented from code; verify generated images on a hosted preview before freezing the page. |
| Contextual menu | Verified | Schema and runtime | Document supported built-in and custom actions. |
| Ask AI configuration | Partially verified | Schema and runtime support `apiBase`, `host`, and `suggestions` | Verify hosted injection, tenancy, billing, and availability. |
| Canonical site URL | Needs product evidence | The temporary domain is confirmed, but hosted configuration is outside this repository | Verify where `docs.getvelu.com` is configured. |
| Custom domain | Product confirmed | Product-owner statement only; absent from the local schema and runtime | Excluded pending the evidence listed in `DOCUMENTATION_EVIDENCE_GAPS.md`. |
| Custom CSS and JavaScript | Product confirmed | Product-owner statement only; absent from the local schema and runtime | Excluded pending the evidence listed in `DOCUMENTATION_EVIDENCE_GAPS.md`. |
| Custom 404 page | Product confirmed | Product-owner statement only; local runtime proves only the standard 404 | Excluded pending the evidence listed in `DOCUMENTATION_EVIDENCE_GAPS.md`. |
| Selectable themes | Product confirmed | Product-owner statement only; local runtime proves only built-in light and dark modes | Excluded pending the evidence listed in `DOCUMENTATION_EVIDENCE_GAPS.md`. |

## Navigation

| Capability | Status | Evidence | Documentation action |
| --- | --- | --- | --- |
| Pages and nested groups | Verified | Schema and navigation implementation | Paths, nesting, ordering, and group landing pages are documented; `expanded` is excluded pending runtime evidence. |
| Tabs | Verified | Schema and navigation implementation | Documented for internal containers and external `href` tabs. |
| Anchors | Partially verified | Labels, icons, links, and active-scope rendering are implemented; `color` is not rendered | Documented without color; track the mismatch in `DOCUMENTATION_EVIDENCE_GAPS.md`. |
| Products | Partially verified | Switching, URL prefixes, names, and icons are implemented; `color` is not rendered | Documented without color; track the mismatch in `DOCUMENTATION_EVIDENCE_GAPS.md`. |
| Versions | Verified | Schema and URL prefix implementation | Documented with URL-change warnings. |
| Languages | Verified | Schema; ISO 639-1 names are resolved by runtime | Documented with codes, defaults, and URL behavior. |
| OpenAPI on tabs and groups | Verified | Schema and OpenAPI navigation generator | Navigation behavior documented in Phase 2; full API workflows remain Phase 3. |
| Dropdown navigation | Verified as unsupported | Schema description explicitly says dropdowns are unsupported | Do not include in public usage guidance. |
| Hidden pages | Package limitation | `hidden` changes build-time indexing metadata but does not hide navigation; only navigated MDX pages are loaded | Do not document a hidden-page workflow; track the intended behavior in `DOCUMENTATION_EVIDENCE_GAPS.md`. |

## Components

| Capability | Status | Evidence | Documentation action |
| --- | --- | --- | --- |
| `Callout` | Verified | Runtime and component prop validator | Documented with seven types and custom icon/color behavior. |
| `Accordion`, `AccordionGroup` | Verified | Runtime | Documented as standalone and grouped disclosure. |
| `Card`, `CardGroup` | Verified | Runtime | Documented as static cards with explicit CTA links. |
| `Columns` | Verified | Runtime | Documented with responsive column behavior. |
| `Field` | Verified | Runtime | Documented for configuration and API reference use. |
| `Prompt` | Verified | Runtime | Documented with string-child, preview, copy, and Cursor behavior. |
| `Steps`, `Step` | Verified | Runtime | Documented for dependent procedures. |
| `Tree`, `Folder`, `File` | Verified | Runtime | Documented for file and directory structures. |
| `Update` | Verified | Runtime and TOC extraction | Documented with labels, tags, anchors, and changelog behavior. |
| `Image` | Verified | Runtime; `src` is required | Documented with captions, alternative text, and chrome variants. |
| `CodeBlock`, `CodeGroup` | Verified | Runtime | Documented with labels, languages, line numbers, highlights, icons, and groups. |
| `MethodBadge`, `ApiPath` | Verified | Runtime and prop validator | Documented for real endpoint references. |
| `TryItBar`, `ApiField`, `ApiClient`, `ApiSidebar` | Verified as internal | Registered components used by generated API runtime | Classified as API-runtime primitives, not public Phase 2 authoring components. |
| Tabs component inside MDX | Deferred | Deferred by product decision | Skip in the current documentation pass and revisit later. |
| Mermaid | Deferred | Deferred by product decision | Skip in the current documentation pass and revisit later. |

## API documentation

| Capability | Status | Evidence | Documentation action |
| --- | --- | --- | --- |
| OpenAPI 3 and Swagger parsing | Verified | Runtime uses Swagger Parser and supports OpenAPI/Swagger fields | Define officially supported versions before writing the compatibility promise. |
| Local and remote specifications | Verified | Schema accepts paths or URLs, including arrays | Document path and URL behavior. |
| Automatic operation pages | Verified | Navigation generator creates pages grouped by first tag | Document grouping and generated routes. |
| Request samples | Verified | cURL, JavaScript, Python, and Ruby generators | Document language configuration. |
| Interactive playground | Verified locally | API client and dev proxy are implemented | Verify hosted proxy, CORS, security, and credential handling. |
| Authentication fields from OpenAPI | Verified | Runtime maps bearer, basic, API key, OAuth2, and OpenID Connect schemes | Verify which schemes can be executed successfully in hosted playgrounds. |
| Current `openapi.json` | Fixture only | Describes a DummyJSON product catalog | Present only as a clearly labelled demonstration. |
| Velu Writing API | Not supported | Product owner confirmed the draft was not a real product API | Draft page deleted; do not document. |
| Public Velu API | Deferred | No approved Velu OpenAPI document is available here | Keep out of launch scope unless an approved specification is provided. |

## AI, search, and optimization

| Capability | Status | Evidence | Documentation action |
| --- | --- | --- | --- |
| Page search | Verified | Runtime integrates Pagefind | Document user-visible search after hosted parity is checked. |
| Intent or natural-language search | Product confirmed | Product owner confirms availability; not established by Pagefind alone | Verify backend behavior, ranking, limits, and dashboard configuration while drafting. |
| Ask Velu | Product confirmed | Runtime chatbot and hosted API configuration exist; product owner confirms hosted availability | Verify complete hosted user and admin flows while drafting. |
| Contextual AI actions | Verified locally | Schema lists built-in AI, IDE, copy, spec, PDF, and MCP actions | Verify which actions are available by plan and deployment type. |
| `llms.txt` and `llms-full.txt` | Verified | Dev server generates both endpoints and Markdown page twins | Document generation, indexing rules, and hosted parity. |
| `skill.md` generation | Product confirmed | Product owner confirms hosted availability | Verify generation rules, override behavior, and URL while drafting. |
| MCP | Product confirmed | Product owner confirms availability; context menu options exist locally | Verify endpoint, authentication, tools, and client setup while drafting. |
| Docs agent | Product confirmed | Product owner confirms hosted availability | Verify supported sources, review flow, permissions, and PR behavior while drafting. |
| Page feedback | Partially verified | Runtime feedback UI and client wiring exist | Obtain dashboard behavior, retention, and permissions. |
| Analytics | Product confirmed | Product owner confirms availability; dashboard/backend not available here | Verify metric definitions, filters, retention, and human/agent classification while drafting. |

## Current content disposition

| Content | Current role | Phase 0 disposition |
| --- | --- | --- |
| `index.mdx` | Product introduction | Rewritten in Phase 1 around the repository, local tooling, and hosted workflow. |
| `quickstart.mdx` | End-to-end onboarding | Rewritten in Phase 1 with independent dashboard editor and docs-as-code paths. |
| `development.mdx` | Superseded starter page | Deleted and replaced by focused pages under `getting-started/`. |
| `getting-started/*.mdx` | First-success guidance | Added in Phase 1 for workflow, structure, installation, preview, validation, and deployment. |
| `essentials/*.mdx` | Core authoring documentation | Rewritten and expanded in Phase 2. |
| `components/*.mdx` | Author-facing component reference | Added in Phase 2; API-runtime primitives are explicitly excluded. |
| `ai-tools/*.mdx` | Generic editor suggestions | Reassess after the first-party AI workflow is defined. |
| `api-reference/introduction.mdx` | Dummy API explanation | Keep only as an explicitly labelled OpenAPI demonstration. |
| `api-reference/writing-api.mdx` | Unsupported API draft | Deleted by product decision. |
| `new-page-test.mdx` | Component test fixture | Remove from public navigation; retain locally until a replacement component test page exists. |

## Evidence required during page drafting

1. Exact dashboard labels, steps, states, and screenshots.
2. Git provider, production branch, preview, and deployment behavior.
3. Plan, role, and permission boundaries for hosted features.
4. Defaults, limits, errors, and recovery paths for hosted features.
5. Product-owned definitions for analytics, agent, MCP, `skill.md`, custom
   domains, themes, CSS/JS, and preview deployments.

This evidence can come from a test account, screenshots, a short product
walkthrough, or the relevant implementation. Full backend repository access is
not required if another source demonstrates the complete user-visible
contract.
