# Look up requests

Chris's Paper has a Look up tab. When Chris types a topic, the app writes `requests/<id>.json`:

```json
{ "id": "20261110-071500-ab12", "query": "Why is the Murray mouth closing?", "askedAt": "2026-11-10T07:15:00Z", "status": "open" }
```

## How to answer (every edition run, before writing the edition)
1. List `requests/`. A request is open when `answers/<same id>.json` doesn't exist yet.
2. For each open request, research the topic on the web (prefer free, reputable sources; never paywalled journal links, see README) and write `answers/<id>.json`:

```json
{
  "id": "20261110-071500-ab12",
  "query": "Why is the Murray mouth closing?",
  "answeredAt": "2026-11-10T19:00:00Z",
  "headline": "One-line news-style headline",
  "body": "120 to 180 words: what is happening, why, and what comes next. Plain Australian English, no em dashes, Oxford comma, balanced on contested politics.",
  "why": "One or two sentences on why it matters to Chris (optional).",
  "points": ["3 to 5 key points", "each one short"],
  "sources": [{ "name": "ABC News", "url": "https://..." }],
  "image": "https://... (optional, a real image from one of the sources)",
  "kind": "Briefing"
}
```
3. Leave the request file in place (the app matches answers by id). The app picks up the answer next time Chris opens the Look up tab.

`headline`, `body`, and `id` are required; everything else is optional.
