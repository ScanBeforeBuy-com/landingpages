# ScanBeforeBuy SEO Landing Pages

This repository contains SEO landing pages for **ScanBeforeBuy**.

ScanBeforeBuy helps used-car buyers analyse the wording of vehicle listings before contacting the seller. The tool identifies missing information, vague claims, possible cost exposure, seller questions, document requests, red flags, and negotiation points.

The main website is:

https://www.scanbeforebuy.com

## Project Goal

Build and deploy approximately 100 high-quality English SEO landing pages targeting real search queries used by people buying used cars worldwide.

The pages must:

- Attract relevant organic traffic
- Answer a distinct buyer question or problem
- Provide useful standalone content
- Link naturally to the ScanBeforeBuy listing analyser
- Avoid duplicate or near-duplicate content
- Use consistent canonical URLs
- Be included in the XML sitemap
- Be deployable through the existing Vercel project

The purpose is not to create 100 lightly edited copies of the same page.

Each landing page must solve a clearly different search intent.

## Main Product URL

CTA links should normally point to:

https://www.scanbeforebuy.com/

ScanBeforeBuy analyses listing text only.

The product does not replace:

- A mechanical inspection
- A vehicle history report
- A VIN database search
- A title or ownership check
- An accident database search
- A registration check
- A recall check
- A finance or lien check

Landing pages must describe the product accurately.

## Deployment Platform

Deploy the SEO pages through the **Vercel project that currently controls**:

- `scanbeforebuy.com`
- `www.scanbeforebuy.com`

Do not deploy the SEO pages to a disconnected project or separate subdomain unless routing has been deliberately configured.

## Canonical Domain

Use the following canonical domain consistently:

```text
https://www.scanbeforebuy.com
```

All canonical URLs, sitemap entries, schema URLs, Open Graph URLs, and internal links should use this domain.

## URL Convention

Use clean URLs without `.html` and without a trailing slash.

Preferred format:

```text
https://www.scanbeforebuy.com/how-to-buy-car
https://www.scanbeforebuy.com/used-car-listing-red-flags
https://www.scanbeforebuy.com/questions-to-ask-used-car-seller
```

Avoid mixing these formats:

```text
/how-to-buy-car
/how-to-buy-car/
/how-to-buy-car.html
/how-to-buy-car/index.html
```

The canonical version should be:

```text
/how-to-buy-car
```

Other versions should redirect permanently to the canonical URL.

## Suggested Repository Structure

For static HTML pages, use one directory per clean URL:

```text
/
├── README.md
├── index.html
├── sitemap.xml
├── robots.txt
├── vercel.json
│
├── how-to-buy-car/
│   └── index.html
│
├── used-car-listing-red-flags/
│   └── index.html
│
├── questions-to-ask-used-car-seller/
│   └── index.html
│
├── used-car-documents-checklist/
│   └── index.html
│
└── hidden-costs-buying-used-car/
    └── index.html
```

Each public URL should load its directory `index.html`.

Example:

```text
/how-to-buy-car/index.html
```

should be publicly available as:

```text
https://www.scanbeforebuy.com/how-to-buy-car
```

## Recommended Vercel Configuration

Use `vercel.json` to normalise URL behaviour.

Example:

```json
{
  "cleanUrls": true,
  "trailingSlash": false,
  "redirects": [
    {
      "source": "/:path*/index.html",
      "destination": "/:path*",
      "permanent": true
    }
  ]
}
```

Test this configuration against the existing ScanBeforeBuy Vercel project before deploying all pages.

The following URL variants should not all return separate HTTP 200 responses:

```text
/how-to-buy-car
/how-to-buy-car/
/how-to-buy-car.html
/how-to-buy-car/index.html
```

Only the selected canonical version should return the final page directly.

## Landing Page SEO Requirements

Every indexable landing page must include:

