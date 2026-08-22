# Centers for Disease Control and Prevention (centers-for-disease-control-and-prevention)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

The Centers for Disease Control and Prevention (CDC) is the United States' national public health agency, part of the Department of Health and Human Services. CDC operates a broad portfolio of public APIs and open data services including the Socrata-powered data.cdc.gov (Open Data API for hundreds of COVID-19, chronic disease, environmental health, immunization, injury, and mortality datasets), the WONDER online query databases for mortality, natality, and cancer statistics, the PLACES / BRFSS and Environmental Public Health Tracking Network APIs, the Content Syndication platform, and the open.cdc.gov developer portal that indexes these resources for civic technologists and public-health researchers.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/centers-for-disease-control-and-prevention/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/centers-for-disease-control-and-prevention/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- CDC
- Environmental Health
- Epidemiology
- Federal Government
- Healthcare
- Open Data
- Public Health
- Socrata
- Surveillance
- WONDER

## Timestamps

- **Created:** 2024-12-03
- **Modified:** 2026-04-23

## APIs

### CDC Socrata Open Data API (data.cdc.gov)

The CDC Socrata Open Data API (SODA) provides programmatic JSON, CSV, and GeoJSON access to hundreds of data.cdc.gov datasets covering COVID-19 case surveillance, vaccination coverage, excess deaths, flu surveillance, PRAMStat, PLACES small-area estimates, environmental public health tracking, and chronic disease indicators. Supports SoQL filtering, aggregation, pagination, and authenticated app tokens for higher rate limits.

