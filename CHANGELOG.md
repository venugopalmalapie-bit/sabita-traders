# Sabita Traders website – change log

Every change to the live site is recorded here, newest first. Each change is one git commit,
so any change can be undone. Before each batch a backup branch is pushed (`backup-YYYY-MM-DD-...`) pointing at the live version.

How to roll back (GitHub web): open the repo → Commits → pick the commit → "Revert".
Or restore a whole backup: repo → branch menu → pick the `backup-...` branch → Code → Download ZIP.

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
