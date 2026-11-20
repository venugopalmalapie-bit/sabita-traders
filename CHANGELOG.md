# Sabita Traders website – change log

Every change to the live site is recorded here, newest first. Each change is one git commit,
so any change can be undone. Before each batch a backup branch is pushed (`backup-YYYY-MM-DD-...`) pointing at the live version.

How to roll back (GitHub web): open the repo → Commits → pick the commit → "Revert".
Or restore a whole backup: repo → branch menu → pick the `backup-...` branch → Code → Download ZIP.

## 2026-11-21 – Analytics tracking upgrade, new titles, 404 page
- Approved by: Venu (21 Nov 2026), after preview of titles and 404 page
- Backup branch before change: `backup-2026-11-21-before-analytics`
- Tracking script (all pages): WhatsApp tag now `[Website: <page> · Ref XXXX]`; events carry page, page_type, lang, placement, wa_ref; new events enquiry_submit, directions_click, review_click, next_step_click, emi_calculate, exchange_check, language_switch, social_click; video_click only for real video links. No name/phone/village sent to GA.
- Tracking added to About, Privacy, Compare (EN + OR), which had none.
- Unique data-page names for blog posts, subsidy guide, and Odia Blog/Careers/Areas.
- Staff flag: open any page once with `?staff=1` (undo with `?staff=0`) → visits sent with traffic_type=internal.
- Internal home links: `index.html` → `./`.
- New `404.html` (noindex).
- Titles: home "John Deere Tractor Showroom in Berhampur, Ganjam"; 10 model pages "… Price in Odisha, Specs | Berhampur" (EN + OR equivalents).