- A unique `<title>`
- A unique meta description
- A unique H1
- A self-referencing canonical
- A mobile viewport meta tag
- An index and follow robots directive
- Open Graph metadata
- Relevant structured data
- Crawlable internal links
- A topic-specific CTA
- Useful visible content
- A visible FAQ when FAQ schema is used
- A relevant disclaimer
- Links to related ScanBeforeBuy pages

Recommended head elements:

```html
<meta charset="UTF-8">

<title>Unique Page Title | ScanBeforeBuy</title>

<meta
  name="description"
  content="A unique description written specifically for this page."
>

<meta
  name="robots"
  content="index, follow, max-image-preview:large"
>

<link
  rel="canonical"
  href="https://www.scanbeforebuy.com/example-page"
>

<meta
  name="viewport"
  content="width=device-width, initial-scale=1.0"
>
```

## Canonical Requirements

Every landing page must use a unique self-referencing canonical.

Example:

```html
<link
  rel="canonical"
  href="https://www.scanbeforebuy.com/how-to-buy-car"
>
```

Do not point every landing page to the homepage.

Do not reuse the same canonical across several pages.

The canonical URL must match:

- The public browser URL
- The sitemap URL
- Internal links
- Open Graph URL
- Structured-data URLs
- Breadcrumb URLs

## Open Graph Requirements

Each page should include unique Open Graph values.

Example:

```html
<meta property="og:type" content="article">

<meta
  property="og:title"
  content="How to Buy a Used Car Without Missing Important Risks"
>

<meta
  property="og:description"
  content="Follow a practical process for assessing the listing, questioning the seller, checking the car, verifying documents, and negotiating."
>

<meta
  property="og:url"
  content="https://www.scanbeforebuy.com/how-to-buy-car"
>

<meta
  property="og:site_name"
  content="ScanBeforeBuy"
>
```

## Structured Data

Use structured data only when it accurately represents visible page content.

Possible schema types include:

- `WebSite`
- `WebPage`
- `Article`
- `BreadcrumbList`
- `FAQPage`

Each page must use its own:

- URL
- `@id`
- Headline
- Description
- Breadcrumb
- Publication date
- Modified date
- FAQ questions and answers

Do not copy schema URLs from another page without updating them.

Example Article schema:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "@id": "https://www.scanbeforebuy.com/how-to-buy-car#article",
  "headline": "How to Buy a Used Car Without Missing Important Risks",
  "description": "A practical guide to assessing a listing, questioning the seller, checking documents, inspecting the vehicle, and negotiating.",
  "datePublished": "2026-06-12",
  "dateModified": "2026-06-12",
  "author": {
    "@type": "Organization",
    "name": "ScanBeforeBuy",
    "url": "https://www.scanbeforebuy.com/"
  },
  "publisher": {
    "@type": "Organization",
    "name": "ScanBeforeBuy",
    "url": "https://www.scanbeforebuy.com/"
  },
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "https://www.scanbeforebuy.com/how-to-buy-car"
  }
}
</script>
```

Use the real publication and substantial-update dates.

## FAQ Schema

FAQ schema may be included when the page contains a visible FAQ section.

The visible question and answer must match the structured-data question and answer.

Do not add FAQ schema for questions that are not visible on the page.

Example:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What should I check before buying a used car?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Check the listing, seller identity, vehicle documents, maintenance history, physical condition, test-drive behaviour, and independent inspection results before committing."
      }
    }
  ]
}
</script>
```

## Content Quality Rules

The 100 pages must not be created by changing only:

- The title
- The keyword
- The marketplace name
- The country name
- The vehicle type
- The seller type
- A few sentences

Each page must have its own search intent and useful outcome.

Every page should contain several topic-specific elements, such as:

- A unique direct answer
- A distinct introduction
- A dedicated checklist
- Specific warning signs
- Specific questions to ask
- Relevant documents to request
- A unique example
- A topic-specific comparison
- A topic-specific CTA
- A unique FAQ
- Distinct internal links
- A conclusion written for the exact query

## Page Types

The 100 pages should be divided across several page formats.

Do not use exactly the same content structure for every page.

### 1. Buyer Guides

