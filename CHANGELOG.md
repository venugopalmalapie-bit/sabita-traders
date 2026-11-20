# Sabita Traders website – change log

Every change to the live site is recorded here, newest first. Each change is one git commit,
so any change can be undone. Before each batch a backup branch is pushed (`backup-YYYY-MM-DD-...`) pointing at the live version.

How to roll back (GitHub web): open the repo → Commits → pick the commit → "Revert".
Or restore a whole backup: repo → branch menu → pick the `backup-...` branch → Code → Download ZIP.

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
