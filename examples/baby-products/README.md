# Example: baby products (2026-11-12 worked example)

This is the one real example output in this repo. It follows the
skill in `skill/SKILL.md` on a baby-products topic, using the
`topics/baby-products.json` plan: 5 DuckDuckGo Lite searches, 52
facts kept, 4 numbers quarantined, 48 new URLs (no previous report
existed for comparison).

Files:

- `2026-11-12-baby-pain-points-example.md` — the human-readable
  report.
- `2026-11-12-baby-pain-points-example.json` — the matching
  machine-readable report (fact list, clusters, numbers quarantine,
  comparison, coverage).
- `report-preview-1.svg` and `report-preview-2.svg` — rendered
  previews of the report (method/searches, and clusters), excerpted
  verbatim from the report file above. These are rendered previews,
  not browser screenshots.

The fact list, clusters, and numbers are unchanged from the run.
Run-method and account details were removed from these files before
publication, at the owner's request; nothing in the evidence itself
was edited.

## Read the caveats before reusing any of this

- **Snippet-level evidence only.** No thread, video, or product page
  was opened. Quotes are search-result titles and snippets. Post
  dates, upvote counts, and star ratings are **unverified**, except
  years shown in video titles.
- **Keyword grouping, not semantic analysis.** Clusters come from
  keyword matching in `topics/baby-products.json`. The largest
  cluster (registry waste, 39 of 52 facts) is broad partly because
  `registry` and `regret` match widely. Treat 1-item groups as watch
  items only; none appear as confirmed trends here.
- **2 of the 52 facts are search-page noise.** Q1 items 1–2
  ("Argentina", "Past Day") are DuckDuckGo page chrome kept in the
  fact list, with no URL captured. They are left in the files
  untouched so the example stays honest about collection limits.
  URL-less results are flagged (`url_missing`) and never given an
  invented link.
- **No retailer evidence.** No retailer buyer-review evidence is
  included in this example.
- **One run, one topic.** Nothing here proves the same queries will
  return the same results tomorrow, or that another topic plan will
  work as well. A new topic needs its own evidence before anyone
  calls it tested.

## What the run found (summary, not a conclusion)

Top clusters: registry waste (39 items, cross-source across Reddit,
YouTube, BabyCenter, and What to Expect) and diaper leaks/blowouts
(9 items, Reddit only). The report's draft outline was never turned
into a full write-up in this run: per the skill, an outline needs
user approval before any article is written. Do not quote cluster
sizes as prevalence — they count search results kept, not users.