Examples:

```text
/how-to-buy-car
/used-car-buying-checklist
/how-to-inspect-used-car
/how-to-test-drive-used-car
/how-to-buy-used-car-online
```

Suggested structure:

```text
Direct answer
→ Step-by-step process
→ Checklist
→ Common mistakes
→ ScanBeforeBuy CTA
→ FAQ
→ Related guides
```

### 2. Listing Risk Pages

Examples:

```text
/used-car-listing-red-flags
/used-car-listing-missing-information
/signs-car-seller-is-hiding-something
/used-car-listing-risk-checker
```

Suggested structure:

```text
Problem explanation
→ Red flags
→ Good and bad examples
→ Seller questions
→ Verification steps
→ ScanBeforeBuy CTA
→ FAQ
```

### 3. Seller Phrase Pages

Examples:

```text
/what-does-needs-tlc-mean
/what-does-sold-as-is-mean
/what-does-mechanic-special-mean
/what-does-just-needs-a-sensor-mean
```

Suggested structure:

```text
Meaning
→ Innocent interpretation
→ Risky interpretation
→ Evidence to request
→ Questions to ask
→ Example listing
→ Walk-away conditions
→ ScanBeforeBuy CTA
→ FAQ
```

### 4. Checklist and Verification Pages

Examples:

```text
/used-car-documents-checklist
/questions-to-ask-used-car-seller
/documents-to-request-before-buying-used-car
/how-to-verify-used-car-service-history
```

Suggested structure:

```text
Direct conclusion
→ Prioritised checklist
→ Required evidence
→ Consequences of missing information
→ Questions to copy
→ ScanBeforeBuy CTA
→ FAQ
```

### 5. Cost and Negotiation Pages

Examples:

```text
/hidden-costs-buying-used-car
/used-car-negotiation-checklist
/how-to-negotiate-used-car-price
/used-car-negotiation-points
```

Suggested structure:

```text
Cost or negotiation problem
→ Confirmed versus possible costs
→ Evidence needed
→ Negotiation method
→ Example
→ ScanBeforeBuy CTA
→ FAQ
```

### 6. Seller and Purchase Scenarios

Examples:

```text
/buying-used-car-private-seller
/buying-used-car-from-dealer
/buying-used-car-remotely
/buying-used-car-without-seeing-it
/buying-used-car-without-inspection
```

Suggested structure:

```text
Scenario-specific risks
→ What to verify
→ Questions to ask
→ Payment or transaction concerns
→ Walk-away conditions
→ ScanBeforeBuy CTA
→ FAQ
```

### 7. Regional English Pages

Examples:

```text
/uk-used-car-buying-checklist
/australia-used-car-buying-checklist
/canada-used-car-buying-checklist
/new-zealand-used-car-buying-checklist
/ireland-used-car-buying-checklist
```

Regional pages must contain real local value.

Do not publish a country page by changing only the country name.

Regional pages should account for differences in:

- Terminology
- Ownership documents
- Inspection requirements
- Roadworthiness systems
- Marketplace practices
- Finance checks
- Buyer protections
- Common seller phrases

Country-specific claims must be researched and maintained.

## Internal Linking

The SEO pages must not be disconnected.

Every important page should be reachable through normal HTML links.

Each landing page should normally link to:

- The main ScanBeforeBuy tool
- One relevant hub page
- Two to five related landing pages
- One broader buyer guide

Use descriptive anchor text.

Good:

```html
<a href="/used-car-listing-red-flags">
  Learn the most common used-car listing red flags
</a>
```

Avoid:

```html
<a href="/used-car-listing-red-flags">
  Click here
</a>
```

## Suggested Hub Pages

Create hub pages to organise and distribute internal authority.

Possible hubs:

```text
/used-car-buying-guides
/used-car-listing-guides
/used-car-seller-questions
/used-car-documents
/used-car-negotiation
/used-car-listing-phrases
```

Every landing page should belong to one primary hub.

## CTA Requirements

