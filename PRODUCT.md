# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Static HTML/CSS (no build step), deployed via GitHub Pages with a custom domain (CNAME: deven.autos). Existing codebase already answers this; not asked separately.

## Users

Anyone who receives the link — strangers, coworkers, acquaintances — with zero prior context on who Deven is. This is a shareable public gag site, not a private inside joke for people who already know him. The copy and design must land as funny on first read, unaided.

## Product Purpose

A satirical "legendary profile" page that presents an ordinary guy, Deven, as if he were a mythic public figure — plane-landing heroics, hostage negotiations, anonymous philanthropy, etc. — in the register of a corporate About page, a press kit, or a Wikipedia "notable achievements" list. The joke is the mismatch between the grandiose format and the absurd/mundane content. Success = it's funny and shareable to someone with no context.

## Positioning

Not a normal personal portfolio or roast page — it's a deadpan pastiche of prestige-bio formatting (stats bar, timeline "chapters," press blurbs, awards wall) applied straight-faced to fabricated legend material. The humor mechanism is tone mismatch, not jokes-as-jokes.

## Operating Context

Deployed as a static GitHub Pages site at deven.autos (repo: Blpcky/Deven.Autos, branch main). Guestbook comments are powered by giscus (GitHub Discussions-backed), configured against this repo's Discussions category — this is a live, working integration, not placeholder content.

## Capabilities and Constraints

- Guestbook (giscus embed) must keep working: same repo mapping, same or equivalent config, visitors sign in with GitHub to comment.
- CNAME file (`deven.autos`) must be preserved for the custom domain to keep resolving.
- `fish.html` (an unrelated "fish database" easter egg page) and its own image assets are out of scope for this redesign — not touched.
- Existing `1.jpg`–`11.jpg` in `/images` are available legend-photo assets that may be reused or replaced.
- No analytics, no backend, no forms beyond the giscus guestbook.

## Brand Commitments

Site is about "Deven Ballback" specifically (his real name appears in the current nav/title). No locked-in palette, typography, or layout — full visual redesign is in scope, including new copy. Only the guestbook *mechanism* is a hard constraint (see Capabilities).

## Evidence on Hand

- Existing copy (chapters/timeline, stats, press quotes, awards) in `index.html` — rewritten for the redesign (Wikipedia-article parody, dry/skeptical voice per user request) rather than preserved verbatim.
- `/images/1.jpg`–`11.jpg` — confirmed to be stock studio photos of well-known tuner/performance cars (Cobra R, Subaru STI, S2000, Integra, etc.), not personal photos of Deven. Not evidence of his real vehicles. One (`6.jpg`) is used once, honestly captioned as "relevance unclear," tied to the deven.autos domain-name joke rather than presented as his own car.
- No real testimonials, press, or data exist beyond what's fabricated in-page as part of the bit; nothing here is factual and nothing further should be fabricated as if it were real (e.g., don't invent real company names, real news outlets, or real dollar figures presented as fact outside the joke).

## Product Principles

1. The bit only works if the format is played completely straight — prestige-bio structure, not visibly "joke-y" design.
2. Must work for a first-time reader with zero context — no assumed inside knowledge.
3. Guestbook must remain functionally intact through any redesign.
4. Rewritten copy should be funnier through understatement and specificity, not through winking at the reader or over-explaining the joke ("cringe" avoidance).
5. Everything outside `index.html`'s core experience (fish.html easter egg) stays untouched.

## Accessibility & Inclusion

No user-specified requirement beyond standard practice (contrast, semantic structure, keyboard/focus support) for a public-facing static site.
