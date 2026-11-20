# Sabita Traders website – change log

Every change to the live site is recorded here, newest first. Each change is one git commit,
so any change can be undone. Before each batch a backup branch is pushed (`backup-YYYY-MM-DD-...`) pointing at the live version.

How to roll back (GitHub web): open the repo → Commits → pick the commit → "Revert".
Or restore a whole backup: repo → branch menu → pick the `backup-...` branch → Code → Download ZIP.

## 2026-11-21 – Technical audit, part 2: lighter Odia pages, faster Odia homepage
- Approved by: Venu (21 Nov 2026)
- Backup branch before change: `backup-2026-11-21-before-odia-slim`
- All template pages (48): template indentation removed; Odia pages keep only the translation entries they use (verified: 524 clicks/selects replayed, identical to the live site; no translation lost). Odia pages ~25% smaller (gzipped), e.g. or/index 39.5 KB -> 30.0 KB
- Homepage (EN + Odia): main photo sized for phones (`sizes="100vw"`), second hero photo marked low priority
- Odia homepage: main-photo preload now uses the phone-sized versions (it was downloading the photo twice); model cards now get phone-sized images (they had an empty srcset and loaded full-size)
- Results (Lighthouse mobile, all 60 pages): performance avg 96.3 -> 98.2 (lowest 86 -> 92); accessibility 97.7 -> 98.1; SEO 100. Odia homepage realistic phone test 91 -> 96, main photo 3.4 s -> 2.8 s
- Look and feel unchanged; no broken links, no script errors

## 2026-11-20 – New blog post: "Not eligible for the tractor subsidy?" (SEO/AEO/GEO/CRO)
- Approved by: Venu (20 Nov 2026)
- Backup branch before change: `backup-2026-11-20-before-not-eligible-post`
- New: `tractor-subsidy-not-eligible-odisha.html`, `or/tractor-subsidy-not-eligible-odisha.html` (built from the subsidy-guide page frame; author M Krishna Reddy, MD)
- Content: answer-first summary, "find your reason" table (Farmer ID, target full, permit lapsed, 5-year moratorium, implement refused, loan rejected), one section per reason, loan/exchange/KCC routes, group and rental routes, mistakes list, 7 FAQs, author box, linked official sources
- Facts checked against: Odisha FM-DBT Operational Modality 2026 (cl. 2.1 repeat subsidy 100/75/50%, 4.1 WSHG up to 33% target at 75%, 5.10 implements only for tractor owners, 5.11 lapsed permit 3-month wait); RBI collateral-free agri loans ₹2 lakh (6 Dec 2024); RBI MISS/KCC 2025-26 (7%, 3% prompt repayment, ₹3 lakh); Balaram notification (groups of 5+); AIF CHC minimum 4 machines (Canara Bank). Second-subsidy rupee figures (₹90,000 / ₹1,12,500) are our calculation from the 75% rule and are labelled as such
- CRO: WhatsApp button in the hero, a pre-filled WhatsApp "Ask us" on every reason row (message names the reason), two in-article help boxes (next target release; loan options), sticky side panel, enquiry form reworded; reasons table becomes stacked cards on mobile so the button stays visible
- Structured data: BlogPosting (citations, isBasedOn the subsidy guide), BreadcrumbList, FAQPage (7 Q&A)
- Site-wide: new card first on the Blog page (EN + Odia) and in the Blog's blogPost list; subsidy guide links to the new post (loan section + Read next, EN; Read next, Odia); sitemap.xml (+2 URLs) and llms.txt updated
- To undo: revert this commit

