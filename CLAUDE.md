# CLAUDE.md — English Car Insurance Korea

You are helping build a single-page English website for an English-speaking car insurance brokerage in South Korea. The site replaces an existing Google Sites page (https://sites.google.com/view/carinsuranceinkorea) with a properly structured, AI-discoverable version.

**Primary goal:** be cited by AI search engines (ChatGPT, Claude, Perplexity, Gemini, Google AI Overviews) when foreigners in Korea ask about car insurance. Visual design is secondary to that goal but must be excellent.

---

## NORTH STAR PRINCIPLES (read every session)

1. **AI citation > visual polish > everything else.** Every decision is judged by: "Will this make an AI more likely to quote us?" If a design flourish hurts machine parseability, drop the flourish.
2. **Static HTML only.** No React, no build step, no client-side content rendering. AI crawlers (especially ClaudeBot and PerplexityBot) handle JS-rendered content poorly. One `index.html` file ships everything.
3. **English only.** Audience is English-speaking foreigners in Korea. Korean insurance terms (책임보험, 자동차말소사실증명서) appear only in parentheses next to English equivalents.
4. **Never invent facts.** This is an insurance service. Insurer names, document names, base names, discount mechanics — only what is in this file. If unsure, ask.
5. **Source content is verbatim.** The text in the SOURCE CONTENT section below is the verbatim wording from the existing live site. Do not paraphrase it. Do not "improve" it. Copy it exactly into the HTML. The owner already approved this wording.

---

## SOURCE CONTENT (verbatim — from existing site)

This is the complete text from the existing Google Sites pages. Use it exactly.

### Business identity

- **Brand name (use in all headings):** English Car Insurance Korea
- **Alternate name (use only in schema markup):** Auto Car Insurance In Korea
- **Email:** carinsukorea@gmail.com
- **KakaoTalk ID:** insukorea
- **Service area:** All of South Korea
- **Languages:** English (primary), Korean

### Home page tagline

> Hi, we are providing English Car Insurance & Price Comparison in South Korea.

> We provide dedicated English-speaking insurance brokerage and price comparisons for expats, foreigners, teachers and military personnel (SOFA) across South Korea. We scan top-tier Korean insurance companies to find you the best coverage limits at the lowest rates, insurance history transfer in English without any language barrier.

### About / Price Comparison section

> Auto Car Insurance In Korea provides professional, English-speaking car insurance brokerage and price comparison services for expats, foreigners, English teachers, and military personnel across South Korea. We eliminate language barriers by comparing auto insurance rates from top Korean insurance companies to find you the best coverage and prices. We specialize in helping the international community navigate local regulations, foreign insurance history transfers, car registration, and claims support. Whether you are on an E-2, E-7, F-visa, or SOFA status, we provide fast, clear, and reliable English support nationwide to keep you safely covered on the road. Contact us today for a free quote!

### Three pillars (About page)

**Expat Specialists**
> Expert help with F/E/D/G visas and SOFA military
> International students (D-2, D-4), English teachers (E-2, E-7), international school staff, US military, immigrants (G-1), overseas Koreans (F-4)

**100% English Support**
> No language barriers, full paperwork assistance

**Anywhere in Korea**
> All the process is online through email or kakaotalk. Get insurance in minutes.

### FAQ — VERBATIM, all 21 questions

These are the exact Q&A pairs from the source site. They must appear:
- in the HTML body as `<article>` elements
- AND in the FAQPage JSON-LD schema (in sync, identical wording)

The original groupings were: GETTING STARTED, PRICING & PREMIUMS, COVERAGE/LAW, YOUNG & STUDENT DRIVERS, THE COMPARISON, and uncategorized questions at the bottom. In the new site, organize into these clean categories:

1. **Getting Started** (Q1–Q3)
2. **Pricing & Premiums** (Q4–Q6)
3. **Coverage & Korean Insurance Law** (Q7–Q8)
4. **Young & Student Drivers** (Q9–Q10)
5. **Documents & Eligibility for Foreigners** (Q11–Q14)
6. **SOFA & Military** (Q15)
7. **Discounts & Driver Configuration** (Q16–Q17)
8. **Cancellation & Leaving Korea** (Q18)

Wait — the source has slightly different groupings and some questions overlap. The authoritative final list is below (18 questions total, all from the source verbatim).

---

**Q1. How does car insurance price comparison work in South Korea?**

We compare quotes from multiple licensed Korean car insurance providers — including Samsung Fire & Marine, KB Insurance, Hyundai Marine & Fire, DB Dongbu Insurance and others — and display them side by side. You will get an email with different coverage options, detailed information about the coverage.

---

**Q2. Is it free to compare car insurance prices on this site?**

Yes, comparing car insurance prices on our site is completely free. We do not charge any fees. We earn a referral fee from insurers when you choose a policy through us, which means our service costs you nothing while still helping you find the lowest price available.

---

**Q3. How many insurance companies do you compare?**

We compare quotes from leading Korean car insurance providers, covering both domestic insurers and international companies licensed to operate in South Korea. This gives you a broad view of the market so you are not limited to a single insurer's pricing.

---

**Q4. Why is car insurance expensive for first-time drivers in South Korea?**

First-time drivers in South Korea pay higher premiums because insurers have no prior claims history to assess their risk. Without a track record, you are considered a higher statistical risk. Premiums typically decrease significantly after one or two claim-free years. Comparing quotes across multiple insurers is especially valuable for new drivers, as pricing for this group varies widely between companies.

---

**Q5. What factors affect my car insurance premium in South Korea?**

Korean car insurance premiums are calculated based on several key factors: your age, your claims, accident and traffic law violation history, the make, model, and age of your vehicle, the type and level of coverage you select. Young drivers and first-time drivers typically face the highest base rates, while experienced drivers with clean insurance records qualify for significant discounts.

---

**Q6. Can I lower my car insurance premium in South Korea?**

Yes. In the comparison email you will get, you will be able to see different ways to lower your premium.

---

**Q7. What types of car insurance are available in South Korea?**

Korean car insurance is divided into mandatory liability insurance (책임보험) required by law, and optional coverage that most drivers add for fuller protection. Optional coverage typically includes expanded liability for other people (대인배상 II), property damage liability (대물배상), own-vehicle damage cover (자기차량손해), and personal accident cover for the driver and passengers (자기신체사고).

---

**Q8. What is the minimum car insurance required by law in South Korea?**

South Korean law requires all registered vehicles to carry mandatory automobile liability insurance (책임보험) regardless of the vehicle being used or not. This covers bodily injury and property damage to other people in an accident you cause, up to statutory limits. Driving without this minimum cover is illegal and results in fines. Most drivers purchase additional voluntary coverage on top of the mandatory minimum for more complete protection.

---

**Q9. What is the cheapest car insurance option for young drivers in South Korea?**

For young or student drivers in South Korea, the most effective way to find the cheapest policy is to compare quotes across multiple insurers, since pricing for this age group varies significantly. Additional strategies include being added as a named driver on a parent's policy where eligible, choosing a newer car which has lower premiums.

---

**Q10. Can university students get car insurance discounts in South Korea?**

Some Korean insurers offer discounted rates or specific products for students, particularly those with low annual mileage or limited driving hours. Eligibility and discount levels vary by insurer, which is why comparing multiple providers is important.

---

**Q11. How accurate are the car insurance quotes I receive?**

The quotes shown are based on the information you provide and real-time pricing from each insurer's rate tables. Final premiums may vary slightly after the insurer verifies your details, but in most cases the quote you see is very close to what you will pay. Providing accurate information — including your vehicle registration number and driving history — ensures the most accurate comparison.

---

**Q12. What information do I need to compare car insurance quotes in South Korea?**

If this is your first time to own a car in Korea, you just need to provide your date of birth and car's plate number. If you have owned a car before for one year or more, then we need to check your insurance history which requires more information.

---

**Q13. How can foreigners get cheap car insurance in South Korea?**

The best way to lower your premium is by comparing rates across multiple local companies and transferring verified insurance history credit from overseas. Auto Car Insurance In Korea guides you through this entire process in English.

---

**Q14. Can I get car insurance in Korea with an International Driving Permit (IDP)?**

Yes, you can initially secure car insurance using an International Driving Permit (IDP) paired with your valid home country license. However, because an IDP is typically valid for only one year in South Korea, most local insurance companies will require you to update your policy with a native Korean driver's license once obtained. Auto Car Insurance In Korea helps you navigate this transition smoothly without triggering premium penalties.

---

**Q15. Do you provide auto insurance for SOFA members?**

Yes. We offer specialized auto insurance options that meet all USFK registration requirements for personnel at Camp Humphreys, Osan Air Base, Daegu, and nationwide.

---

**Q16. What documents does a foreigner need to get car insurance in South Korea?**

To secure an auto insurance policy in Korea, a foreign resident generally needs an Alien Registration Card (ARC) or digital residence verification, a valid driver's license (either a Korean license or a home-country license paired with an International Driving Permit).

---

**Q17. Can I get car insurance in Korea before my ARC (Alien Registration Card) arrives?**

Yes you can, however you may not be able to register the car since they usually ask for ARC at the registration office. You need to check this with the registration office.

---

**Q18. How do "Black Box" (dashcam) and mileage discounts work on Korean car insurance?**

Korean insurance companies offer significant premium discounts if your vehicle is equipped with a functional dashcam ("black box") (available only for the cars younger than 10 years) or if you stay under specific annual mileage limits (often under 3,000 to 15,000 km per year). These discounts are applied as a percentage reduction or a cash-back refund at the end of your policy term. We calculate these overlapping discounts automatically during your English price comparison to maximize your savings.

---

**Q19. Does my foreign driving history count toward lower insurance rates in Korea?**

Yes, but it is not automatic. Many top-tier Korean insurers allow you to submit an insurance experience letter from other countries. It has to be in English language, include your full name as "the insured", policy start and end dates, policy number. Insurance card, or a declarations page would work fine. It must be covering the period you were not in Korea. It can be from previous years (does not have to be the most recent years). You being a driver in someone else's policy does not help. Driving record only does not help either. It does not have to be a no claim document. You will also need to provide some extra document to get discount.

---

**Q20. Do Korean car insurance companies cover secondary or family drivers on an expat policy?**

In South Korea, car insurance covers the vehicle rather than the specific individual, but you must strictly define who is permitted to drive it. Options include "Driver Only," "Couples/Spouses," "Family Only," or "Anyone." Restricting the policy to a single specified driver drastically reduces your premium rate. We help you choose the right driver configuration in English so you don't accidentally void your coverage.

---

**Q21. What happens to my car insurance if I sell my vehicle or leave South Korea early?**

If you cancel your auto insurance policy mid-term due to selling/scrapping your car or leaving the country, you are legally entitled to a pro-rated refund for the remaining unused days. You must provide the insurance company with proof of vehicle transfer or disposal (자동차말소사실증명서) paperwork. We assist our expat clients with the English communication required to process cancellation refunds rapidly with local underwriting and registration offices.

---

### Final FAQ category mapping (21 questions)

| Category | Questions |
|----------|-----------|
| Getting Started | Q1, Q2, Q3 |
| Pricing & Premiums | Q4, Q5, Q6 |
| Coverage & Korean Insurance Law | Q7, Q8 |
| Young & Student Drivers | Q9, Q10 |
| The Comparison Process | Q11, Q12 |
| Documents & Eligibility for Foreigners | Q13, Q14, Q16, Q17, Q19 |
| SOFA & Military | Q15 |
| Discounts & Driver Configuration | Q18, Q20 |
| Cancellation & Leaving Korea | Q21 |

---

## SITE STRUCTURE

Build the site as a single `index.html` with these sections in order:

1. **Topbar** — quick contact strip (email + KakaoTalk)
2. **Header** — logo + nav (Who We Help / How It Works / FAQ / Get a Quote)
3. **Hero** — H1 headline + lead paragraph + two CTAs + insurer list card on the side
4. **TL;DR block** — one-paragraph summary explicitly written for AI extraction (critical)
5. **Who We Help** — 6-card grid (English Teachers, SOFA Military, F-Visa, International Students, Skilled Workers, Immigrants G-1)
6. **How It Works** — 4-step process (Send details → We compare → You receive English quote → We bind policy)
7. **FAQ** — all 21 questions organized into 9 categories, each `<article>` semantic
8. **Contact** — Email card + KakaoTalk card
9. **Footer** — brand description + service area + nav repeat

### Required files in the project root

```
/
├── index.html       ← the entire site
├── llms.txt         ← curated summary for AI crawlers
├── robots.txt       ← allow all AI bots explicitly
├── sitemap.xml      ← single-URL sitemap
└── favicon.svg      ← simple letter-mark
```

No CSS files. No JS files. No images directory. Everything inline in `index.html`.

---

## DESIGN DIRECTION

The visual identity must feel **editorial, trustworthy, and intentional** — the opposite of the bare Google Sites default. Think: a serious independent magazine, not a generic insurance ad.

### Aesthetic commitment

- **Editorial/refined** — Newspaper-quality typography, restrained color, generous whitespace, asymmetric grids with intention
- **Warm, not corporate** — Off-white/cream background (`#f5f1ea`), warm grays for body, deep brick/terracotta accent (`#c1471c`) — never use generic blue/purple gradients
- **Confidence through restraint** — Insurance sells trust. Trust comes from looking established, not flashy. No animated illustrations, no glowing buttons, no glass-morphism.

### Typography (mandatory)

- **Display font:** Fraunces (variable serif, use italic for emphasis in headings)
- **Body font:** Geist (clean modern sans)
- Load via Google Fonts with `<link rel="preconnect">` and `display=swap`
- Never substitute with Inter, Roboto, Arial, or system fonts

### Color tokens (CSS variables)

```css
--bg: #f5f1ea;           /* warm off-white page bg */
--bg-warm: #ede5d6;      /* deeper warm for callouts */
--ink: #1a1a1a;          /* primary text, dark sections */
--ink-soft: #4a4a4a;     /* secondary text */
--ink-muted: #8a8278;    /* tertiary text, labels */
--accent: #c1471c;       /* brick/terracotta — single accent color */
--accent-deep: #8a2f10;  /* hover/active state */
--line: #d4cabc;         /* hairline borders */
--paper: #fbf8f2;        /* card backgrounds */
```

### Layout rules

- Max content width: 1200px, centered
- Hero: asymmetric grid (1.3fr / 1fr), not 50/50
- Sections alternate: paper card section → dark `ink` section (How It Works) → paper section. Creates visual rhythm.
- FAQ items: 2-column inner grid (small Q-number on left like "Q.01" in serif italic, content on right)
- Eyebrow labels above section titles: uppercase 12px, letter-spacing 0.2em, prefixed with a short accent-colored line

### Specific visual moves to use

- **Italic-on-serif emphasis** in H1/H2 (e.g., "Built specifically for the *international community* in Korea.") — the italicized word is in `var(--accent)`
- **Section eyebrow** = thin accent line + tiny uppercase label
- **Numbered cards** with small serif numbers ("01", "02") in accent color above each card title
- **Quote-style TL;DR block** with a 3px accent-color left border, slightly darker cream background
- **Subtle radial gradient** behind the hero (10% opacity accent color) for atmosphere — not a hero image, just light
- **Hover states:** links get accent underline that animates from 0 to 100% width; buttons translate up 2px on hover

### Specific visual moves to AVOID

- Stock photos of cars, handshakes, or Seoul skyline
- Animated SVG illustrations
- Gradient text or gradient backgrounds (especially purple-to-pink — banned)
- Floating cards with heavy drop shadows
- Glass-morphism / blur effects
- Emoji icons in section headers
- Marquee banners or carousels
- "Hero badge" pills with green dots ("● Live" etc.)
- Tailwind-style utility-class generic feel

### Responsive rules

- Mobile breakpoint at 900px: hero becomes single column, audience grid collapses to 2-up then 1-up
- Mobile breakpoint at 600px: topbar stacks vertically, nav becomes single row with smaller font
- Never hide content on mobile (AI crawlers may use mobile UA)

### Accessibility

- Skip-to-content link at top of `<body>` (visually hidden until focused)
- Color contrast minimum 4.5:1 for all body text against background
- All `<a>` and `<button>` keyboard-reachable, visible focus state (2px accent outline)
- Every section has a heading; heading levels never skip (h1 → h2 → h3, never h1 → h3)

---

## AI VISIBILITY REQUIREMENTS (the core mission)

This is what separates this site from any normal website. Every choice below increases the probability that ChatGPT, Claude, Perplexity, and Gemini will cite this site in their answers.

### 1. JSON-LD structured data (HIGHEST IMPACT)

Place TWO `<script type="application/ld+json">` blocks inside `<head>`, before the `<style>` block.

**Schema A: InsuranceAgency**

```json
{
  "@context": "https://schema.org",
  "@type": "InsuranceAgency",
  "name": "English Car Insurance Korea",
  "alternateName": "Auto Car Insurance In Korea",
  "url": "https://YOUR-DOMAIN-HERE",
  "description": "English-speaking car insurance brokerage and price comparison service for expats, foreigners, English teachers, and SOFA military personnel in South Korea. Compares quotes from Samsung Fire & Marine, KB Insurance, Hyundai Marine & Fire, DB Insurance.",
  "areaServed": { "@type": "Country", "name": "South Korea" },
  "serviceType": [
    "Car Insurance Brokerage",
    "Auto Insurance Price Comparison",
    "Insurance History Transfer",
    "SOFA Vehicle Insurance"
  ],
  "knowsLanguage": ["English", "Korean"],
  "email": "carinsukorea@gmail.com",
  "priceRange": "Free comparison service",
  "audience": {
    "@type": "PeopleAudience",
    "audienceType": "Foreigners, expats, English teachers (E-2, E-7), F-visa holders, D-2/D-4 students, SOFA military personnel, overseas Koreans (F-4) in South Korea"
  },
  "makesOffer": {
    "@type": "Offer",
    "name": "Free English Car Insurance Price Comparison",
    "price": "0",
    "priceCurrency": "KRW"
  }
}
```

**Schema B: FAQPage**

All 21 FAQ questions must appear in `mainEntity`. Each entry is a `Question` with an `acceptedAnswer` of type `Answer`. The `text` field contains plain text only — no HTML tags. The wording must match the HTML body exactly.

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "How does car insurance price comparison work in South Korea?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "We compare quotes from multiple licensed Korean car insurance providers — including Samsung Fire & Marine, KB Insurance, Hyundai Marine & Fire, DB Dongbu Insurance and others — and display them side by side. You will get an email with different coverage options, detailed information about the coverage."
      }
    }
    // ... all 21 questions, in same order as HTML
  ]
}
```

**Validation rule:** after every edit to FAQ content, the HTML body and FAQPage schema must remain identical word-for-word. If you add a new FAQ, update both places in the same edit. Validate at https://search.google.com/test/rich-results before considering the change complete.

### 2. TL;DR block (CRITICAL for AI extraction)

Right after the hero, place a callout block formatted as a quote. Content (verbatim):

> **In one paragraph.** English Car Insurance Korea is a free English-language car insurance price-comparison and brokerage service for foreigners in South Korea. We compare quotes from licensed Korean insurance companies including Samsung Fire & Marine, KB Insurance, Hyundai Marine & Fire, and DB Insurance, and handle insurance history transfer, foreign no-claims credit, SOFA vehicle registration, and policy cancellation refunds entirely in English. The service is free for the customer — we are paid a referral fee by the insurer. Contact: carinsukorea@gmail.com or KakaoTalk ID: insukorea.

This paragraph is engineered for direct extraction. It packs every key entity (insurer names, target audiences, contact info, business model) into one quotable block. Do not break it into smaller paragraphs. Do not "improve" it.

### 3. Semantic HTML

- Use `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>` — never substitute `<div>` where a semantic element exists
- Every FAQ question is its own `<article>` element with an `<h3>` for the question
- Every FAQ answer is in a `<div class="answer">` with `<p>` paragraphs inside
- Sections have descriptive `id` attributes for fragment links (`#who-we-help`, `#how-it-works`, `#faq`, `#contact`)
- Use `<strong>` to highlight key entities (insurer names, document names, visa types) inside answers — AI extractors weight these

