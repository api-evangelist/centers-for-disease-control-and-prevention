---
name: Retrieve and embed CDC syndicated content
description: Search the CDC Public Health Media Library and pull embeddable markup, reading the in-body status rather than the HTTP code.
api: https://tools.cdc.gov/api/docs/info.aspx
operations: [listMedia, getMedia, getMediaEmbed, getMediaSyndicate, listTopics, listTags]
generated: '2026-09-05'
method: generated
---

# Retrieve and embed CDC syndicated content

CDC's Content Syndication API at `https://tools.cdc.gov/api/v2/resources/` serves 6,734 media
resources — articles, infographics, videos, widgets, microsites — with no authentication.
Verified live 2026-09-05.

## 1. Search

```
GET https://tools.cdc.gov/api/v2/resources/media?q=influenza&mediaTypes=html&max=25&sort=-datePublished
```

Filters: `q`, `mediaTypes`, `name`, `nameContains`, `topic`, `topicIds`, `audience`,
`languageIsoCode`, `sourceAcronym`, and geo filters (`geoName`, `countryCode`, `latitude`,
`longitude`). Trim the payload with `fields` — it supports nesting, e.g. `fields=name,tags{name,type}`.

Vocabulary endpoints: `/v2/resources/topics`, `/tags`, `/audiences`, `/mediatypes`, `/languages`,
`/organizations`, `/sources`.

## 2. Page

`max` (default **100**), `pagenum`, `offset`, `sort` (prefix `-` for descending), `order`.
Read `meta.pagination.total` and `meta.pagination.totalPages`.

## 3. READ meta.status, NOT the HTTP code

This is the trap on this API. A bad request comes back as **HTTP 200** with the error inside the
envelope:

```json
{"meta":{"status":400,"message":[{"type":"Error","code":"ID","userMessage":"Id could not be parsed as a number"}]},"results":[]}
```

A status-code-only check will treat that as success. Branch on `meta.status` and surface
`meta.message[].userMessage`.

## 4. Embed

- `/v2/resources/media/{id}/embed` — embeddable markup.
- `/v2/resources/media/{id}/syndicate` — full syndication payload with `stripScripts`,
  `stripAnchors`, `stripImages`, `stripStyles`, `cssClasses`, `xpath`, `of=xhtml|xml`, `ns`.
- `/v2/resources/media/{id}/content` — raw content.

Syndicated content updates at the source, so re-fetch rather than caching indefinitely.

## 5. Formats

`.json` (default), `.xml`, `.jsonp`, or `?format=xml`. Dates are ISO 8601 `yyyy-MM-ddTHH:mm:ssZ`.
No rate limit is documented and no rate-limit header is returned.