- **Human URL:** [https://data.cdc.gov/](https://data.cdc.gov/)
- **Base URL:** `https://data.cdc.gov/resource/`

#### Tags

- Chronic Disease
- COVID-19
- Datasets
- Open Data
- SODA
- Socrata
- Surveillance

#### Properties

- [Website](https://data.cdc.gov/)
- [Documentation](https://dev.socrata.com/)
- [Reference](https://dev.socrata.com/docs/endpoints.html)
- [Getting Started](https://dev.socrata.com/consumers/getting-started.html)
- [Sign Up](https://evergreen.data.socrata.com/signup)
- [Postman Collection](collections/centers-for-disease-control-and-prevention.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/centers-for-disease-control-and-prevention.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CDC WONDER API

CDC WONDER (Wide-ranging ONline Data for Epidemiologic Research) is a suite of public-use ad-hoc query databases covering underlying and multiple cause of death, natality, cancer statistics, tuberculosis, STDs, vaccine adverse events, and environmental health indicators. WONDER exposes an XML-based HTTP API that accepts parameter documents and returns aggregate statistics suitable for epidemiologic research.

- **Human URL:** [https://wonder.cdc.gov/](https://wonder.cdc.gov/)
- **Base URL:** `https://wonder.cdc.gov/controller/datarequest/`

#### Tags

- Cancer
- Mortality
- Natality
- Query Database
- Statistics

#### Properties

- [Website](https://wonder.cdc.gov/)
- [Documentation](https://wonder.cdc.gov/wonder/help/WONDER-API.html)
- [F A Q](https://wonder.cdc.gov/wonder/help/faq.html)
- [Postman Collection](collections/centers-for-disease-control-and-prevention.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/centers-for-disease-control-and-prevention.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CDC PLACES / 500 Cities API

PLACES (Population Level Analysis and Community Estimates) provides model-based small-area estimates for chronic disease risk factors, health outcomes, and prevention practices for counties, ZCTAs, census tracts, and places across the United States. Data is available via the Socrata chronicdata.cdc.gov portal as JSON, CSV, and GeoJSON endpoints.

- **Human URL:** [https://www.cdc.gov/places/](https://www.cdc.gov/places/)
- **Base URL:** `https://chronicdata.cdc.gov/resource/`

#### Tags

- BRFSS
- Census Tract
- Chronic Disease
- Health Indicators
- Small Area Estimation

#### Properties

- [Website](https://www.cdc.gov/places/)
- [Methodology](https://www.cdc.gov/places/methodology/)
- [Open Data](https://chronicdata.cdc.gov/)
- [Postman Collection](collections/centers-for-disease-control-and-prevention.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/centers-for-disease-control-and-prevention.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CDC Environmental Public Health Tracking Network API

The Environmental Public Health Tracking Network API provides a REST interface over the National Tracking Network's JSON-formatted data for air quality, water quality, climate and health, childhood lead poisoning, asthma, cancer, and other environmental health indicators at national, state, and county levels.

- **Human URL:** [https://ephtracking.cdc.gov/apihelp](https://ephtracking.cdc.gov/apihelp)
- **Base URL:** `https://ephtracking.cdc.gov:443/apigateway/api/v1`

#### Tags

- Air Quality
- Environmental Health
- Exposure
- GIS
- Water Quality

#### Properties

- [Website](https://ephtracking.cdc.gov/)
- [Documentation](https://ephtracking.cdc.gov/apihelp)
- [Explorer](https://ephtracking.cdc.gov/DataExplorer/)
- [Postman Collection](collections/centers-for-disease-control-and-prevention.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/centers-for-disease-control-and-prevention.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CDC Public Health Media Library (Content Syndication)

The CDC Public Health Media Library Content Syndication API lets developers and partner sites programmatically retrieve CDC health content (articles, infographics, videos, widgets, images, and microsites) in multiple formats to embed on third-party properties with automatic update propagation.

- **Human URL:** [https://tools.cdc.gov/medialibrary/](https://tools.cdc.gov/medialibrary/)

#### Tags

- Content Syndication
- Health Content
- Media
- Multimedia

#### Properties

- [Website](https://tools.cdc.gov/medialibrary/)
- [Reference](https://tools.cdc.gov/api/v2/resources/media)
- [Documentation](https://tools.cdc.gov/api/docs/info.aspx)
- [Postman Collection](collections/centers-for-disease-control-and-prevention.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/centers-for-disease-control-and-prevention.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CDC Open Technology API Index

open.cdc.gov is CDC's Open Technology landing site that indexes the agency's public APIs, open-source GitHub repositories, and open data assets, serving as a catalog entry point for developers seeking CDC interfaces across programs and centers.

- **Human URL:** [https://open.cdc.gov/apis.html](https://open.cdc.gov/apis.html)

#### Tags

- Developer Portal
- Directory
- Open Technology

#### Properties

- [Website](https://open.cdc.gov/apis.html)
- [Portal](https://open.cdc.gov/)
- [GitHub Organization](https://github.com/CDCgov)
- [Postman Collection](collections/centers-for-disease-control-and-prevention.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/centers-for-disease-control-and-prevention.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CDC NNDSS / MMWR Socrata Data

The National Notifiable Diseases Surveillance System (NNDSS) and Morbidity and Mortality Weekly Report (MMWR) tables are published as Socrata datasets on data.cdc.gov, providing weekly and historical case counts for notifiable conditions accessible via SoQL and bulk download.

- **Human URL:** [https://data.cdc.gov/browse?category=NNDSS](https://data.cdc.gov/browse?category=NNDSS)

#### Tags

- MMWR
- NNDSS
- Notifiable Disease
- Surveillance

#### Properties

- [Catalog](https://data.cdc.gov/browse?category=NNDSS)
- [Program](https://www.cdc.gov/nndss/)
- [Tables](https://wonder.cdc.gov/nndss/nndss_table_menus.asp)
- [Postman Collection](collections/centers-for-disease-control-and-prevention.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/centers-for-disease-control-and-prevention.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/centers-for-disease-control-and-prevention)
- [Website](https://www.cdc.gov/)
- [Open Data](https://data.cdc.gov/)
- [Portal](https://open.cdc.gov/)
- [A P Is](https://open.cdc.gov/apis.html)
- [GitHub Organization](https://github.com/CDCgov)
- [W O N D E R](https://wonder.cdc.gov/)
- [Socrata](https://dev.socrata.com/)
- [Content Syndication](https://tools.cdc.gov/medialibrary/)
- [E P H T N](https://ephtracking.cdc.gov/)
- [Privacy Policy](https://www.cdc.gov/other/privacy.html)
- [Integrations](https://www.cdc.gov/partners/about/index.html)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