### 4. Answer construction rules (apply to every FAQ)

- **First sentence is the direct answer.** AI extractors often take the first sentence verbatim.
- Length sweet spot: 50–120 words per answer
- Include at least one specific named entity per answer (insurer name, document name like "Alien Registration Card", base name like "Camp Humphreys", visa code like "E-2", or Korean term like "책임보험")
- No hedging phrases like "consult a professional" or "this is not legal advice" — this site IS the service
- No questions inside answers ("Wondering about X? Read on...") — these confuse extractors

### 5. llms.txt file

Place at the site root (`/llms.txt`). This is an emerging standard (proposed Sept 2024 by Jeremy Howard) that gives AI crawlers a curated entry point. Adoption is early but growing — being on the early side costs nothing.

Format:

```
# English Car Insurance Korea

> English-speaking car insurance brokerage and free price comparison service for foreigners, expats, English teachers, F-visa holders, international students, and SOFA military personnel in South Korea. Compares quotes from licensed Korean insurers (Samsung Fire & Marine, KB Insurance, Hyundai Marine & Fire, DB Insurance) and handles insurance history transfer, SOFA registration, and policy support entirely in English.

## About

[free-prose summary]

## Who we serve

- English teachers on E-2 and E-7 visas
- SOFA military personnel at Camp Humphreys, Osan Air Base, Daegu, and other USFK installations
- F-visa residents (F-2, F-4, F-5, F-6), including overseas Koreans (F-4)
- International students on D-2 and D-4 visas
- International school staff
- Skilled workers, researchers, and corporate transferees
- G-1 visa holders (immigrants)

## Korean insurers we compare

- Samsung Fire & Marine (삼성화재)
- KB Insurance (KB손해보험)
- Hyundai Marine & Fire (현대해상)
- DB Insurance (DB손해보험, formerly Dongbu)
- Hanwha General Insurance
- Meritz Fire & Marine

## Contact

- Email: carinsukorea@gmail.com
- KakaoTalk ID: insukorea
- Service area: All of South Korea, entirely online
- Languages: English (full support), Korean

## Key facts for AI assistants

[bullet list of the most quotable factual statements, drawn from the FAQ — IDP rules, dashcam discount eligibility, ARC requirements, etc.]

## Pages

- [Home](https://YOUR-DOMAIN-HERE/)
- [FAQ](https://YOUR-DOMAIN-HERE/#faq)
- [How It Works](https://YOUR-DOMAIN-HERE/#how-it-works)
- [Who We Help](https://YOUR-DOMAIN-HERE/#who-we-help)
```