## 2026-11-21 – Two new blog posts: paddy puddling guide and on-road price explained (SEO/AEO/GEO/CRO)
- Approved by: Venu (21 Nov 2026), drafts approved in chat, publish approved after preview
- Backup branch before change: `backup-2026-11-21-before-puddling-onroad-posts`
- New: `best-tractor-for-paddy-puddling-ganjam.html` + `or/` (2WD vs 4WD, HP, Paddy Special Rotary Tiller vs Puddler cum Leveler, 4WD price table with MRP/after subsidy, buying season, see one working nearby; 5 FAQs; sources: Ganjam district agriculture dept (paddy 2,23,500 ha; irrigation 61% kharif / 12% rabi), Operational Modality 2026, our sales records)
- New: `tractor-on-road-price-odisha.html` + `or/` (MRP = tractor only; RTO registration OD07/OD32 with papers; insurance; DBT subsidy paid to the farmer's bank after verification; loan and hypothecation; how we help; 5 FAQs; sources: Operational Modality 2026, Motor Vehicles Act 1988 s.39/s.146, our subsidy guide)
- Both: answer-first summary, quick answer box, WhatsApp buttons and page-specific sticky WhatsApp message (Odia pages send Odia text), enquiry form, BlogPosting + FAQPage + BreadcrumbList schema, EN/OR hreflang
- Wiring: blog index cards and Blog schema (EN + OR); "What's in the on-road price ›" link in the price box on all 10 model pages (EN + OR); puddling guide link on 5045D, 5105, 5050D pages and the implements page; on-road link in the subsidy guide; sitemap (+4 URLs); llms.txt entries; llms-full.txt regenerated
- Checks: links 0 broken; clicks replayed with no script errors; form and sticky WhatsApp messages tested (EN + OR); Lighthouse new pages 99–100 performance, 98 accessibility, 100 SEO

## 2026-11-21 – Competitor and AI-search audit: fixes on the site
- Approved by: Venu (21 Nov 2026). Directory correction emails parked; comparison stays John Deere only; neutral price FAQ approved; no Telugu page for now
- Backup branch before change: `backup-2026-11-21-before-ai-search-fixes`
- Home (EN + OR): loan-and-subsidy FAQ corrected (register on Go-Sugam, then book on the FM-DBT portal) in text and schema; new FAQ "Is Sabita Traders the John Deere dealer in Berhampore, West Bengal?" (answer: no, Brahmapur, Ganjam, Odisha)
- 10 model pages (EN + OR): new FAQ "Why do some websites show a different price for this tractor?" (neutral, no competitor named), text and schema
- Subsidy guide (EN + OR): FM-DBT portal linked; new "Sources" list (FM-DBT portal, Go-Sugam, Operational Modality 2026 and 2024, Krushak Odisha); visible "Updated 21 Nov 2026"
- Schema on all pages: one consistent dealer node (same description; areaServed = Berhampur, Aska, Bhanjanagar, Ganjam district + all 22 blocks); contact languages English and Odia; John Deere logo removed from the careers JobPosting
- Dates: dateModified 2026-11-21 on pages whose content changed today; sitemap lastmod now taken from each page's dateModified or its last git change (was the same date on 52 URLs)
- llms-full.txt regenerated from the current English pages (27 pages; adds about, blocks, not-eligible; current prices and FAQs)
- Checks: all JSON-LD parses; no new markup errors; every click replayed, only the new FAQs/sources differ; no script errors

## 2026-11-21 – Design audit, Wave 2 (next steps, links, Odia readability, consistency)
- Approved by: Venu (21 Nov 2026)
- Backup branch before change: `backup-2026-11-21-before-design-wave2`
- "Next steps" strip above the footer (EN + OR): 10 model pages (compare, exchange value, subsidy, WhatsApp price), exchange (tractor prices, EMI, subsidy, WhatsApp), EMI (tractor prices, compare, subsidy, WhatsApp), service (book on WhatsApp, exchange, tractors, implements)
- Footer on all pages: added "Compare models" and "Subsidy guide"; home tractor section: "Compare models by HP and use" link
- Odia pages: 10/12/13/14px text bumped to 12/13.5/14.5/15px; line height 1.55 for table cells, labels, buttons and spans; underline offset for Odia script
- Exchange tool (EN + OR): WhatsApp message includes year/condition/tyres/papers only if the farmer chose them (or entered a price, so the estimate's inputs are sent)
- Desktop: menu kept on one row (smaller gaps 1101–1239px; padding fix when it wraps at ≤1100px); round floating WhatsApp button only on screens ≥1340px, placed in the empty side margin so it never covers content
- Buttons: all rounded; yellow reserved for WhatsApp ("Get directions", "Check exchange value" -> green; "Rate us on Google" -> outline)
- Accessibility: visible focus outline (dark ring + yellow halo); form field borders darker (#8C8A80)
- Checks: every click replayed on all pages, only new links differ; no script errors; no new markup errors; 0 broken links; CLS 0; Lighthouse unchanged (model 98, contact 99)

## 2026-11-21 – One delivery figure (340+) and real showroom photo on home
- Approved by: Venu (21 Nov 2026): "keep it 340+ as consistent"; showroom photo is real; all 11 lender tie-ups confirmed active (logos unchanged)
- Backup branch before change: `backup-2026-11-21-before-340-showroom-photo`
- Ganjam blocks page (EN + OR): headline stat, meta description and schema 346 -> 340+; llms.txt and llms-full.txt likewise. Source note (John Deere records, Oct 2023) unchanged
- Home (EN + OR): real Sabita Traders showroom/workshop photo added to "Visit our Berhampur showroom" (lazy, sized, srcset, no layout shift)
- Checks: clicks replayed on the 4 changed pages, only difference 346 -> 340+; no script errors

## 2026-11-21 – Design audit, Wave 1 (enquiries and phone usability)
- Approved by: Venu (21 Nov 2026)
- Backup branch before change: `backup-2026-11-21-before-design-wave1`
- Source: 8-reviewer design audit (mobile, conversion, layout, Odia typography, brand, accessibility, consistency, navigation); findings checked against the pages before fixing
- Model pages (10 EN + 10 OR): phone-only price strip under the title (MRP, after-subsidy, "Get today's on-road price on WhatsApp"); phone photo 420 -> 220px and title 48 -> 34px so it fits the first screen
- Sticky WhatsApp button now sends the page's own message: model pages (on-road price for the chosen drive), service, subsidy guide, not-eligible post, EMI, exchange, Aska, Bhanjanagar (EN + OR; Odia translation at tap verified)
- Home (EN + OR): "What do you need?" tiles under the hero (Buy / Loan & subsidy / Exchange / Service); compact tractor cards on phones; "Get on-road price" text link -> yellow "On-road price on WhatsApp" button; stats 2 per row on phones; "5 yrs" stat -> "5-year John Deere warranty (or 5,000 hours)"; hero text overlay even on phones
- Phone menu (all pages): order Home, Tractors, Finance, Service, Contact, Exchange, Implements, Resources, Blog, Areas; current page scrolled into view
- Odia contact form: dropdown had no selected option and sent English; options now carry the English values (translated at tap)
- Subsidy guide (EN + OR): 3-column subsidy table becomes stacked cards on phones
- Farmer resources (EN + OR): removed "delivery moments will be added here" line; YouTube thumbnails maxresdefault -> hqdefault (lighter, always exists)
- WhatsApp and phone icons on all WhatsApp/Call buttons (CSS, site-wide)
- Checks: every click/select replayed on all pages, only intended differences; 0 broken links; no new markup errors; CLS 0; home realistic phone test 97-98, main photo 2.3-2.4 s

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
