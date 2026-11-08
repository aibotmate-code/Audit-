# SEO Audit — intellicallabs.com

**Date:** 8 Nov 2026 · **Pages crawled:** 14 of 14 in sitemap (+ robots.txt, sitemap.xml, llms.txt)
**Business type:** Local service business / digital marketing agency (Bareilly, UP; service-area business)
**Method:** Raw HTML fetched via Firecrawl (direct access from the audit machine was blocked by its network policy). No Google Search Console, PageSpeed/CrUX, or backlink data was available, so performance scores are estimates from page structure, not measurements.

## SEO Health Score: 67 / 100

| Category | Weight | Score | Notes |
|---|---|---|---|
| Technical SEO | 22% | 72 | Crawlable and indexable; host (www vs non-www) inconsistencies and split analytics |
| Content Quality | 23% | 58 | Good local intent coverage; weak E-E-A-T and unverifiable claims |
| On-Page SEO | 20% | 70 | Strong service pages; homepage H1 and long titles |
| Schema / Structured Data | 10% | 68 | Lots of markup, but entity URLs, NAP and some types are wrong |
| Performance (CWV) | 10% | 65 (est.) | Not measured; ~42 KB inline CSS, 3 font families |
| AI Search Readiness | 10% | 80 | AI crawlers allowed, llms.txt present, answer-first blocks |
| Images | 5% | 55 | Almost no real images; only the logo |

## Top 5 critical / high issues
1. **Google Analytics is split across two IDs and missing on one page.** 5 pages (`/local-seo-bareilly`, `/whatsapp-marketing-bareilly`, and the 3 city pages) load `G-536888633`; the rest load `G-FJJDNKHL9W`; `/ai-marketing-agency-bareilly` has no tag. `G-536888633` doesn't match the usual GA4 ID format, so traffic from those pages is probably not being recorded in your main property.
2. **www vs non-www mismatch across signals.** Canonicals and the sitemap use `https://www.`, but `hreflang` on the homepage and service pages, every JSON-LD `@id`/`url`, breadcrumb items, logo, favicon and `twitter:image` point at `https://intellicallabs.com`. This sends Google conflicting signals about the preferred URL and splits your entity's identity in the Knowledge Graph.
3. **NAP inconsistency.** Schema postal code is `243005` (Saket, Prem Nagar); `llms.txt` says `243001`. The footer shows only "Bareilly, Uttar Pradesh" — no street address on any page. For a local SEO agency, NAP consistency is the core trust signal.
4. **Weak E-E-A-T for a YMYL-adjacent purchase (agency selection).** No founder/team names, no About page, no client names, testimonials, reviews or verifiable case studies. Blog posts are authored by "Organization", not a person. Meanwhile copy makes strong, unverifiable claims: "#1 digital marketing agency in Bareilly", "Bareilly's First AI-Powered Marketing Agency", "Only AI-powered growth agency…", "no other agency in Bareilly…".
5. **Blog index contains cards for articles that don't exist.** Of 7 cards on `/blog`, only 3 link to real posts. "Why Your Instagram Isn't Generating Inquiries" and the "Jewellery Shop Case Study" link to WhatsApp; two others link to service pages. Users and Google see dated "articles" that are actually CTAs.

## Top 5 quick wins
1. Replace `G-536888633` with `G-FJJDNKHL9W` on the 5 pages and add the tag to `/ai-marketing-agency-bareilly`.
2. Global find/replace `https://intellicallabs.com` → `https://www.intellicallabs.com` in hreflang, JSON-LD, favicon, logo and twitter:image.
3. Fix the postal code in one place (schema or llms.txt) and add the full street address to the footer.
4. Remove the `WebSite > SearchAction` (`/?s=` is not a working site search).
5. Shorten the homepage title (85 chars) to about 60, and rewrite the homepage H1 to include the main keyword.

---

## Technical SEO (72)
**What works:** HTTPS; `robots.txt` allows all crawlers, including AI bots; sitemap is declared and lists all 14 URLs; every page has a self-referencing canonical; `index, follow, max-snippet:-1, max-image-preview:large`; Google and Facebook verification tags; clean, descriptive URLs; breadcrumbs.

| Finding | Severity | Detail | Fix |
|---|---|---|---|
| Split / missing GA4 tags | High | See issue #1 | One GA4 ID site-wide, ideally via a shared include |
| hreflang & entity URLs on non-www host | High | Homepage `hreflang en-in` and `x-default` → `https://intellicallabs.com/`; same on 8 service/city pages. Blog posts are correct. | Point all alternates and @ids at the www canonical. For a single-language site, hreflang can simply be removed. |
| Sitemap `lastmod` stale or incorrect | Low | 10 URLs show `2025-08-22`; homepage claims `changefreq weekly`. | Generate `lastmod` from real edit dates. Drop `changefreq`/`priority` (Google ignores them). |
| robots.txt comment says "single-page site" | Info | Outdated comment; harmless | Update the comment |
| Invalid `<img width="auto">` | Low | Logo images on every page | Use numeric width and height (prevents layout shift) |
| `rel=icon type=image/png` points to a `.jpg` | Low | Favicon MIME mismatch | Serve a real `/favicon.ico` or PNG, 48×48 or larger |