CTA text should reflect the user's current intent.

Examples:

### Listing risk page

```text
Check this listing for red flags
```

### Missing-information page

```text
Find what the listing leaves out
```

### Seller-question page

```text
Generate questions for this seller
```

### Negotiation page

```text
Find negotiation points in the listing
```

### General buyer guide

```text
Analyze a used-car listing
```

CTA links should normally point to:

```text
https://www.scanbeforebuy.com/
```

Optional tracking parameters may be added to CTA links later.

Example:

```text
https://www.scanbeforebuy.com/?source=used-car-listing-red-flags
```

Tracking parameters must never be used in canonical URLs.

## Sitemap

The sitemap must be available at:

```text
https://www.scanbeforebuy.com/sitemap.xml
```

Every important canonical page must be included.

Only final canonical URLs should be listed.

Do not include:

- Redirecting URLs
- `.html` alternatives
- Trailing-slash alternatives
- Duplicate URLs
- Preview deployment URLs
- Test pages
- Pages blocked from indexing
- Deleted pages
- Non-canonical pages

Example:

```xml
<?xml version="1.0" encoding="UTF-8"?>

<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">

  <url>
    <loc>https://www.scanbeforebuy.com/</loc>
    <lastmod>2026-06-12</lastmod>
  </url>

  <url>
    <loc>https://www.scanbeforebuy.com/how-to-buy-car</loc>
    <lastmod>2026-06-12</lastmod>
  </url>

  <url>
    <loc>https://www.scanbeforebuy.com/used-car-listing-red-flags</loc>
    <lastmod>2026-06-12</lastmod>
  </url>

</urlset>
```

Use the real publication or substantial-update date for `<lastmod>`.

Do not change `<lastmod>` only because the sitemap was regenerated.

## Sitemap Maintenance

Update `sitemap.xml` whenever a page is:

- Added
- Removed
- Renamed
- Redirected
- Consolidated
- Substantially updated

When a URL is changed:

1. Remove the old URL from the sitemap.
2. Redirect the old URL to the closest relevant new page.
3. Update all internal links.
4. Update the canonical.
5. Update structured-data URLs.
6. Add the final destination URL to the sitemap.

## Robots.txt

The robots file should be available at:

```text
https://www.scanbeforebuy.com/robots.txt
```

Recommended content:

```text
User-agent: *
Allow: /

Sitemap: https://www.scanbeforebuy.com/sitemap.xml
```

Do not block files required to render and understand the pages.

## Deployment Checklist

Before deployment, confirm:

- [ ] The pages are in the correct Vercel project
- [ ] Each page has a unique title
- [ ] Each page has a unique meta description
- [ ] Each page has a unique H1
- [ ] Each page has a self-referencing canonical
- [ ] Canonical URLs use the selected no-trailing-slash format
- [ ] No canonical URL is duplicated
- [ ] Structured-data URLs match the canonical
- [ ] Open Graph URLs match the canonical
- [ ] Internal links use clean canonical URLs
- [ ] CTA links work
- [ ] Pages are mobile-friendly
- [ ] Pages return HTTP 200
- [ ] Duplicate URL versions redirect permanently
- [ ] No important page is blocked by robots.txt
- [ ] The sitemap contains all indexable pages
- [ ] The sitemap contains no redirected URLs
- [ ] The sitemap contains no duplicate URL variations
- [ ] The sitemap is deployed with the website

## Post-Deployment Testing

After deployment:

1. Open every new page manually.
2. Confirm the intended clean URL loads.
3. Confirm the canonical matches the browser URL.
4. Test the trailing-slash version.
5. Test `/index.html`.
6. Test any possible `.html` version.
7. Confirm duplicate variants redirect.
8. Confirm the final page returns HTTP 200.
9. Confirm internal links work.
10. Confirm CTA links work.
11. Inspect the HTML source.
12. Confirm the title and meta description.
13. Confirm schema URLs are correct.
14. Confirm visible FAQs match FAQ schema.
15. Open the sitemap.
16. Confirm the new URLs are listed.
17. Open robots.txt.
18. Confirm robots.txt references the sitemap.

