# ScanBeforeBuy buying guides

The public articles are served by the Railway-hosted [ScanBeforeBuy website](https://www.scanbeforebuy.com). Browse them at [Used Car Buying Guides](https://www.scanbeforebuy.com/guides).

## Source files

- `guides.json` defines the editorial catalog, topic groups, related links and original quick answers and practical checklists for 22 priority guides.
- `index.html` is a portable directory linking to the canonical articles on ScanBeforeBuy.
- The four ZIP files are the original delivery archives. The website has a checked-in copy of their guide HTML and applies the current catalog at render time.

## Publishing

1. Update `guides.json` here. Keep existing slugs unless the website also receives a permanent redirect.
2. From the `website` repository, run `node scripts/sync-seo-guides.mjs ../landingpages` to copy and validate the catalog. Run `node scripts/test-seo-pages.mjs` and `npm run build`.
3. Commit the synchronized catalog to `website`. Railway deploys the website from `main`; committing to this repository alone does not deploy production.
4. Check the live guide, its canonical URL and `/sitemap.xml` after deployment.

Use `updated` only for a substantive editorial change and record the actual date. The current catalog has tailored, evidence-focused answers and buyer checklists on 22 priority guides, including seller-phrase pages that previously shared repetitive wording. Keep answers useful on their own. State what a listing can establish, identify the documents or checks still needed, and link to specific next steps. Keep the original article at its clean, self-canonical production URL.

The scanner analyzes the listing text. It does not perform vehicle inspections or query official vehicle registries.
