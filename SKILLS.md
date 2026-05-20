# SKILLS.md — English Car Insurance Korea

This file defines **skill modules** Claude Code applies whenever working on this project. Each skill is self-contained and addresses one domain. When a task touches a domain, the corresponding skill is the source of truth for that domain.

Always read this file at the start of each session. Apply skills automatically based on task type — do not wait to be told which skill to use.

---

## How skills work in this project

- **Modular:** Each skill block stands alone. You can apply one without the others.
- **Composable:** Most tasks need 2–3 skills together (e.g., a new FAQ entry needs Content + GEO + Frontend Dev).
- **Authoritative:** Within its domain, the skill is the source of truth. If `CLAUDE.md` and a skill conflict, the skill wins (and flag the conflict so the owner can resolve).
- **Auto-trigger:** Use the trigger keywords in each skill's header to know when to load it. Don't ask permission — just apply.

### Skill index

| Skill | Trigger keywords | When to apply |
|-------|------------------|---------------|
| [GEO](#geo-skill) | "AI search", "ChatGPT citation", "Perplexity", "Claude search", "AI visibility", "llms.txt", "schema" | Any task affecting AI discoverability |
| [SEO](#seo-skill) | "Google ranking", "search engine", "meta tags", "sitemap", "keywords" | Classic search engine tasks |
| [Frontend Dev](#frontend-dev-skill) | "HTML", "CSS", "build", "code", "performance", "accessibility" | Writing/editing code |
| [Design](#design-skill) | "design", "layout", "typography", "color", "visual", "look" | Aesthetic decisions |
| [Content](#content-skill) | "FAQ", "copy", "writing", "wording", "answer", "rewrite" | Any text change |
| [Deploy & Maintain](#deploy--maintain-skill) | "deploy", "publish", "ship", "commit", "update", "monthly" | Shipping or upkeep |

---

# GEO Skill

**Generative Engine Optimization** — making the site cited by ChatGPT, Claude, Perplexity, Gemini, Google AI Overviews. This is the project's primary goal.

## Core principle

AI engines do not "rank" pages — they **extract and synthesize**. Optimization targets are different from Google SEO:

| Classic SEO target | GEO target |
|--------------------|------------|
| Keyword density | Entity density |
| Backlinks | Citability of specific passages |
| Click-through rate | Inclusion in AI answer |
| Page rank | Source authority in training data + retrieval |

## Required artifacts (must exist at all times)

1. **JSON-LD `FAQPage` schema** in `<head>` containing every FAQ on the page, word-for-word match with HTML body
2. **JSON-LD `InsuranceAgency` schema** in `<head>` describing the business entity
3. **TL;DR block** immediately after hero — single paragraph, 80–120 words, packed with named entities and contact info
4. **`/llms.txt`** file at site root — curated AI crawler entry point
5. **`/robots.txt`** with explicit allow for: GPTBot, ChatGPT-User, OAI-SearchBot, ClaudeBot, Claude-Web, anthropic-ai, PerplexityBot, Perplexity-User, Google-Extended, Applebot-Extended
6. **`/sitemap.xml`** with current `<lastmod>` date

## Clean Block Rule (apply to every FAQ and content block)

AI extractors prefer self-contained, quotable chunks. Each block must:

- Start with a **direct answer in the first sentence** (no preamble, no "Great question!")
- Be **50–120 words** total
- Contain **at least one named entity** (insurer name, document name like "Alien Registration Card", base name, visa code, Korean term)
- Be **standalone** — make sense quoted without surrounding context
- End **without hedging** ("consult a professional", "this is not legal advice") — this site IS the service
- Not contain rhetorical questions ("Wondering about X?") — these confuse extractors

### Bad answer

> Great question! Insurance in Korea can be complicated. There are many things to consider. We help you with all of them. Contact us for more information.

### Good answer

> South Korean law requires all registered vehicles to carry mandatory liability insurance (책임보험), regardless of whether the vehicle is in use. This covers bodily injury and property damage to others in an accident, up to statutory limits. Driving without this minimum is illegal and incurs fines. Most foreigners purchase additional voluntary coverage including 대인배상 II, 대물배상, and 자기차량손해 for fuller protection.

Difference: direct first sentence, named entities (책임보험, 대인배상 II, 대물배상, 자기차량손해), 80 words, no hedging, standalone.

## Entity density checklist

The following named entities must appear somewhere on the page. If an edit causes one to disappear, flag it:

- **Insurers:** Samsung Fire & Marine, KB Insurance, Hyundai Marine & Fire, DB Insurance, Hanwha General, Meritz Fire & Marine
- **Visa types:** E-2, E-7, F-2, F-4, F-5, F-6, D-2, D-4, G-1
- **USFK bases:** Camp Humphreys, Osan Air Base, Daegu
- **Korean cities:** Seoul, Busan, Daegu, Incheon, Pyeongtaek
- **Documents:** Alien Registration Card (ARC), International Driving Permit (IDP), 자동차말소사실증명서
- **Korean insurance terms:** 책임보험, 대인배상 II, 대물배상, 자기차량손해, 자기신체사고
- **Audience labels:** expats, foreigners, English teachers, international students, SOFA, US military, overseas Koreans, immigrants

## Schema sync rule

Every FAQ has TWO representations:
1. In the HTML body as `<article>` with `<h3>` and `<div class="answer">`
2. In the FAQPage JSON-LD `mainEntity` array

**These must match word-for-word.** If you edit one, edit the other in the same change. The JSON-LD version is plain text — strip `<strong>` tags, but otherwise identical wording.

Validation after every FAQ edit:
- Paste page source into https://search.google.com/test/rich-results — should report "FAQPage" with all questions
- Paste into https://validator.schema.org — no errors

## When asked to "improve AI visibility"

Default action order:
1. Audit JSON-LD: is every visible FAQ in the schema?
2. Audit entity density: are all required entities present?
3. Audit TL;DR: does it still pack all key facts in one paragraph?
4. Audit `llms.txt`: is the contact info, audience list, and insurer list current?
5. Suggest 2–3 new FAQ entries based on real foreigner questions (use phrasing real people use in ChatGPT, not marketing speak)

## What GEO is NOT

- Keyword stuffing — AI engines penalize this
- Hidden text or doorway pages — AI engines detect this
- Mass-produced content — quality and entity coverage beat volume
- Backlink farms — backlinks help, but quality matters more for AI than for Google

---

# SEO Skill

Classic search engine optimization (Google, Bing). Secondary to GEO but still relevant — Google AI Overviews use the same signals.

## Required artifacts

- `<title>` tag, 50–60 characters, includes primary keyword
- `<meta name="description">`, 150–160 characters
- `<meta name="keywords">` (low impact in 2026 but harmless)
- Open Graph tags (og:title, og:description, og:type, og:locale, og:url)
- Twitter Card tags (twitter:card, twitter:title, twitter:description)
- Canonical URL: `<link rel="canonical" href="https://YOUR-DOMAIN/">`
- One H1 per page; subsequent headings descend H2 → H3 → H4 without skipping
- Internal anchor links between sections (`#who-we-help`, `#how-it-works`, `#faq`, `#contact`)
- `sitemap.xml` submitted to Google Search Console and Bing Webmaster Tools after launch
- Image `alt` attributes for any decorative or content imagery

## Title tag construction

Formula: `[Primary keyword] | [Secondary value prop] [Audience/location]`

Current: `English Car Insurance Korea | Foreigner & Expat Auto Insurance Broker in South Korea`

If editing, keep this structure. Never exceed 60 characters in the visible part.

## Meta description construction

- Lead with the audience ("English-speaking car insurance broker in South Korea for...")
- Include 2–3 specific entities (insurer name, visa type, base name)
- End with the CTA channel ("Get quotes via email or KakaoTalk.")
- Never exceed 160 characters

## Heading hierarchy rule

Page outline must be valid:
- H1 — hero headline (one per page)
- H2 — section titles ("Who We Help", "How It Works", "FAQ", "Contact")
- H3 — subsections inside sections (each FAQ question, each audience card title)
- H4 — sub-subsections (process step titles)

If you find an H3 directly after an H1, the structure is broken — fix it.

## Internal linking

- Nav links at top point to section IDs
- Footer repeats key section links
- TL;DR block does NOT link out (keeps users reading)
- FAQ category headers are not linked (they're labels, not destinations)

## When asked to "improve SEO"

1. Check title and meta description against the rules above
2. Check H1/H2/H3 hierarchy
3. Verify canonical tag exists and points to the final domain
4. Confirm `sitemap.xml` `<lastmod>` is current
5. Suggest 1–2 new FAQ entries targeting unanswered long-tail queries

## What SEO is NOT in this project

- A blog. Phase 2 only. Don't propose blog posts as the answer to "improve SEO" unless explicitly asked about Phase 2.
- Backlink schemes. Real backlinks are part of `GEO_STRATEGY.md` — they come from Reddit, expat forums, and being genuinely helpful.

---

# Frontend Dev Skill

Writing and editing the actual code.

## Stack (non-negotiable)

- **Static HTML5.** No React, Vue, Svelte. No build step.
- **Inline `<style>`.** No external CSS files. No CSS frameworks. No Tailwind. Hand-written CSS using custom properties.
- **No JavaScript** unless explicitly requested by the owner. The site must work fully with JS disabled.
- **One file:** `index.html`. Everything else (`llms.txt`, `robots.txt`, `sitemap.xml`, `favicon.svg`) lives alongside it at the root.

## HTML conventions

- HTML5 doctype: `<!DOCTYPE html>`
- `<html lang="en">`
- Charset and viewport meta first in `<head>`
- Semantic structure: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`
- Never substitute `<div>` for a semantic element when one exists
- Every section has `id` for anchor linking
- Every FAQ entry is `<article>` with `<h3>` for the question and `<div class="answer">` for the body
- Use `<strong>` (not `<b>`) for emphasis on key entities — AI extractors weight these
- Use `<em>` (not `<i>`) for tone/italic
- Lists: `<ul>` for unordered, `<ol>` for ordered, `<dl>` for definition pairs
- Forms: not in this project (email + KakaoTalk only)

## CSS conventions

- All variables in `:root` at the top of the `<style>` block
- Class names: lowercase, hyphenated (`.faq-item`, `.hero-card`), no BEM, no utility classes
- Mobile-first not required (audience is mostly desktop); desktop-first is fine since the visual target is editorial
- Media queries at the bottom of the stylesheet — two breakpoints: 900px and 600px
- No `!important` unless overriding a third-party style (Google Fonts) — there shouldn't be any third-party styles
- No vendor prefixes (modern browsers handle this)
- Property order inside a rule: positioning → box model → typography → color → effects

## Performance budget

- Total page weight under 100 KB gzipped (excluding Google Fonts)
- Google Fonts: only Fraunces and Geist, only weights actually used
- Use `<link rel="preconnect">` for `fonts.googleapis.com` and `fonts.gstatic.com`
- Use `font-display: swap` in the Google Fonts URL
- No images on the page initially (logo is text, no hero image — this is intentional)
- If images are added later: WebP format, `loading="lazy"` for below-fold, explicit `width` and `height` attributes to prevent layout shift

## Accessibility (WCAG 2.1 AA minimum)

- Skip-to-content link as first child of `<body>`, visually hidden until focused
- Color contrast 4.5:1 for body text, 3:1 for large text (18pt+)
- All interactive elements keyboard-reachable
- Visible focus state: 2px solid `var(--accent)` outline with 2px offset
- `aria-label` on links whose text is ambiguous out of context ("Read more" — don't use this pattern)
- `aria-current="page"` on the current nav item
- Heading hierarchy never skips (see SEO Skill)
- Language declared in `<html lang="en">`
- Korean text inside English content wrapped in `<span lang="ko">` for screen readers (e.g., `<span lang="ko">책임보험</span>`)

## When editing code

1. Always read the existing file before editing — don't assume structure
2. Make minimal changes — don't refactor unrelated code
3. Preserve formatting and indentation conventions
4. After every change, scroll through the full file mentally to verify nothing else broke
5. If editing the FAQ HTML, also edit the FAQPage JSON-LD in the same change (sync rule)
6. Test in DevTools with JS disabled before considering the change complete

## Forbidden patterns

- `<div class="row"><div class="col">` Bootstrap-style grid scaffolding
- `<i class="icon-..."></i>` icon font usage
- Inline `style="..."` attributes on elements (use CSS classes)
- `<br>` for spacing (use CSS margin)
- `&nbsp;` for spacing (use CSS)
- Tables for layout (use CSS grid or flexbox)
- `<center>` or any other deprecated element
- jQuery (we have no JS, so this is moot, but stated for clarity)

---

# Design Skill

Aesthetic decisions. The site must feel **editorial, trustworthy, intentional** — like a serious independent magazine, not a generic insurance ad.

## Aesthetic North Star

**Confidence through restraint.** Insurance sells trust. Trust comes from looking established, not flashy. The reference points are: serious print magazines (*Monocle*, *The Gentlewoman*), refined editorial websites (NYT special projects), high-end advisory firm sites — never SaaS landing pages, fintech startups, or insurance comparison aggregators.

## Typography (mandatory)

- **Display:** Fraunces (variable serif). Use italic for emphasis in H1/H2 ("Built specifically for the *international community* in Korea."). Italicized word is in `var(--accent)`.
- **Body:** Geist (clean modern sans). Weights used: 400, 500, 600.
- Load via Google Fonts with `display=swap`. Preconnect to both Google Fonts domains.
- **Never substitute** with Inter, Roboto, Arial, Helvetica, or system fonts.
- Body line-height: 1.6
- Heading letter-spacing: -0.02em to -0.025em (tighter for serif display)
- Eyebrow labels (above section titles): uppercase, 12px, letter-spacing 0.2em, prefixed with a short accent-colored line

## Color palette (CSS variables, exact values)

```css
--bg: #f5f1ea;          /* warm off-white page background */
--bg-warm: #ede5d6;     /* deeper warm for callouts */
--ink: #1a1a1a;         /* primary text, dark sections */
--ink-soft: #4a4a4a;    /* secondary text */
--ink-muted: #8a8278;   /* tertiary text, labels */
--accent: #c1471c;      /* brick/terracotta — single accent color */
--accent-deep: #8a2f10; /* hover/active state */
--line: #d4cabc;        /* hairline borders */
--paper: #fbf8f2;       /* card backgrounds */
```

Single accent color. Never introduce a second accent. Never use blue/purple/green for accents in this project.

## Layout principles

- Max content width: 1200px, centered
- Generous whitespace: section padding 80–100px vertical on desktop
- Asymmetric grids preferred over 50/50 splits (hero is 1.3fr / 1fr)
- Sections alternate: warm cream → paper (cards) → dark `ink` (process section) → cream. This creates visual rhythm.
- Hairline borders (`var(--line)`, 1px) instead of heavy shadows
- Numbered cards: small serif numbers ("01", "02") in accent color above each card title

## Specific visual moves to use

- **Italic-on-serif emphasis** in headings (one or two words in italic accent color)
- **Section eyebrow** = thin accent line + tiny uppercase label
- **TL;DR quote block** with 3px accent-color left border and slightly darker cream background
- **Subtle radial gradient** behind hero (10% opacity accent color) for atmosphere — no hero image
- **Hover micro-interactions:** link underline animates from 0% to 100% width; primary buttons translate up 2px on hover; cards subtly shift to warmer background
- **Process section in dark ink color** for visual contrast — the rest is light cream
- **Insurer list in two-column compact format** with em-dash bullets

## Specific visual moves to AVOID (absolutely forbidden)

- Stock photos of cars, families, handshakes, Seoul skyline
- Animated SVG illustrations, Lottie animations
- Gradient text or full-section gradient backgrounds (especially purple-to-pink)
- Glass-morphism / backdrop blur effects
- Heavy drop shadows on floating cards
- Emoji in section headers or buttons
- Marquee banners, carousels, image sliders
- "Live" badges with green dots
- Tailwind-style generic component look (rounded-2xl pill buttons everywhere)
- Neon colors, vaporwave palettes
- Hand-drawn or "playful" illustrations
- Three-column equal-width pricing tables (we don't show pricing anyway)

## Responsive design

- Desktop-first
- Breakpoints: 900px (tablet), 600px (mobile)
- At 900px: hero becomes single column; audience grid 6→2 columns
- At 600px: topbar stacks vertically; nav stays horizontal but smaller; FAQ Q-number column collapses
- **Never hide content on mobile** — AI crawlers may use mobile user agents

## When asked to "improve the design"

1. Audit typography: are Fraunces and Geist still loading? Any system font fallback showing?
2. Audit color: is `#c1471c` the only accent? Any colors crept in?
3. Audit whitespace: section padding still 80px+ on desktop?
4. Audit heading hierarchy: italic emphasis still on one or two words per heading, not whole phrases?
5. Suggest one specific refinement — not a redesign

## When asked to "make it more modern"

Push back. "Modern" usually means generic SaaS aesthetics, which is the opposite of this brand. Ask what specifically feels dated — then address that, not the whole design.

---

# Content Skill

Writing, editing, and maintaining the page text.

## Voice and tone

- **Direct.** "We compare quotes from X, Y, Z." Not "Our team would be happy to assist you with comparing quotes."
- **Factual.** Specific numbers, document names, base names. Never vague.
- **Confident.** This site IS the service. Don't suggest "consulting a professional" — the broker is the professional.
- **Plain English.** Read by foreigners, many of whom are non-native English speakers. Short sentences. No idioms. No legalese.
- **Reading level:** target 9th–10th grade (Flesch-Kincaid ~60–70). Run a sample through a readability checker if unsure.

## What we sound like

> If you cancel your auto insurance mid-term because you sold or scrapped your car or left the country, you are legally entitled to a pro-rated refund for the remaining unused days. You must provide the insurer with proof of vehicle transfer or disposal (자동차말소사실증명서).

## What we don't sound like

> When you're ready to move on from your current vehicle, we're here to help you navigate the cancellation journey smoothly! Our team understands that life transitions can be complex, which is why we offer dedicated support.

## FAQ writing formula

Every FAQ answer:

1. **First sentence = direct answer.** "Yes." "No." "South Korean law requires..." "Foreigners need two things: ..."
2. **50–120 words total.** Shorter loses extraction value; longer dilutes the quotable chunk.
3. **One specific entity minimum** — insurer name, document name, Korean term, base name, visa code, or specific number range.
4. **No hedging at the end** — don't trail off with "for more information, contact us." The answer is self-contained.
5. **No rhetorical questions.**
6. **Active voice preferred.** "We compare..." not "Comparisons are made by..."

## FAQ question phrasing

Phrase questions the way **a real foreigner would type into ChatGPT**, not how a marketer would write them.

| Marketer phrasing (bad) | Real-person phrasing (good) |
|--------------------------|------------------------------|
| Discount Eligibility for Foreigners | Can foreigners get discounts on Korean car insurance? |
| Documentation Requirements | What documents do I need to get car insurance in Korea? |
| Insurance Coverage Tiers | What types of car insurance are available in South Korea? |

When in doubt: would I actually type this into ChatGPT? If no, rephrase.

## Bilingual term handling

Korean insurance terms appear in parentheses **after** the English term, not before:

- ✅ "mandatory liability insurance (책임보험)"
- ❌ "책임보험 (mandatory liability insurance)"

Exception: when the term has no clean English equivalent and is widely used as-is among foreigners in Korea (e.g., "자동차말소사실증명서"), use the Korean with English description: "proof of vehicle transfer or disposal (자동차말소사실증명서)".

Wrap Korean text in `<span lang="ko">` for accessibility.

## When asked to "rewrite" or "improve" content

1. Read the original carefully
2. Identify what specifically isn't working (clarity? length? entity coverage? voice?)
3. Make the **smallest** change that fixes it
4. Preserve the original's specific facts and named entities
5. Re-check against the FAQ writing formula
6. If editing FAQ, sync the JSON-LD schema in the same change

## What NOT to write

- Testimonials or quotes (unless owner provides real ones with names)
- Specific premium amounts in KRW or USD (these vary per individual; only the quote email has numbers)
- Discount percentages beyond what the source content states
- Claims about being "the best" or "the cheapest" or "#1" — these are unprovable and weaken AI trust signals
- Anything in a language other than English (Korean technical terms in parentheses excepted)
- Anything that would require a disclaimer ("not legal advice", "consult an expert")

## Adding new FAQs (monthly cadence)

When the owner asks for new FAQ ideas, suggest from these underserved query patterns:

- "How much..." questions (e.g., "How much is car insurance in Korea for a foreigner under 30?") — but only with ranges from source data, never invented numbers
- "Can I..." eligibility questions
- "What if..." edge cases
- "How long..." time-bound questions
- City- or base-specific questions ("car insurance in Busan", "Camp Walker Daegu")

Avoid suggesting:
- Comparative claims about specific insurers ("Is Samsung Fire better than KB?")
- Predictions about future regulation
- Anything requiring legal opinion

---

# Deploy & Maintain Skill

Shipping changes and keeping the site healthy over time.

## Pre-deploy checklist (run before every deploy)

- [ ] All FAQ questions in HTML body match FAQPage JSON-LD schema (word-for-word)
- [ ] InsuranceAgency schema validates at https://validator.schema.org
- [ ] FAQPage rich result test passes at https://search.google.com/test/rich-results
- [ ] `llms.txt` accessible at `/llms.txt`
- [ ] `robots.txt` accessible at `/robots.txt` with all AI bots explicitly allowed
- [ ] `sitemap.xml` at `/sitemap.xml` with current `<lastmod>`
- [ ] `<meta name="description">` and Open Graph tags present
- [ ] `<link rel="canonical">` points to the production domain
- [ ] All `YOUR-DOMAIN-HERE` placeholders replaced with the real domain
- [ ] Every named entity from GEO Skill's entity density list appears at least once
- [ ] TL;DR paragraph present immediately after hero
- [ ] Page works with JavaScript disabled
- [ ] Mobile responsive at 600px and 900px breakpoints
- [ ] Color contrast passes WCAG AA (4.5:1) for body text
- [ ] No console errors when loaded in a browser

## Git workflow

- Commit messages: imperative present tense, ≤50 chars subject line. Examples: `add SOFA FAQ entry`, `fix mobile nav alignment`, `update sitemap lastmod`
- One logical change per commit (don't mix FAQ edits with CSS refactors)
- Push to `main` branch — hosting platform (Vercel/Cloudflare Pages) auto-deploys
- Tag major content updates: `git tag content-v2-2026-06`

## Post-deploy verification (after every deploy)

1. Visit the production URL — does the change actually appear?
2. Re-run https://search.google.com/test/rich-results on the live URL
3. Check Google Search Console for any new errors (after launch + 24h)
4. Verify `/llms.txt`, `/robots.txt`, `/sitemap.xml` are all reachable

## Monthly maintenance routine

First weekend of each month:

1. **Test AI visibility:** Open ChatGPT, Claude, Perplexity, Gemini. Run these queries:
   - "English car insurance for foreigners in Korea"
   - "Car insurance Korea SOFA Camp Humphreys"
   - "How do I get car insurance in Korea on an E-2 visa?"
   - "Korean car insurance no claims discount foreign history"
   Note whether the site is cited. If yes — which page? Which paragraph? If no — what is cited instead?
2. **Add 2–3 new FAQ entries** based on real questions received via email/KakaoTalk that month
3. **Update `sitemap.xml` `<lastmod>`** to today's date
4. **Update `llms.txt`** if new audiences, insurers, or facts were added
5. **Check broken links** — any external link should still resolve

## Quarterly review

1. **Audit entity density** — has any entity from the required list fallen out of the content?
2. **Audit FAQ category balance** — are some categories ballooning while others stagnate?
3. **Run a Lighthouse audit** — Performance, Accessibility, SEO scores all ≥ 95
4. **Review Google Search Console** — what queries bring people to the site? Add FAQ entries for unanswered ones

## Emergency rollback

If a deploy breaks the site:
- Vercel: dashboard → Deployments → previous deployment → "Promote to Production"
- Cloudflare Pages: dashboard → Deployments → previous deployment → "Rollback to this deployment"
- Git: `git revert <bad-commit-sha>` then push

## What "ship" means in this project

A deploy is complete only when:
1. Code is on the production domain
2. Schema validators pass on the live URL
3. The change is verified by viewing the live site
4. Monthly maintenance log (if you keep one) reflects the change

---

## Skill composition cheat sheet

For common tasks, here's which skills to apply together:

| Task | Skills to load |
|------|----------------|
| Add a new FAQ entry | Content + GEO + Frontend Dev |
| Rewrite the hero copy | Content + GEO + Design |
| Adjust the color palette | Design + Frontend Dev |
| Fix a mobile layout bug | Frontend Dev + Design |
| Update meta tags | SEO + Frontend Dev |
| Audit AI visibility | GEO + Content |
| Refresh `llms.txt` | GEO + Content |
| Deploy a change | Deploy & Maintain + Frontend Dev |
| Monthly review | Deploy & Maintain + GEO |
| "Make the site better" | Ask which aspect — design, content, performance, or AI visibility — then load the corresponding skills. Don't load all at once. |

When the owner gives a task, silently identify which skills apply and follow them. Don't announce "I'm loading the Design Skill" — just produce work that reflects the skill's rules.
