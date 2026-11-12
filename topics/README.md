# Topic plans

A topic plan is a JSON file that records, for one research topic,
what to search for and how to group what is found. It is a plan for
following the skill by hand: the queries to run, the cluster
keywords to group by, and the follow-up searches to record. The
skill itself contains no topic-specific queries or keywords:
everything topic-specific lives here.

## Included example

`baby-products.json` is the only topic plan shipped with this repo.
It holds the queries and cluster keywords used in the worked example
(see `examples/baby-products/`).

## Writing a new topic plan

Copy `baby-products.json` to a new file, for example
`topics/my-topic.json`, and edit these fields:

| Field | Required | Meaning |
|---|---|---|
| `slug` | yes | Short id for the topic, e.g. `my-topic`. Letters, digits, `_` and `-` only. |
| `title` | no | Short title for the topic, e.g. `My topic pain points`. Defaults to the slug. |
| `topic` | no | One-line description of the research question. |
| `description` | no | Free-text note for humans. |
| `queries` | yes | Non-empty list of DuckDuckGo search strings. Prefer `site:` queries so each result set stays on one platform (the platform label is derived from the `site:` host). Keep the list short: the worked example used 5 queries and kept 52 facts. Do not add retailer queries (for example `site:amazon.com`) unless you have first proven, in a manual run, that the query returns usable buyer-review evidence. |
| `max_facts` | no | Cap on facts kept. Default 60 in the example. |
| `max_per_query` | no | Cap on results kept per query. Default 12 in the example. |
| `max_numbers` | no | Cap on quarantined numbers. Default 30 in the example. |
| `clusters` | no | List of keyword clusters. Each cluster needs `id` (short, stable), `keywords` (list of lowercase phrases matched against title + snippet), and may carry `label` (human-readable heading) and `follow_up` (one proposed follow-up search, recorded only, never run automatically). Results matching no cluster land in `ungrouped`. A cluster needs at least 2 items to count as confirmed; 1-item groups are watch items only. |
| `counter_keywords` | no | Phrases that mark counter evidence (users saying the opposite), e.g. `fixed`, `worked for`. |
| `safety_note` | no | Wording for the report. For any health-related topic, keep general-information-only wording and never present output as medical advice. |
| `extra_gaps` | no | Extra evidence-gap lines for the report, e.g. sources deliberately excluded. |

## Rules the plan must respect

- No Reddit API, and no login needed. Queries are public web
  searches only, and no account is needed to get the information.
- Follow-up searches in `follow_up` fields are proposals for a later
  run. They are recorded only and never run automatically.
- Follow-ups pointing at `amazon.com` are left out. See the README
  for why retailer queries stay out by default.
- Keep cluster keywords specific to the topic. Overly broad keywords
  (for example a single common word) will swallow unrelated results
  into one cluster; the example run's largest cluster had 39 of 52
  facts partly because `registry` and `regret` matched widely.

## Checking a new plan

Check the file is valid JSON before using it, and that the slug is
well formed, `queries` is non-empty, and every cluster has its `id`
and `keywords` list. A new topic plan has not been worked through
until it has its own evidence. Do not present unworked plans as
tested.
