---
name: seo-keyword-brief
description: Analyze three uploaded screenshots for SEO keyword research: a Google autocomplete screenshot, a Google related searches screenshot, and a Semrush keyword data screenshot. Use when the user wants a structured keyword brief with primary keyword, secondary keywords, long-tail keywords, search intent, page type recommendation, topic angles, and risk notes for SEO content planning.
---

# SEO Keyword Brief

Use this skill when the user uploads keyword research screenshots and wants a clean, reusable SEO brief for the next writing step.

## Inputs

Expected core inputs:

1. A Google autocomplete screenshot
2. A Google related searches screenshot
3. A Semrush keyword data screenshot

Optional inputs:

- Industry or niche
- Product type
- Client website
- Competitor websites

Default assumptions unless the user explicitly overrides them:

- Target country: United States
- Target language: English

If the screenshots are missing, incomplete, or unreadable, say so clearly and continue only with the information that is visible.

## Role

Your job is not to browse or fetch keyword data yourself.

Your job is to:

1. Read the screenshots carefully
2. Extract visible keywords and metrics
3. Identify the most viable main keyword
4. Group supporting keywords by use
5. Infer likely search intent
6. Recommend the best page type
7. Produce a writing brief that can be handed to the next SEO-writing skill

## Prioritization Rules

When choosing the primary keyword, prioritize:

1. Strong relevance to the user's product or topic
2. Clear commercial or practical writing value
3. Visible search volume
4. KD at or below 7
5. Lower KD when choices are otherwise similar

Do not pick a keyword only because it has volume if it is weakly related to the actual product or page goal.

Treat `KD <= 7` as the preferred range.

If a keyword is highly relevant but has `KD > 7`, do not use it as the default primary keyword unless the screenshot evidence shows there is no better low-KD alternative. In that case, flag the competition risk clearly in `Risk Notes`.

Google autocomplete and related searches are mainly used to expand supporting terms, subtopics, and FAQ directions.

Semrush data is mainly used to validate the main keyword choice and compare nearby alternatives.

## Screenshot Handling Rules

- Never invent a keyword, number, KD, or volume that is not visible.
- If a value is blurry, partially cut off, or uncertain, mark it as `unclear from screenshot`.
- If multiple candidate keywords appear in Semrush, compare them briefly before choosing one.
- If the screenshots suggest different intent directions, call out the conflict instead of forcing certainty.
- If there is not enough evidence to recommend a page type confidently, say which options remain plausible.
- If all visible strong candidate keywords have `KD > 7`, explicitly say that the keyword set is more competitive than the team's current target range.

## Intent Classification

Classify search intent using the visible evidence. Use one of these labels:

- Transactional
- Commercial investigation
- Informational
- Navigational
- Mixed intent

For B2B and industrial topics, prefer practical judgment over textbook labels. For example:

- machine model terms often indicate product-page intent
- broad equipment category terms may fit a collection page
- "how", "what", "benefits", and "working principle" terms often fit blog or guide intent
- "price", "manufacturer", "supplier", "for sale" suggest stronger buying intent

## Page Type Recommendation

Recommend one primary page type:

- Product page
- Product collection page
- Category page
- Blog article
- FAQ page
- Comparison page

Base this on the search intent and keyword breadth.

Assume the market is the United States and the page language is English unless the user explicitly says otherwise.

## Output Requirements

Always output in the following structure.

Keep it compact, practical, and ready for the next step.

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

## Content Rules

### Primary Keyword

Select one best keyword.

If the Semrush screenshot shows metric values for that term, include them.

If the exact metric cannot be read, write:

- `Search Volume: unclear from screenshot`
- `KD: unclear from screenshot`

Always include:

- `Target Country: United States`
- `Target Language: English`

unless the user explicitly overrides them.

### Secondary Keywords

Include closely related terms that can be used naturally in headings, body copy, anchor text, and internal links.

### Long-tail Keywords

Include more specific variants that are useful for:

- H2 and H3 sections
- FAQ questions
- subtopics
- future supporting articles

### Suggested Topic Angles

List content angles that fit the keyword set and intent. Examples:

- machine types
- applications
- working principle
- benefits
- technical specifications
- how to choose
- maintenance
- price factors
- buyer FAQs

Only include angles supported by the keyword cluster and topic.

### Notes for Content Writing

Use this section to give practical guidance for the next SEO-writing step, such as:

- whether the page should target a broad or narrow intent
- whether the page should emphasize product features, use cases, comparisons, or education
- whether FAQ is important
- whether supporting pages may be needed

### Risk Notes

Use this section when there are quality concerns, such as:

- low volume but high relevance
- broad keyword with unclear intent
- mismatch between Semrush metrics and Google suggestion patterns
- screenshots too blurry for confident selection
- keyword may be better suited to a different page type
- KD is above the team's preferred ceiling of 7

## Style

- Be direct and structured
- Avoid long explanations
- Avoid generic SEO advice
- Prefer judgment tied to the visible screenshots
- If evidence is weak, state uncertainty clearly

## Handoff

The result should be suitable for passing directly into a page-planning skill such as a page architect or SEO writer.