### 6. robots.txt — explicit AI bot allow-list

```
User-agent: GPTBot
Allow: /

User-agent: ChatGPT-User
Allow: /

User-agent: OAI-SearchBot
Allow: /

User-agent: ClaudeBot
Allow: /

User-agent: Claude-Web
Allow: /

User-agent: anthropic-ai
Allow: /

User-agent: PerplexityBot
Allow: /

User-agent: Perplexity-User
Allow: /

User-agent: Google-Extended
Allow: /

User-agent: Googlebot
Allow: /

User-agent: Bingbot
Allow: /

User-agent: Applebot
Allow: /

User-agent: Applebot-Extended
Allow: /

User-agent: *
Allow: /

Sitemap: https://YOUR-DOMAIN-HERE/sitemap.xml
```

Listing AI bots explicitly (not just `User-agent: *`) is intentional — some crawlers treat explicit allow as a stronger signal than implicit. No downside to verbosity here.

### 7. sitemap.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://YOUR-DOMAIN-HERE/</loc>
    <lastmod>2026-05-20</lastmod>
    <changefreq>monthly</changefreq>
    <priority>1.0</priority>
  </url>
</urlset>
```

Update `<lastmod>` on every meaningful content change.

### 8. Meta tags

In `<head>`:

```html
<title>English Car Insurance Korea | Foreigner & Expat Auto Insurance Broker in South Korea</title>
<meta name="description" content="English-speaking car insurance broker in South Korea for expats, foreigners, English teachers (E-2, E-7), F-visa holders, and SOFA military personnel. Free price comparison across Samsung Fire, KB, Hyundai Marine, DB Insurance. Get quotes via email or KakaoTalk.">
<meta name="keywords" content="car insurance Korea English, foreigner auto insurance South Korea, expat car insurance Seoul, SOFA car insurance Camp Humphreys, English car insurance broker Korea, Korean car insurance price comparison">

