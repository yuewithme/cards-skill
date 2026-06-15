# Mode: Industry Application

Use this mode when the user asks to apply a method, tool, model, framework, or analysis approach to a specific industry, company, product, market, region, audience, scenario, or business problem.

Examples:

- `用 STEEP 分析银发经济`
- `SWOT × 代运营公司`
- `用微笑曲线分析跨境电商供应链`
- `波特五力分析物业旅居行业`
- `AARRR 在本地生活业务里怎么用`

## Goal

Create a consulting-style application report card that answers:

1. What does the method reveal in this specific domain?
2. Which signals matter most?
3. What opportunities and risks follow?
4. What actions should the reader consider?

This is not a generic method introduction. It must say something specific about the selected domain.

## Canvas Contract

Industry application cards need more room than method intro cards. Use a large fixed report canvas by default.

Recommended export:

```bash
node assets/capture.js <html> <png> 1280 900 fullpage
```

Recommended CSS:

```css
html, body { width: 1280px; }
.page { width: 1280px; min-height: 1800px; }
```

For dense analyses, allow `min-height: 2100px` to `2600px`. Do not squeeze a full industry analysis into a compact teaching-card composition.

Use a compact social-card format only when the user explicitly asks for it.

## Content Model

Extract or infer:

- **Method**: SWOT, STEEP, smile curve, Porter five forces, value chain, AARRR, etc.
- **Domain**: industry, company, product, market, region, audience, or scenario.
- **Analysis object**: what exactly is being judged.
- **Framework mapping**: each part of the method mapped to domain-specific facts.
- **Key insights**: 3-6 implications, not just labels.
- **Opportunity windows**: where upside may appear.
- **Risk constraints**: what could block or erode value.
- **Action direction**: what to build, avoid, test, reposition, or prioritize.

If domain details are missing, make reasonable assumptions and state them visually only when useful. Do not invent fake statistics.

## Fixed Report Structure

Use this six-layer structure as the default:

1. **Title Layer**
   - Format: `{Method} × {Domain}` or `{Domain} {Method} 分析`.
   - Add a subtitle stating what the analysis is trying to judge.

2. **Framework Diagram Layer**
   - A large visual anchor occupying the full width or a dominant upper band.
   - Examples: five-forces pressure map, SWOT matrix, smile curve, STEEP field map.
   - Keep this diagram clear and spacious. It should orient the reader before details begin.

3. **Pressure / Signal Cards**
   - 4-6 compact cards below or beside the framework diagram.
   - Each card includes: factor name, intensity/priority tag if useful, and 2-4 lines of domain-specific analysis.

4. **Detailed Analysis Table**
   - A wide table or structured grid for the real analysis payload.
   - Typical columns: dimension, domain signal, implication, strategy/action.
   - This is the main reason to use the larger canvas.

5. **Opportunity / Risk / Action Layer**
   - Split into opportunity windows and risk constraints.
   - Alternative: use "可下注 / 要回避 / 先验证".

6. **Action Thesis**
   - One strong concluding sentence.
   - It should answer: "So what should we do next?"

## Previous Compact Structure

Use a shorter five-layer structure only when the user explicitly asks for a compact output:

1. Title Layer.
2. Mapping Layer.
3. Insight Layer.
4. Opportunity / Risk Layer.
5. Action Thesis.

## Analysis Depth

For normal industry application requests, include enough substance to justify the larger format:

- At least 5 framework mapping items when the method supports them.
- At least 4 pressure/signal cards.
- At least 4 detailed rows in the analysis table.
- At least 2 opportunity windows.
- At least 2 risk constraints.
- One action thesis.

Do not create a large blank poster. If the content is thin, add analysis by reasoning from the method and domain.

## Layout Blueprint

Default report layout:

```text
┌──────────────────────────────────────────────┐
│ Title: Method × Industry                     │
│ Subtitle / scope / object                    │
├──────────────────────────────────────────────┤
│ Large framework diagram                      │
│ e.g. curve / pressure map / matrix           │
├──────┬──────┬──────┬──────┬──────┬──────────┤
│ Signal cards / pressure cards                │
├──────────────────────────────────────────────┤
│ Detailed analysis table                      │
│ dimension | domain signal | implication | action │
├────────────────────┬─────────────────────────┤
│ Opportunity windows │ Risk constraints       │
├──────────────────────────────────────────────┤
│ Action thesis / strategic direction          │
└──────────────────────────────────────────────┘
```

Use asymmetry inside sections, but keep the overall report order stable.

## Original Layer Meanings

When implementing the fixed report structure:

- **Mapping Layer** becomes the framework diagram plus signal cards.
- **Insight Layer** becomes the detailed table and implications.
- **Opportunity / Risk Layer** remains explicit.
- **Action Thesis** remains the final landing statement.

## Insight Layer Guidance

For the detailed analysis table:

   - Convert the mapping into implications.
   - Use "这意味着..." thinking, not list-only summaries.
   - Every row should move from observation to consequence to action.

## Layout Patterns

Choose by method:

| Method | Recommended application layout |
| --- | --- |
| SWOT | 2x2 matrix mapped to the domain + SO/WO/ST/WT strategy moves |
| STEEP | Five factor field map + opportunity/risk/action blocks |
| Porter five forces | Pressure map around incumbents + bargaining/rivalry summary |
| Smile curve | Industry value chain curve + high/low-value position diagnosis |
| Value chain | Chain map + margin/control points + capability gaps |
| AARRR | Funnel by domain behavior + drop-off / growth lever blocks |
| Jobs-to-be-Done | Situation-force map + functional/social/emotional jobs |

## Required Sections

Include:

- **Analysis Lens**: one short line explaining why this method fits the domain.
- **Domain Mapping**: method components translated into domain facts.
- **Critical Insights**: 3-6 domain-specific implications.
- **Opportunity Windows**: 2-4 places to act.
- **Risk Constraints**: 2-4 things that can break the strategy.
- **Action Direction**: one concise recommendation.

## Writing Rules

- Use domain-specific nouns. Avoid generic labels that could fit any industry.
- Do not merely explain the method again.
- Do not use fake numbers.
- Avoid "赋能", "生态闭环", "无缝", "释放潜力", and other vague business filler.
- Prefer concrete verbs: bundle, narrow, reposition, standardize, outsource, test, price, retain, acquire, automate, certify.
- Make claims proportional to available information. If uncertain, phrase as a strategic hypothesis.

## Visual Rules

- Make the domain, not only the method, visible in the first viewport.
- Prefer consulting-report density: clear grouping, strong section hierarchy, restrained colors.
- Use one main framework visualization, then supporting blocks.
- Do not overload the main diagram with all details; move implications into adjacent blocks.
- For industry cards, clarity beats decorative complexity.
- Do not add footer, logo, author signature, or default source line.

## Quality Check

Before rendering, verify:

- The card is not just a method explanation with the industry name pasted in.
- Each method component has domain-specific content.
- The insights include implications, not only observations.
- The opportunity/risk/action sections are distinguishable.
- The final thesis names a direction of action.
- Text remains readable at 1280px export width.