## 2026-11-21 – Technical audit fixes (speed, search markup, links, accessibility)
- Approved by: Venu (21 Nov 2026) – "fix all"; stock status (availability) held back pending his decision; Odia page-weight work (#4) to follow as its own step
- Backup branch before change: `backup-2026-11-21-before-tech-fixes`
- Fonts load without blocking the page on all pages; English pages no longer download the full Odia font (only the few Odia letters they show)
- Phone-sized copies of 20 large photos (480 px and 960 px) with srcset; homepage hero photo fetched first (fetchpriority + matching preload)
- Measured on a simulated slow phone (Lighthouse, devtools throttling): homepage speed 88 -> 96, main photo 3.9 s -> 2.8 s; Odia homepage 87 -> 92, 4.0 s -> 3.3 s
- Structured data: dealer map coordinates and price range on every page; 2WD/4WD product variants now carry an image; blog listing posts carry an image
- Links: 8 John Deere implement links (moved by John Deere) now point to John Deere's implements page, labelled "John Deere implement range"; Power & Technology 6.0 card points to John Deere India's YouTube channel
- Accessibility: yellow-on-green labels now white (contrast); logo link label matches its visible text
- Titles shortened on 6 pages and meta descriptions on 8 pages so Google does not cut them off

## 2026-11-21 – New About page
- Approved by: Venu (21 Nov 2026), copy and phone/desktop previews
- Backup branch before change: `backup-2026-11-21-before-about`
- New: `about.html`, `or/about.html`: farming-family story, 20+ years in agriculture and farm equipment (owner's statement), one window for subsidy (register, apply, follow up until credited), loan (11 partners), RTO registration and insurance help, exchange; service empathy section (no response-time promise yet); proof tiles (20+ years, only authorised dealer for Ganjam, 340+ tractors, 11 lenders, 22 blocks, 5-yr/5,000-hr warranty); 6 FAQs; WhatsApp CTAs
- Structured data: AboutPage + dealer record (with knowsAbout) + BreadcrumbList + FAQPage
- "About us" / "ଆମ ବିଷୟରେ" link in every footer; sitemap.xml (54 URLs); llms.txt entry; JPG link-preview image of the workshop
- Photo: existing workshop photo; swap for a team/showroom photo when available

## 2026-11-20 – Privacy notice and small cleanups
- Approved by: Venu (20 Nov 2026), including the two data-sharing lines
- Backup branch before change: `backup-2026-11-20-before-privacy`
- New: `privacy.html`, `or/privacy.html` (who we are, what the site collects: WhatsApp enquiries, Google Analytics, language choice, YouTube/Maps; how details are used and shared only on request; retention; how to correct or delete); "Privacy" / "ଗୋପନୀୟତା" link in every footer next to the GSTIN; sitemap.xml (52 URLs)
- Odia menu: "Exchange" now "ଏକ୍ସଚେଞ୍ଜ"
- Blog: "New guides every week" replaced with "Practical guides for Ganjam farmers" (EN + Odia)
- 5039D pages (EN + Odia): official John Deere India video "5039D and 5042D PowerPro" (click-to-play) + VideoObject
- Link previews: og:image now JPG copies in `images/og/` (15 images, ~1 MB) with width/height, so WhatsApp shows them reliably
- Comparison pages: analytics page label corrected (was "John Deere 5105")

## 2026-11-20 – Contact page: Managing Director line
- Approved by: Venu (20 Nov 2026). "Formerly Krishna Motors" deliberately not added (old Krishna Motors listings still show other brands; revisit once they are cleaned up)
- contact.html and or/contact.html business details: "Managing Director: M Krishna Reddy"

## 2026-11-20 – GSTIN added (lean version)
- Approved by: Venu (20 Nov 2026): GSTIN confirmed; partnership firm; MD name and former name deliberately left out
- Backup branch before change: `backup-2026-11-20-before-gstin`
- Footer on all 50 pages (EN + Odia): "GSTIN 21AEOFS3076G1ZY"
- Contact page (EN + Odia): small "Business details" block under the showroom card: Sabita Traders (partnership firm), GSTIN, link to the GST portal taxpayer search
- Structured data: legalName and taxID added to the dealer (AutoDealer) record on every page; llms.txt and llms-full.txt key facts

## 2026-11-20 – Fixes from the 100-visitor site audit (prices, Odia WhatsApp, phone layout, facts)
- Approved by: Venu (20 Nov 2026), after reviewing before/after previews
- Backup branch before change: `backup-2026-11-20-before-audit-fixes`
- Prices (homepage cards and all 20 model pages, EN + Odia): MRP shown first, after-subsidy price on its own labelled line ("After ₹1.2 lakh subsidy*: …"), 2WD and 4WD listed separately; note says the subsidy is subject to eligibility and DBT approval, with a link to the subsidy guide. Same figures as before, only the labelling changed
- Structured data: model page offers now carry the MRP as the price (were after-subsidy "lowPrice")
- Odia pages: WhatsApp messages now open in Odia (translated when the button is tapped; product names stay in English; the "[Website: …]" lead tag is kept)
- Phones: model pages show the model name, description and price box before the video and spec boxes (model name now ~540 px from the top, was ~1,330 px); the other-models buttons fit in one sliding row; the main menu fades at the right edge to show it scrolls
- Service booking form lists all 10 models
- Fixes: the "5050D" button on 12 model pages pointed to the page itself; comparison page said "the four tractors we sell" (we sell 10); top banner "Berhampur · Aska · Bhanjanagar" now reads "Showroom in Berhampur · serving all of Ganjam" (homepage and implements page); redirect page titles; llms-full.txt now lists all 10 models and the two newest pages
- Not changed (needs the dealer to confirm): implements page "5050D (45 HP model) · 5105 (35 HP model)" wording

## 2026-11-20 – Official John Deere videos near the top of 8 model pages (SEO/AEO/GEO/CRO, stopgap)
- Approved by: Venu (20 Nov 2026), as a stopgap until our own Odia walkaround videos
- Backup branch before change: `backup-2026-11-20-before-model-videos`
- Files: 3036EN, 5036D, 5042D, 5045D, 5050D, 5075E, 5310, 5405 model pages, English and `or/` (16 files)
- The small video tile in the photo strip is replaced by a large 16:9 video right under the main tractor photo, with a caption (title · John Deere India · length)
- Click-to-play: YouTube (privacy-enhanced youtube-nocookie.com) loads only when the visitor taps, so page speed is unchanged; the video keeps playing if the visitor switches 2WD/4WD; tap is tracked as `video_play`
- Structured data: VideoObject per page (title, upload date, length and thumbnail read from the official John Deere India YouTube channel on 20 Nov 2026)
- To undo: revert this commit; to replace with our own videos later, change the video ID on each page

## 2026-11-19 – New "Areas we serve" page for all 22 Ganjam blocks (SEO/AEO/GEO/CRO)
- Approved by: Venu (19 Nov 2026); owner counts, durability figures and tractor suggestions approved
- Backup branch before change: `backup-2026-11-19-before-areas-page`
- New: `john-deere-dealer-ganjam-blocks.html`, `or/john-deere-dealer-ganjam-blocks.html` (built from the Aska page frame by a generator script; one data table drives both languages)
- Content: proof stats (346 tractors, 235 villages, 88% of 10+ yr tractors in service, 4 in 5 choose 4WD), village/block search, 22 block cards by sub-division (owners, soil and crops from KVK Ganjam-I/II, suggested tractor + implement + price, WhatsApp buttons naming the block), 6 FAQs, structured data (dealer areaServed 22 blocks, BreadcrumbList, WebPage, FAQPage)
- Data sources: John Deere tractor population file (Oct 2023, totals only, no personal data); dealer sales file Jun 2022 – Oct 2026; KVK Ganjam-I report; KVK Ganjam-II block cropping systems; OrissaPOST (district agriculture office) for cotton and paddy procurement
- Known gap: Sanakhemundi has no KVK crop line (KVK Ganjam-II site blocks downloads)
- Site-wide: "Areas" / "ଅଞ୍ଚଳ" menu item before Contact on all pages; homepage "All 22 blocks of Ganjam" row; Contact page link; Aska and Bhanjanagar breadcrumbs now point to the new page; sitemap.xml (48 URLs) and llms.txt updated

## 2026-11-19 – Homepage prices and headings (SEO/AEO)
- Approved by: Venu (19 Nov 2026)
- Backup branch before change: `backup-2026-11-19-before-homepage-prices`
- Files: `index.html`, `or/index.html`, `sitemap.xml` (lastmod for / and /or/)
- Tractor cards: added each model's indicative price range (same figures as the model pages,
  llms.txt and schema); WhatsApp button "Ask price ›" renamed "Get on-road price ›"
  (Odia: "ଅନ୍-ରୋଡ୍ ଦାମ ଜାଣନ୍ତୁ ›"), same WhatsApp link and message
- Note under the grid: lower figure after Odisha subsidy (subject to eligibility), upper is MRP, tractor only
- Headings now carry search terms: John Deere tractor, tractor loans, old tractor exchange,
  John Deere service in Berhampur, Berhampur showroom, Ganjam farmers
- How the homepage is built: static HTML inside `<div id="app">` is pre-rendered from the
  template in the `DCRT.mount(...)` script + the `models` data; the Odia page uses Odia text in
  its template and the `DCRT_TR` dictionary for data values. Edit template/data, then re-render,
  so the static copy and the in-browser version stay identical.