## Google Search Console

After deployment:

1. Open Google Search Console.
2. Submit or resubmit:

```text
https://www.scanbeforebuy.com/sitemap.xml
```

3. Inspect the main hub pages.
4. Inspect the strongest buyer guides.
5. Inspect the most commercially relevant pages.
6. Run live URL tests.
7. Request indexing for priority pages.
8. Confirm Google can access each page.
9. Confirm Google detects the intended canonical.
10. Monitor indexing, crawling, and canonical reports.
11. Review impressions, clicks, CTR, and average position.
12. Improve pages that receive impressions but few clicks.
13. Strengthen pages ranking between positions 8 and 30.
14. Consolidate pages competing for the same search intent.
15. Rewrite or remove weak pages that remain thin or duplicative.

## Priority Indexing

Do not treat all pages as equally important.

Request indexing first for:

- Main hub pages
- Core commercial pages
- Strong buyer guides
- Pages linked prominently from the main website
- High-intent search pages
- Pages with the strongest standalone value

The sitemap and internal links should help Google discover the rest.

## Content Review Checklist

Before publishing any page, confirm:

- [ ] The page targets a real and distinct search intent
- [ ] The page gives the user a useful answer
- [ ] The page is useful before the CTA is clicked
- [ ] The content is materially different from other pages
- [ ] The page avoids unsupported mechanical claims
- [ ] The page avoids unsupported legal claims
- [ ] The product is described accurately
- [ ] The CTA matches the topic
- [ ] The internal links are relevant
- [ ] The examples are unique
- [ ] The FAQ is unique
- [ ] The canonical is correct
- [ ] Schema URLs are correct
- [ ] No placeholder text remains
- [ ] The page is ready to be indexed

## Avoid Keyword Cannibalisation

Do not create several pages targeting essentially the same search intent unless they deliver genuinely different outcomes.

Potentially overlapping examples:

```text
/used-car-ad-checker
/used-car-listing-checker
/used-car-advert-checker
/used-car-listing-analyzer
```

Before creating overlapping pages, decide whether they should:

- Be combined into one stronger page
- Target different regional terminology
- Provide different functionality
- Belong to different stages of the buyer journey

One strong page is normally better than several weak pages competing against each other.

## Measurement

Track performance for each landing page.

Important metrics:

- Indexing status
- Search impressions
- Organic clicks
- Search CTR
- Average search position
- Listing-analysis starts
- Completed report previews
- Full-report purchases
- Revenue per organic visit
- Conversion rate by landing page
- Search queries by landing page

Traffic alone is not the final goal.

The SEO pages should attract relevant used-car buyers and move them naturally toward analysing a real listing.

## Initial Production Plan

Recommended first phase:

- 10 buyer guides
- 15 listing-risk pages
- 15 seller-question and verification pages
- 20 seller-phrase pages
- 15 cost and negotiation pages
- 15 purchase-scenario pages
- 10 regional English pages

Total:

```text
100 landing pages
```

Pages should be produced and reviewed in groups rather than publishing all 100 without quality control.

Recommended batches:

```text
Batch 1: 10 pages
Batch 2: 15 pages
Batch 3: 25 pages
Batch 4: 25 pages
Batch 5: 25 pages
```

After each batch:

- Deploy
- Update the sitemap
- Test canonical URLs
- Check internal links
- Submit the sitemap
- Inspect priority pages
- Review early search signals
- Correct problems before scaling further

## Repository Responsibility

The person deploying this repository is responsible for:

- Using the correct Vercel project
- Preserving the canonical URL convention
- Deploying all page folders
- Updating `sitemap.xml`
- Maintaining `robots.txt`
- Testing redirects
- Confirming HTTP status codes
- Submitting the sitemap in Google Search Console
- Monitoring indexing and canonical errors
- Updating internal links when URLs change
- Preventing duplicate and near-duplicate pages
