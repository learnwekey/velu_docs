# Velu Documentation Plan

## Objective

Build task-oriented product documentation for Velu that helps users publish,
operate, and improve an AI-native documentation site. Mintlify is an
information-architecture benchmark, but its wording and feature claims will
not be copied.

Every Velu claim must be supported by one of these sources of truth:

1. Product or platform implementation.
2. The published `@aravindc26/velu` package and npm documentation.
3. The supported `velu.json` schema.
4. A working dashboard or hosted-site flow.
5. An approved API specification or product decision.

## Domain decision

- Current documentation domain: `https://docs.getvelu.com`.
- Intended final location: `https://veludocs.com/doc`.
- Redirects, canonical URLs, and the migration plan will be handled near
  launch.
- The hosted platform configuration for the temporary domain must be verified
  separately from this repository.

## Audience and primary workflow

- Velu documentation serves both developers and documentation authors who
  prefer a dashboard editor.
- Docs-as-code is the primary and recommended workflow.
- The recommended authoring path uses terminal tools with AI coding agents
  such as Codex or Claude Code.
- The dashboard editor is a supported alternative for authors who prefer a
  browser-based workflow and does not require a Git connection.
- The initial onboarding sequence is: sign up, enter the dashboard, and choose
  either the terminal/agent workflow or the dashboard editor.
- A connected documentation Git repository is required for docs-as-code,
  Git-based automation, and self-updating documentation.
- The quickstart presents the dashboard editor and docs-as-code as two complete
  paths with their requirements stated before either procedure.

## Documentation principles

1. Organize documentation around user outcomes, not internal architecture.
2. Get a new user to a successful published edit before introducing advanced
   configuration.
3. Separate tutorials, how-to guides, explanations, and reference pages.
4. Keep procedures executable and examples realistic.
5. Keep critical instructions visible; do not hide prerequisites or warnings
   in accordions.
6. Write self-contained sections that work for human readers, search, and AI
   retrieval.
7. Do not publish planned or marketed capabilities as available until their
   behavior is verified.

## Proposed information architecture

```text
Documentation
├── Get started
│   ├── Introduction
│   ├── Quickstart
│   ├── How Velu works
│   └── Migrate existing documentation
│
├── Create content
│   ├── Content overview
│   ├── Pages and frontmatter
│   ├── Markdown and text
│   ├── Code examples
│   ├── Images and media
│   └── Reusable content
│
├── Organize
│   ├── velu.json overview
│   ├── Navigation
│   ├── Tabs, groups, pages, and anchors
│   ├── Products
│   ├── Versions
│   └── Languages
│
├── Customize
│   ├── Docs site structure
│   ├── Appearance and themes
│   ├── Colors, fonts, logo, and favicon
│   ├── Custom domains
│   ├── Custom CSS and JavaScript
│   └── Custom 404 page
│
├── Document APIs
│   ├── API documentation overview
│   ├── OpenAPI setup
│   ├── Organize API operations
│   ├── Configure authentication
│   ├── API playground
│   ├── Proxy configuration
│   ├── Manual API pages
│   └── Troubleshooting
│
├── Develop and publish
│   ├── Install Velu
│   ├── Preview locally
│   ├── Validate documentation
│   ├── Deploy from Git
│   ├── Preview deployments
│   └── Deployment troubleshooting
│
├── AI-native features
│   ├── Overview
│   ├── Ask Velu and intent search
│   ├── Docs agent
│   ├── Contextual menu
│   ├── llms.txt
│   ├── skill.md
│   └── MCP
│
├── Optimize
│   ├── Analytics overview
│   ├── Human and agent traffic
│   ├── Page engagement
│   └── Search performance
│
└── Reference
    ├── Local commands
    ├── velu.json schema
    ├── Page frontmatter
    ├── Supported file types
    ├── Errors and limits
    └── Troubleshooting

Components
├── Overview
├── Layout and navigation
│   ├── Card and CardGroup
│   ├── Columns
│   ├── Steps and Step
│   └── Tree, Folder, and File
├── Emphasis and disclosure
│   ├── Callout
│   ├── Accordion
│   └── AccordionGroup
├── Code and AI
│   ├── CodeBlock and CodeGroup
│   └── Prompt
├── Media and updates
│   ├── Image
│   └── Update
└── API documentation
    ├── Field
    ├── MethodBadge
    └── ApiPath

API Reference
└── Velu's public API, generated from an approved OpenAPI specification
```

Only verified features will be added to public navigation. Hosted-only
features can be added after their dashboard and production behavior are
confirmed.

## Page-writing model

### Tutorials

Learning-oriented, end-to-end experiences that give a new user a working
result.

### How-to guides

Task-oriented procedures for readers who already understand the relevant
concepts.

### Explanations

Conceptual pages covering mental models, architecture, and product behavior.

### Reference

Complete descriptions of commands, configuration properties, component
properties, defaults, constraints, errors, and limits.

## Standard page structures

### Procedure

