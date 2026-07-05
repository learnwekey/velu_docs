# Velu component preference

This note records the component choices I’m preferring for the docs that have
been written so far. The goal is to fit the component to the content instead of
using `Card` everywhere as a generic wrapper.

`Card` is still useful, but only when the content is a set of parallel options
or feature summaries that should scan quickly. For workflow, config, and
reference content, other components read better and carry more structure.

| Content type | Preferred component(s) | Why |
| --- | --- | --- |
| Step-by-step workflows | `Steps`, `Step` | They naturally express ordered actions and make progress obvious. |
| Configuration surfaces | `Field` | They mirror schema shape, defaults, and required values without extra visual noise. |
| Caveats and exceptions | `Callout`, `Accordion`, `AccordionGroup` | Warnings and edge cases should stand out, and collapsible details keep the page scannable. |
| Content maps and exports | `Tree`, `Folder`, `File` | They show hierarchy better than cards and are a good fit for navigation, file sets, and generated outputs. |
| Command-line examples and prompts | `Prompt` | Prompts should look like something a reader can copy into an AI tool or terminal workflow. |
| Code-focused examples | `CodeBlock`, `CodeGroup` | Raw code should read like code, not as a feature tile. |
| Product overviews with a few distinct choices | `Columns` + a small number of `Card`s | Cards work when the page is a scanable menu or landing-page summary. |
| Media, changelogs, or updates | `Image`, `Update` | These are content-specific components and should stay visually distinct. |
| API request and response shape | `Field`, `CodeBlock`, `ApiPath`, `MethodBadge` | API docs need structure, not marketing layout. |

Practical rule:

1. Start with the most specific component that matches the content.
2. Use `Card` only when the section is a comparison, choice set, or quick
   summary.
3. Use `Columns` to arrange content side by side, but let the inner component
   carry the meaning.
4. Use `Accordion` for details that should not dominate the main reading path.

Current bias by page type:

- Getting-started tutorials: `Steps`, `Callout`, `Prompt`, `Accordion`.
- API reference pages: `Field`, `CodeBlock`, `MethodBadge`, `ApiPath`.
- AI-native feature pages: `Steps`, `Field`, `Tree`, `Accordion`, with cards
  only for short overviews.
- Navigation and structure pages: `Tree`, `Field`, `Steps`.
- Styling and customization pages: `Field`, `Callout`, `Accordion`, plus a
  small number of cards when comparing options.

That is the default I’ll use going forward unless a page clearly benefits from a
different shape.
