# cards-skill

`cards` is a Codex skill for creating PNG information cards from content.

It is based on the `ljg-card -i` infographic workflow, with the built-in footer, logo, author signature, and source line removed.

## Modes

- `method-intro`: introduce a method, tool, model, or framework.
- `industry-application`: apply a method or framework to an industry, market, product, company, or scenario.

## Structure

```text
skill/cards/
  SKILL.md
  assets/
  references/
  agents/
examples/
  *.html
  *.png
```

## Usage

Install or copy `skill/cards` into your Codex skills directory:

```text
~/.codex/skills/cards
```

Then restart Codex and ask for cards such as:

```text
Use cards to create a SWOT method intro card.
Use cards to create a STEEP x silver economy industry analysis card.
```

The skill renders HTML to PNG with:

```bash
node assets/capture.js <html> <png> 1080 800 fullpage
```

## Examples

Generated examples are stored in `examples/`.
