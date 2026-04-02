---
name: seo-keyword-brief
description: Create a structured SEO keyword brief from uploaded keyword research screenshots, especially Google autocomplete, Google related searches, and Semrush keyword data. Use when the user wants a primary keyword, supporting keywords, search intent, buying stage, proof requirements, recommended content pattern, and page type for practical SEO and commercial content planning.
---

# SEO Keyword Brief

Use this skill when the user has keyword evidence and needs a compact brief that can guide page planning and writing.

This skill is not just for picking a keyword. It must also identify what kind of page the keyword actually needs.

## Default Market

Unless the user explicitly overrides it, assume:

- Target country: United States
- Target language: English

## Purpose

Turn visible keyword evidence into a brief that is usable for commercial publishing.

The output must help downstream skills answer questions like:

- What does the searcher likely want to accomplish?
- How close is the user to inquiry or purchase?
- What kind of page should be built?
- What evidence will make the page credible?
- What content pattern fits this query best?

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
- Notes about the intended offer

If screenshots are missing, partial, blurry, or contradictory, say so plainly and continue only with what is visible.

## Workflow

1. Extract only keywords and metrics that are clearly visible.
2. Compare candidate primary keywords using relevance first, then volume and difficulty.
3. Prefer `KD <= 7` when a similarly relevant option exists, but do not force a weak keyword just because difficulty is lower.
4. Use Google evidence mainly for supporting terms, modifiers, question angles, and content shape.
5. Use Semrush mainly to validate the main keyword choice and compare nearby alternatives.
6. Infer the likely search intent and the buyer's decision stage.
7. Recommend the best-fit page type and content pattern.
8. Identify what proof or evidence the page will need to avoid sounding generic.
9. Flag uncertainty instead of inventing confidence.

## Rules

- Never invent a keyword, search volume, KD, or intent signal.
- If a value is blurry or cut off, write `unclear from screenshot`.
- Do not choose a keyword only because it has volume if it is weakly related to the user's product or commercial goal.
- If all strong candidates are above the preferred KD range, say so in `Risk Notes`.
- If intent signals conflict, note the conflict briefly.
- Treat page planning and writing as downstream stages. Do not write the page here.

## Decision Labels

Use one of these intent labels:

- Transactional
- Commercial investigation
- Informational
- Navigational
- Mixed intent

Use one of these buyer-stage labels:

- Problem discovery
- Solution research
- Supplier comparison
- Model selection
- Ready to inquire

Use one of these content-pattern labels:

- Product page
- Product collection page
- Category page
- Blog article
- FAQ page
- Comparison page
- Application page
- Process guide
- Selection guide
- Manufacturer page

Use one recommended page type:

- Product page
- Product collection page
- Category page
- Blog article
- FAQ page
- Comparison page
- Landing page

## Interpretation Heuristics

Apply these heuristics when the evidence supports them:

- exact machine or model terms usually indicate `Model selection` or `Ready to inquire`
- `vs`, `difference`, `which is better`, `compare` often indicate `Supplier comparison` or `Model selection`
- `how`, `what is`, `process`, `working principle` often indicate `Problem discovery` or `Solution research`
- material or industry modifiers such as `for gold ore`, `for food processing`, or `for wastewater treatment` often suggest an `Application page`, `Landing page`, or `Selection guide`
- broad family terms often fit a collection page unless the search modifiers clearly demand a guide or comparison article

## Evidence Planning

For each keyword, infer the proof type that a strong page will likely need.

Examples:

- specifications or size ranges
- model differences
- compatible materials or applications
- process flow or system configuration
- pricing drivers
- case examples
- standards or compliance information
- service and delivery reassurance

Do not invent the evidence itself. Only state what kind of proof will matter.

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
Buyer Decision Stage:
Recommended Page Type:
Best Content Pattern:

## Secondary Keywords
- 

## Long-tail Keywords
- 

## Buyer Questions To Answer
- 

## Proof The Page Will Need
- 

## Suggested Topic Angles
- 

## Notes for Page Planning
- 

## Risk Notes
- 
```

## Writing Standard

- Keep the brief compact and practical.
- Tie judgments directly to visible evidence.
- Prefer commercially useful interpretation over generic SEO advice.
- Recommend a page shape that downstream skills can actually execute.
- If the keyword could support more than one page shape, choose the best primary option and note the tension briefly in `Risk Notes`.

## Quality Bar

The brief is failing if it does only these things:

- picks a keyword
- repeats visible terms
- labels intent vaguely

The brief is succeeding when it gives the next skill a clear answer to:

- what page should be built
- what the searcher wants to decide
- what proof the page must include
- what kind of content pattern should drive the page
