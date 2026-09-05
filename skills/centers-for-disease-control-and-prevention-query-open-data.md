---
name: Query a CDC open dataset
description: Find a CDC dataset in the DCAT-US catalog and pull rows from it with SoQL, paging correctly and handling the Socrata error envelope.
api: openapi/centers-for-disease-control-and-prevention-soda-v2-1-api-openapi.yml
operations: [queryDatasetJson, queryDatasetCsv, queryDatasetGeoJson]
generated: '2026-09-05'
method: generated
---

# Query a CDC open dataset

CDC publishes 1,385 datasets through Socrata SODA at `data.cdc.gov` (and the chronic-disease /
PLACES portal at `chronicdata.cdc.gov`). No key is required. All of this is verified against the
harvested catalog and live probes on 2026-09-05.

## 1. Find the dataset

`GET https://data.cdc.gov/data.json` returns the full DCAT-US 1.1 catalog (1,385 entries, ~4 MB).
Each entry's `identifier` is `https://data.cdc.gov/api/views/{four-by-four}` — the eight-character
`abcd-efgh` id at the end is the `dataset_id` every query below needs. A verbatim copy is in this
repository at `well-known/centers-for-disease-control-and-prevention-data-json-catalog.json`.

Do not scrape `https://data.cdc.gov/browse` for this — `robots.txt` disallows the filtered browse
query strings and sets `Crawl-delay: 1`.

## 2. Query it

Use `queryDatasetJson` — `GET /resource/{dataset_id}.json`. `queryDatasetCsv` and
`queryDatasetGeoJson` are the same operation with a different representation; use `.geojson` only
for datasets that actually carry geometry.

SoQL parameters: `$select`, `$where`, `$order`, `$group`, `$having`, `$limit`, `$offset`, `$q`.

```
GET https://data.cdc.gov/resource/9mfq-cb36.json?$select=state,tot_cases&$where=submission_date>'2023-01-01'&$order=submission_date&$limit=1000
```

## 3. Page correctly

`$limit` defaults to **1,000**. SODA 2.0 caps it at 50,000; 2.1 and 3.0 have no cap. Always send
`$order` when paging — without it, row order across `$offset` windows is not guaranteed and you
will silently duplicate and skip rows.

## 4. Authenticate only to lift throttling

Anonymous requests are throttled per IP and return **429** when they trip. Send a free Socrata
application token as the `X-App-Token` header (or `$$app_token` query parameter) and Socrata
states it does not throttle at all unless traffic is abusive. There are no rate-limit response
headers on this API — you cannot see your remaining budget, so back off on 429 rather than
predicting it.

## 5. Handle errors

The envelope is Socrata-native, not RFC 9457:

```json
{"code":"dataset.missing","error":true,"message":"Not found","data":{"id":"zzzz-zzzz"}}
```

A bad four-by-four returns HTTP 404 with `code: dataset.missing`. Keep `X-Socrata-RequestId` from
the response headers — it is the only correlation id CDC returns anywhere.

## 6. Attribution

Most CDC datasets are CC0 1.0 public domain. Check each catalog entry's `license` before assuming.