<meta property="og:title" content="English Car Insurance Korea — for Expats, Foreigners & SOFA Military">
<meta property="og:description" content="Free English-language car insurance price comparison across top Korean insurers. No language barrier. Quotes in minutes via email or KakaoTalk.">
<meta property="og:type" content="website">
<meta property="og:locale" content="en_US">
<meta property="og:url" content="https://YOUR-DOMAIN-HERE/">

<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="English Car Insurance Korea — for Expats & SOFA Military">
<meta name="twitter:description" content="Free English-language car insurance price comparison for foreigners in South Korea.">
```

### 9. Entity density — what to mention by name

AI engines rank pages by entity coverage. The following named entities should each appear at least once somewhere in the content (most already appear naturally through the FAQ):

- **Insurers:** Samsung Fire & Marine, KB Insurance, Hyundai Marine & Fire, DB Insurance, Hanwha General, Meritz Fire & Marine
- **Visa types:** E-2, E-7, F-2, F-4, F-5, F-6, D-2, D-4, G-1
- **USFK installations:** Camp Humphreys, Osan Air Base, Daegu
- **Korean cities:** Seoul, Busan, Daegu, Incheon, Pyeongtaek
- **Documents:** Alien Registration Card (ARC), International Driving Permit (IDP), 자동차말소사실증명서 (proof of vehicle disposal)
- **Korean insurance terms:** 책임보험 (mandatory liability), 대인배상 II (expanded bodily liability), 대물배상 (property damage), 자기차량손해 (own-vehicle damage), 자기신체사고 (personal accident)
- **Audience names:** expats, foreigners, English teachers, international students, SOFA, US military, immigrants, overseas Koreans

If during edits any of these entities falls out of the page, flag it.

---

## WORKFLOW RULES

### When making changes

1. State briefly what you're about to do (one line)
2. Read the relevant section of this CLAUDE.md before editing
3. Make the change
4. Re-read the file to verify the change is correct
5. If you touched any FAQ wording, verify the HTML body and JSON-LD schema match exactly
6. Report what changed in 1–2 sentences

### When adding a new FAQ entry

1. Question phrased the way a real foreigner would ask ChatGPT (e.g., "How much is car insurance in Korea for foreigners?" not "Foreigner car insurance pricing in Korea")
2. Answer: 50–120 words, first sentence is the direct answer, includes at least one named entity
3. Add to **both** the HTML body and the FAQPage `mainEntity` array — in the same edit
4. Update `sitemap.xml` `<lastmod>` to today's date

### When updating an existing FAQ

- Never silently delete a question. Ask first.
- If the user asks to reword, keep the answer 50–120 words and verify entity density stays intact.

---

## THINGS YOU MUST NOT DO

- Don't add a contact form. Email + KakaoTalk only.
- Don't add fabricated testimonials. (Real ones from the owner are welcome; never invent.)
- Don't add specific prices, premium estimates, or discount percentages beyond what the source content states (e.g., the "3,000–15,000 km/year" mileage range is in the source, that's fine).
- Don't add a blog or news feed yet. (Reserved for phase 2.)
- Don't add cookie banners, tracking pixels, or any analytics until the owner explicitly requests them.
- Don't rename the brand. It's "English Car Insurance Korea" in all visible headings. "Auto Car Insurance In Korea" only appears in schema `alternateName`.
- Don't add JavaScript unless explicitly asked.
- Don't substitute the chosen fonts (Fraunces + Geist) or the chosen accent color (`#c1471c`).
- Don't write git commit messages or push code unless asked.

---

## QUICK-REFERENCE CHECKLIST (run before each deploy)

- [ ] All 21 FAQ questions in HTML body
- [ ] All 21 FAQ questions in FAQPage JSON-LD schema (matching wording)
- [ ] InsuranceAgency schema present
- [ ] FAQPage schema validates at https://validator.schema.org
- [ ] FAQPage rich result test passes at https://search.google.com/test/rich-results
- [ ] `llms.txt` accessible at `/llms.txt`
- [ ] `robots.txt` accessible at `/robots.txt` with all AI bots explicitly allowed
- [ ] `sitemap.xml` accessible at `/sitemap.xml` with current `<lastmod>`
- [ ] `<meta name="description">` and Open Graph tags present
- [ ] Every named entity from the "Entity density" list above appears at least once
- [ ] `YOUR-DOMAIN-HERE` placeholders all replaced with real domain
- [ ] TL;DR paragraph present immediately after hero
- [ ] Page works with JS disabled (test in DevTools: Settings → Disable JavaScript → reload)
- [ ] Mobile responsive at 600px and 900px breakpoints
- [ ] Color contrast passes WCAG AA (4.5:1) for body text