## Content Quality (58)
**What works:** Each service and city page has distinct copy (city pages share only about 30% of 3-word phrases, so they aren't doorway clones); "Quick Answer" blocks; honest timelines ("3–6 months"); natural Hinglish in blog posts that fits the audience; FAQs that answer real questions.

| Finding | Severity | Detail | Fix |
|---|---|---|---|
| No people behind the business | High | No founder or team page, no bios, no LinkedIn | Add an About page with founder name, photo, background and LinkedIn; add `Person` authors to blog posts |
| Unverifiable superlatives | High | "#1", "First", "Only", "leading" in titles, meta and llms.txt | Replace with provable claims (years, number of clients, named results) |
| No proof of results | High | No testimonials, Google reviews, client logos or real case studies | Publish 2–3 case studies with client permission, numbers and screenshots; embed GBP reviews |
| Fake blog cards | High | See issue #5 | Remove the cards, or write the articles |
| Stats cited without links | Medium | "76% … Source: Google", "92% … Backlinko", "70%+ … BrightLocal" | Link the primary source and year, or remove |
| Thin blog | Medium | 3 real posts, `dateModified` = `datePublished` | 2 posts a month targeting the cluster below |

## On-Page SEO (70)
| Page | Issue |
|---|---|
| `/` | Title 85 chars (truncates). H1 "Most businesses don't have a content problem." has no keyword or location. Two identical Google Fonts `<link>` tags. |
| `/ai-marketing-agency-bareilly` | Title 87 chars; no hreflang; no GA |
| City pages | Titles 79–85 chars; meta descriptions 166–208 chars (truncate at about 155) |
| `/blog/ai-search-local-business-bareilly` | Title 94 chars |
| Internal linking | Good nav and footer links. City pages aren't linked from service pages; the blog links back to services, but services don't link to relevant posts. |

Suggested homepage: `<title>Digital Marketing Agency in Bareilly | Intellical Labs</title>` · `<h1>Digital Marketing Agency in Bareilly for Local Businesses</h1>` (keep the "content problem" line as a subheading).

## Schema & Structured Data (68)
Present: LocalBusiness+ProfessionalService, Organization, WebSite, WebPage, BreadcrumbList, Service/OfferCatalog, ItemList, FAQPage (on every page), BlogPosting, Blog, SpeakableSpecification. All JSON-LD blocks parse.

| Finding | Severity | Fix |
|---|---|---|
| All `@id`/`url` on non-www host | High | Use `https://www.intellicallabs.com/#business` etc. |
| Postal code 243005 vs 243001 (llms.txt) | High | Make it consistent everywhere, including GBP |
| `SearchAction` to `/?s=` (no site search) | Medium | Remove |
| FAQPage on every page | Low | Google limited FAQ rich results to government/health sites in 2023 and ended them on 2026-05-07, so this markup no longer earns a SERP feature. It is harmless entity markup. Keep only where FAQs are visible (they are). |
| `speakable` targets `#hero`, `#faq`, which don't exist on inner pages | Low | Point at real selectors, or remove (Speakable is still beta and news-only) |
| Footer microdata `LocalBusiness` (name, phone only) duplicates the JSON-LD entity | Low | Remove the microdata |
| BlogPosting `author` = Organization | Medium | Use `Person` with `url` and `sameAs` (LinkedIn) |
| `sameAs` contains a Maps short link and wa.me | Low | Use profile URLs: Instagram, LinkedIn, Facebook, GBP CID URL, JustDial |
| No `aggregateRating`/`review` | Info | Don't self-serve review stars (Google ignores self-serving LocalBusiness reviews); focus on GBP reviews |

## Performance (≈65, not measured)
Lab and field data were unavailable (no PageSpeed/CrUX access from this environment). From the HTML:
- 42 KB inline CSS and 26 KB inline JS on the homepage (147 KB HTML total). Fine for first paint, but nothing gets cached between pages.
- 3 Google Font families with 12+ weights, render-blocking, and loaded twice on the homepage → cut to 2 families and 4 weights, and self-host with `font-display: swap`.
- `.rev` elements start at `opacity:0` and depend on IntersectionObserver, so if JS is slow, content stays hidden (an LCP and rendering risk).
- Logo `logo.jpg` is preloaded and used at 44 px — serve a small WebP or SVG.

**Next step:** run PageSpeed Insights on `/` and `/local-seo-bareilly` (mobile) to get real LCP, INP and CLS.

## Images (55)
Only the logo is used as an `<img>` (2–3 per page, alt text present). There are no photos of the team, office, client work or results. For a local agency this hurts both conversion and E-E-A-T. Add a real team photo, an office or workspace photo, and screenshots of client results (with permission), each with descriptive alt text, WebP format, and explicit dimensions.

## AI Search Readiness (80)
**What works:** robots.txt explicitly allows GPTBot, OAI-SearchBot, ClaudeBot, PerplexityBot, Google-Extended, Applebot-Extended and more; `/llms.txt` exists and is detailed; "Quick Answer" blocks; FAQs written in plain answer format; consistent entity naming.

**Gaps:**
- `llms.txt` repeats unverifiable claims ("only", "leading") and has the wrong PIN code. AI systems weigh corroboration, and self-claims without third-party mentions get discounted.
- No third-party brand mentions found on-site (press, directories, LinkedIn, YouTube). Build profiles on JustDial, Sulekha, Clutch/GoodFirms, LinkedIn company page, and YouTube.
- Missing `/llms.txt` links to the city pages, the AI marketing page and blog posts.

## Recommended content cluster (blog)
Hub: `/local-seo-bareilly`. Spokes: "GBP categories for [industry] in Bareilly", "Google reviews strategy for Bareilly shops", "JustDial vs Google Maps for UP businesses", "Local SEO cost in Bareilly (2026)", "Case study: [real client]". Hub: `/whatsapp-marketing-bareilly`. Spokes: "WhatsApp Business API cost India", "Instagram DM to WhatsApp funnel setup", "WhatsApp catalog for jewellers".
