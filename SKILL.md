---
name: seo-keyword-brief
description: Create a structured SEO keyword brief from uploaded keyword research screenshots, especially Google autocomplete, Google related searches, and Semrush keyword data. Use when the user wants a primary keyword, supporting keywords, search intent, recommended page type, topic angles, and risk notes for SEO content planning.
---

# SEO Keyword Brief

## Purpose

Turn visible screenshot evidence into a compact keyword brief for the next SEO planning or writing step.

Do not browse for additional keyword data. Work only from the screenshots and any user-provided context.

## Inputs

Preferred inputs:

- Google autocomplete screenshot
- Google related searches screenshot
- Semrush keyword data screenshot

Optional inputs:

- Industry or niche
- Product type
- Client site
- Competitor sites
- Target country
- Target language

Defaults unless the user overrides them:

- Target country: United States
- Target language: English

If screenshots are missing, incomplete, or unclear, say so plainly and continue with only the evidence that is visible.

## Workflow

1. Extract only keywords and metrics that are visible.
2. Compare candidate primary keywords using relevance first, then volume and difficulty.
3. Prefer `KD <= 7` when a similarly relevant option exists.
4. Use Google screenshots mainly for supporting terms, subtopics, and FAQ directions.
5. Use Semrush mainly to validate the main keyword choice and compare nearby alternatives.
6. Infer search intent and recommend the best-fit page type.
7. Flag uncertainty or competition risk instead of inventing certainty.

## Rules

- Never invent a keyword, search volume, KD, or intent signal.
- If a value is blurry or cut off, write `unclear from screenshot`.
- Do not choose a keyword only because it has volume if it is weakly related to the user's product or page goal.
- If all strong candidates are above the preferred KD range, say so in `Risk Notes`.
- If intent signals conflict, note the conflict briefly.

Use one of these intent labels:

- Transactional
- Commercial investigation
- Informational
- Navigational
- Mixed intent

Recommend one page type:

- Product page
- Product collection page
- Category page
- Blog article
- FAQ page
- Comparison page

## Output

Always return this structure:

```markdown
# Keyword Brief

Primary Keyword:
Reason for Selection:
Target Country:
Target Language:
Search Volume:
KD:
Search Intent:
Recommended Page Type:

## Secondary Keywords
- 

## Long-tail Keywords
- 

## Suggested Topic Angles
- 

## Notes for Content Writing
- 

## Risk Notes
- 
```

## Writing Standard

- Keep the brief compact and practical.
- Prefer judgment tied directly to visible screenshot evidence.
- Avoid generic SEO advice.
- Make the result usable as a handoff to a page-planning or SEO-writing skill.