1. One-sentence outcome.
2. The result the reader will have when finished.
3. Prerequisites.
4. Ordered actions.
5. Verification.
6. Common failure cases.
7. Next steps.

### Component reference

1. What the component does.
2. When to use it.
3. When not to use it.
4. Minimal syntax.
5. Supported properties and defaults.
6. Basic example.
7. Realistic example.
8. Accessibility and AI-readability considerations.
9. Related components.

### Configuration reference

1. Purpose and scope.
2. Valid location in `velu.json`.
3. Field definitions.
4. Defaults and inheritance.
5. Complete example.
6. Constraints and errors.
7. Related configuration.

## Delivery phases

### Phase 0: Product truth and governance

- Create a feature-to-source-of-truth matrix.
- Verify commands, configuration, components, defaults, and limits.
- Record hosted features that require platform evidence.
- Establish the writing and component usage guide.
- Record the temporary domain decision.
- Separate production documentation from test and speculative content.

Phase 0 establishes feature availability and documentation governance. Exact
hosted UI steps, permissions, limits, and failure behavior will be verified
when the corresponding page is drafted; full backend access is not a Phase 0
requirement.

### Phase 1: First successful experience

Rewrite or add:

- Introduction.
- Quickstart.
- How Velu works.
- Docs site structure.
- Velu installation.
- Local preview.
- Validation.
- Deployment.

The quickstart must take a new user from the supported starting point to a
published edit without requiring another page.

**Status:** Implemented. The introduction and quickstart were rewritten, and
pages were added for the product workflow, docs site structure, Velu installation,
local preview, validation, and deployment. Static validation passes. Exact
dashboard labels and screenshots remain subject to review against the hosted
interface.

### Phase 2: Core authoring platform

Document pages, frontmatter, Markdown, code, media, navigation, configuration,
customization, and every confirmed author-facing component.

**Status:** On hold as of July 3, 2026. Resume after confirming which package
defines the current product contract: `@aravindc26/velu` 0.13.24 or
`@veluai/velu` 0.2.25. Phase 1 currently documents the former, while the local
preview environment runs the latter. Their configuration schemas and component
contracts differ, so Phase 2 must not mix the two implementations.

### Phase 3: Product differentiators

Document the API playground, OpenAPI, Ask Velu, intent search, the docs agent,
the contextual menu, `llms.txt`, `skill.md`, MCP, and analytics. Product
availability is confirmed; exact workflows, permissions, defaults, limits,
and failure states must still be verified while drafting each page.

### Phase 4: Complete reference

Add the `velu.json` schema reference, command reference, component property
reference, error catalog, troubleshooting, and a real Velu API reference if a
public API is supported.

### Phase 5: Quality and launch

- Run `velu lint`.
- Test every command and example.
- Test internal and external links.
- Review desktop and mobile rendering.
- Check accessibility and alternative text.
- Remove duplicate and unsupported claims.
- Verify page sequence and next actions.
- Verify human, search, and AI retrieval quality.
- Configure redirects and canonical URLs for the final domain move.

## Definition of done for a page

A page is complete only when:

- Its behavior is verified against an approved source of truth.
- Its title and description are unique and task-specific.
- Its examples are executable or clearly identified as illustrative.
- Required prerequisites and permissions are stated.
- The result can be verified by the reader.
- Likely failure modes are covered or linked.
- Components follow `DOCUMENTATION_STYLE_GUIDE.md`.
- Links, headings, code language labels, and alternative text are valid.
- The page has an appropriate next action.
- `velu lint` passes.

## Initial repository findings

- The repository currently contains starter content rather than complete
  product documentation.
- `new-page-test.mdx` is a component test fixture and must not be in public
  navigation.
- The example `openapi.json` describes a DummyJSON product catalog, not the
  Velu API.
- The unsupported `api-reference/writing-api.mdx` draft has been deleted.
- The public package is `@aravindc26/velu`. Its documented commands are
  `init`, `lint`, `run`, and `build`.
- The public package requires Node.js 20.9 or later and serves the local site
  on port 4321 by default.
- Some public marketing claims are hosted-platform features and cannot be
  proven from this documentation repository alone.

## Phase 0 decisions

- Docs-as-code is the recommended workflow for both developers and technical
  documentation authors.
- Codex and Claude Code are first-class authoring workflows.
- The dashboard editor is a supported alternative.
- Users can enter the dashboard and publish from the web editor without
  connecting Git. Git is required only for docs-as-code, automation, and
  self-updating documentation.
- The hosted features listed in this plan are available. Their detailed
  contracts will be verified during page drafting.
- The Writing API is not a supported product feature and must not appear in
  the documentation.
- MDX Tabs and Mermaid documentation is deferred until their implementation
  is revisited.

## Governance artifacts

- `PRODUCT_CAPABILITY_MATRIX.md`: what is verified, provisional, or blocked.
- `DOCUMENTATION_STYLE_GUIDE.md`: writing, page, and component usage rules.
- `DOCUMENTATION_PLAN.md`: scope, sequence, and definition of done.
