# Velu Documentation Style Guide

This guide records the editorial and component usage decisions for the Velu
documentation. Update it whenever the team agrees on a new pattern. Public
pages should not invent a conflicting pattern without first updating this
guide.

## Writing goals

Velu documentation should help readers complete work accurately and quickly.
It should be understandable by developers, technical writers, product
managers, and AI agents without assuming they share the same product context.

## Voice and tone

- Address the reader as “you.”
- Use active voice and present tense.
- Start with the outcome, then provide context.
- Prefer direct verbs: “Add,” “Run,” “Open,” “Select,” and “Verify.”
- Keep sentences focused on one idea.
- Define product-specific terms on first use.
- Use “Velu” for the product and `velu` for local commands.
- Avoid promotional claims in tutorials, how-to guides, and reference pages.
- Do not use “easy,” “simple,” “obvious,” or “just.”
- Do not claim support, performance, security, or availability without a
  verified source.

## Titles and descriptions

- Use sentence case.
- Use task titles for procedures: “Configure API authentication.”
- Use noun titles for reference: “Navigation configuration.”
- Keep descriptions specific enough to distinguish the page in search.
- Do not repeat the title as the description.
- Do not add an `#` heading that duplicates the frontmatter `title`; Velu
  renders the page title.

## Headings

- Begin page sections with `##`.
- Use `###` only inside a `##` section.
- Use descriptive headings that remain meaningful out of context.
- Avoid headings such as “Overview,” “Details,” or “More information” when a
  more specific label is possible.
- Keep heading levels sequential.

## Procedures

- State the completed outcome before the steps.
- Put prerequisites before the procedure.
- Use `Steps` only when order matters.
- Give every `Step` an action-oriented title.
- Put one primary action in each step.
- Include a verification step or expected result.
- Put optional branches after the main successful path.
- Link to troubleshooting instead of interrupting the main flow with every
  edge case.

## Lists

- Use a numbered list for “Before you begin” requirements and “Next steps.”
- Use bullets for benefits, options, and other items where sequence does not
  matter.
- Verify that list markers are visible in the rendered page. The local preview
  theme may reset default browser markers, so set an explicit `listStyleType`
  in MDX when required.

## Code and commands

- Use the correct language identifier on every fenced block.
- Make examples runnable when the product permits it.
- Use `your-login` for a Git account and `your-docs-repo` for a documentation
  repository. Use environment-variable placeholders for credentials.
- Never include working credentials, personal paths, or tenant identifiers.
- Explain where a command must be run.
- State expected output when it helps readers verify success.
- Use a `CodeGroup` only for equivalent alternatives.
- Keep all alternatives in a `CodeGroup` behaviorally equivalent.
- Use `filename` for a file label and `title` for a grouped alternative.
- Use line highlighting only when the surrounding example needs focus.

## Links

- Use descriptive link text that states the destination.
- Prefer repository-relative links for documentation pages.
- Link once at the point where the reader needs the destination.
- Do not use “click here” or expose raw URLs in prose unless the URL itself is
  the subject.
- Verify external links before publication.

## Images and media

- Use an image when spatial UI context is necessary to complete a task.
- Do not use screenshots to communicate text that can be written and searched.
- Provide meaningful `alt` text, or an empty `alt` only for decorative images.
- Describe the task-relevant state, not every visible interface element.
- Crop images to the relevant product area and remove sensitive data.
- Prefer durable interface landmarks over pixel-specific instructions.

## Component usage

### `Callout`

Use a callout for information the reader could miss and that materially
changes understanding, success, risk, or safety. Do not use callouts for
ordinary paragraphs.

| Type | Use |
| --- | --- |
| `note` | A constraint or behavior that affects the current task. |
| `info` | Background information needed to interpret the surrounding content. |
| `tip` | An optional improvement or faster workflow. |
| `check` | A success condition or recommended verification. |
| `warning` | A likely failure, compatibility issue, or recoverable risk. |
| `danger` | Security risk, data loss, destructive action, or difficult rollback. |
| `callout` | General emphasis that does not fit a semantic status above. Use sparingly. |

Keep required actions in the main text even when a warning reinforces them.

### `Steps` and `Step`

Use for dependent actions that must be completed in order. Use a normal list
for independent items, requirements, or unordered choices.

### `Card` and `CardGroup`

Use cards on landing pages to present a small set of meaningful destinations
or next actions. A Velu card is not itself clickable; add an explicit `cta`
when navigation is intended. Do not turn ordinary bullet lists into cards.

### `Accordion` and `AccordionGroup`

Use accordions for optional details, advanced variations, long examples, or
secondary troubleshooting. Do not hide prerequisites, the primary procedure,
security warnings, or information required to choose correctly.

Use `AccordionGroup` when multiple adjacent disclosures form one set.

### `Columns`

Use columns for short, parallel choices or balanced examples. Do not use them
for sequential instructions or long text that becomes difficult to scan on
narrow screens.

### `CodeBlock` and `CodeGroup`

Use a standalone code block for one implementation. Use a code group for
equivalent languages, package managers, or frameworks. A code group must not
split consecutive steps into tabs.

### `Prompt`

Use for a complete AI instruction that readers can copy without reconstructing
missing context. State the expected result before the prompt and tell readers
what must be reviewed before accepting generated changes.

### `Field`

Use for configuration properties, API parameters, and response fields. Keep
conceptual prose outside field lists. Include name, type, required status, and
default only when verified.

### `ApiPath` and `MethodBadge`

Use only for real HTTP endpoints. Do not use them as decorative labels for
commands, routes that are not APIs, or unapproved future endpoints.

### `Tree`, `Folder`, and `File`

Use for meaningful file or directory structures. Keep trees focused on the
paths discussed by the page; omit unrelated generated files.

### `Image`

Use `chrome="window"` for browser screenshots and `chrome="frame"` only for
content that benefits from a device-like frame. Use plain images for diagrams
and assets. Supply `alt` text or a descriptive string caption.

### `Update`

Use for dated product changes and changelog entries, not undated notices or
ordinary feature descriptions. The complete public property contract must be
verified before the component reference page is written.

## Landing pages

A section landing page should contain:

1. A short explanation of the section's user value.
2. A recommended starting point.
3. Task-oriented cards for the main destinations.
4. No long procedure that belongs on a dedicated page.

## Reference pages

- Be complete rather than narrative.
- State accepted values exactly, including case sensitivity.
- State defaults, inheritance, and scope.
- Separate verified behavior from recommendations.
- Include one minimal example and one complete example when useful.
- Document errors and constraints next to the relevant field.

## Accessibility and AI retrieval

- Use semantic headings and visible text labels.
- Do not encode meaning only with color, position, or icons.
- Keep critical content outside collapsed components.
- Write self-contained sections with explicit nouns instead of vague pronouns.
- Define abbreviations on first use.
- Give code examples enough surrounding context to identify their purpose.
- Use meaningful alternative text and link text.

## Page review checklist

- Is the reader and task clear?
- Is every product claim verified?
- Are prerequisites and permissions stated?
- Can the reader verify the result?
- Are examples current and safe?
- Are components used according to this guide?
- Are important details visible rather than hidden?
- Are headings useful in search results and AI excerpts?
- Do all links resolve?
- Does `velu lint` pass?
