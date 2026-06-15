---
name: cards
description: "Create PNG information cards from content using a stripped-down ljg-card -i workflow. Use when the user asks to make content into a card, information card, infographic, analysis graphic, framework diagram, business model card, strategy card, visual explanation, method introduction, or method-applied-to-industry analysis. Outputs a PNG from an HTML template. This skill has no built-in footer, author signature, logo, or source line."
---

# cards

Turn content into a PNG information card. This skill keeps the original `ljg-card -i` information-graph workflow, removes the built-in footer/signature area, and adds two explicit modes:

- **Method Intro**: explain a tool, method, model, or framework.
- **Industry Application**: apply a tool, method, model, or framework to a specific industry, company, product, market, or scenario.

## Inputs

Accept one of:

- A short topic.
- A method plus a domain.
- Pasted text.
- A URL fetched by the assistant.
- A local file path read by the assistant.

## Output

Create:

- An HTML file using `assets/infograph_template.html`.
- A PNG screenshot rendered from that HTML.

Default render command:

```bash
node assets/capture.js <html> <png> 1080 800 fullpage
```

Run the command from the skill root. The script depends on local Playwright in this skill folder.

## Required Reads

Always read:

1. `references/taste.md`
2. `references/mode-infograph.md`
3. `assets/infograph_template.html`

Then read exactly one mode reference:

- `references/mode-method-intro.md` when the user asks to introduce, explain, teach, summarize, or visualize a method/tool/model/framework.
- `references/mode-industry-application.md` when the user asks to apply a method/tool/model/framework to an industry, company, product, market, region, audience, scenario, or business problem.

If the user request contains both a method and a domain, prefer **Industry Application**.

## Mode Routing

Use **Method Intro** when the request asks what a method is, how it works, how to use it, or asks for a general method explanation card.

Use **Industry Application** when the request combines a method with an industry, company, product, market, region, audience, scenario, or business problem.

## Workflow

1. Understand the content and identify the mode.
2. Classify the information shape:
   - Density: sparse / medium / dense
   - Structure: single point / contrast / hierarchy / process / radial / parallel / matrix / application map
   - Mood: reflective / sharp / warm / technical / business
   - Anchor: the largest visual idea on the card
3. Follow the selected mode reference.
4. Choose a layout that grows from the content, not a generic dashboard.
5. Fill only:
   - `{{CUSTOM_CSS}}`
   - `{{CONTENT_HTML}}`
6. Do not add built-in author footer, logo, signature, or default source line.
7. If attribution is explicitly required by the user, design it as part of the card content, not as a reusable footer.
8. Render with `assets/capture.js`.
9. Inspect the PNG for overflow, cramped text, unclear hierarchy, and accidental footer/signature remnants.

## Template Contract

`assets/infograph_template.html` provides:

- Font imports
- CSS variables
- Page background
- Noise texture
- `{{CUSTOM_CSS}}`
- `{{CONTENT_HTML}}`

It intentionally does not provide:

- `.colophon`
- Logo replacement
- `{{LOGO}}`
- `{{SOURCE_LINE}}`
- Built-in author name

## Visual Rules

Follow `references/taste.md`.

Key constraints:

- Avoid Inter.
- Avoid pure black.
- Avoid generic three-equal-card layouts.
- Avoid centered hero layouts unless the content is a single sparse idea.
- Avoid fake data and AI-flavored copy.
- Use at most one strong accent color.
- Keep text readable at 1080px export width.
- For industry application cards, prioritize analytical clarity over decorative framework purity.

## Delivery

Report the PNG path and, if useful, the HTML path.
