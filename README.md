# chris-paper-feed
Edition feed for the Chris's Paper app

## Notes for the editions task (read before writing an edition)

These are additions to the edition format and rules, added 10 Nov 2026. Everything here is optional and backward compatible: older app builds ignore unknown fields.

### Paywalled journals: NEJM, Lancet, JAMA
Never link a story to nejm.org, thelancet.com, or jamanetwork.com (or their sub-journals). Chris can't get past the paywall. Link a free source covering the same paper instead, in this order:
1. The PubMed record: https://pubmed.ncbi.nlm.nih.gov/<PMID>/ (find the PMID by searching PubMed for the DOI).
2. The journal's or institution's press release.
3. A free news report on the paper (ABC, The Conversation, Guardian, STAT, MedicalXpress, and so on).

Set `source` to name both, for example `"NEJM (free abstract on PubMed)"`. Never use paywall-bypass tools or archive mirrors. The app also rewrites any NEJM, Lancet, or JAMA link that has a DOI to its PubMed record as a safety net.

### Local events (optional `events` array)
A small, low-prominence "What's on locally" list for Dubbo and the Central West. Not a main focus: 3 to 6 items, the next 7 days, worth leaving the house for (markets, live music, sport, community, talks, the Western Plains Cultural Centre, Dubbo Regional Theatre, Taronga Western Plains Zoo events). Leave the array out when there's nothing good; the app hides the section when it's absent or empty.

```json
"events": [
  {
    "title": "Dubbo Farmers Market",
    "date": "2026-11-14",
    "endDate": null,
    "time": "8am to 12pm",
    "venue": "Dubbo Showground",
    "detail": "Local produce, coffee, and food stalls.",
    "url": "https://example.org/event",
    "free": true
  }
]
```
`title` and `date` (yyyy-MM-dd) are required. Everything else is optional. Past events are hidden by the app.

### Look up requests (see ASK.md)
The app writes `requests/<id>.json` when Chris asks for a briefing on a topic. Each edition run, answer every open request into `answers/<id>.json` as described in ASK.md.
