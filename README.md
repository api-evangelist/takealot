# Takealot (takealot)

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

Takealot is South Africa's largest online retailer and the flagship brand of the Takealot Group, a Cape Town-headquartered e-commerce holding company that is majority-owned (approximately 96%) by Naspers through its consumer-internet arm Prosus. The Group operates a connected ecosystem of consumer brands — Takealot.com (general merchandise marketplace), Mr D (on-demand food and grocery delivery), Superbalist.com (fashion and homeware, divested in September 2024 to a South African consortium led by Blank Canvas Capital but historically associated with the Group), and TFS (Takealot Fulfilment Services, the Group's first- and last-mile logistics arm) — and employs more than 7,300 people across South Africa. Takealot.com itself is a 1P-plus-3P hybrid marketplace where Takealot Retail sells its own inventory alongside thousands of third-party Marketplace sellers; sellers list, price, fulfil, and analyse their offers through the Seller Portal at seller.takealot.com and programmatically via the public Takealot Seller API. The Seller API is the company's primary external developer surface — a Swagger 2.0 / OpenAPI REST API at seller-api.takealot.com that exposes offer management (single and 10,000-item batch create / update / patch), stock-health and storage-fee diagnostics, and sales / order / customer-invoice reporting, authenticated with per-seller API keys minted from the Seller Portal and governed by per-key rate-limit headers (x-RateLimit-Limit / Remaining / Reset). There is no public buyer-side / catalog / consumer-facing API, no published OAuth flow, no webhook surface, no SDKs, no CLI, and no developer Slack / forum; the Group's GitHub presence (TAKEALOT org) is a small set of archived infrastructure forks (Diamond, statsite, kafka-connect-bigquery, protoc-gen-bq-schema, Newtonsoft.Json, Lithium) rather than a maintained developer platform. The Seller API is the integration point that powers South Africa's marketplace-listing tool ecosystem (Stock2Shop, Wherehouse, Flowgear, OrderEazi, and similar) and is the canonical artifact to profile for any Takealot capability work.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/takealot/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/takealot/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Provider
- **Access:** 3rd-Party

## Tags

- Commerce
- E-Commerce
- Marketplace
- Retail
- Marketplace Sellers
- Offers
- Orders
- Sales
- Stock Management
- Fulfilment
- Logistics
- Food Delivery
- South Africa
- Africa
- Naspers
- Prosus

## Timestamps

- **Created:** 2026-05-24
- **Modified:** 2026-05-24

## APIs

### Takealot Seller API

The Takealot Seller API is the public REST API that Takealot Marketplace sellers use to manage their offers, monitor stock health, and pull sales and order data on Takealot.com. It exposes offer CRUD by SKU / barcode / offer-id (single and batch of up to 10,000 items), batch-status polling, stock-count and stock-health-stats diagnostics tied to Takealot's storage-fee policy, and sales / sales-summary / sales-orders / customer-invoices reporting. Authentication is by per-seller API key (Authorization header) minted from the Seller Portal at https://seller.takealot.com/api/seller-api; the API is described as a Swagger 2.0 specification at https://seller-api.takealot.com/api-docs/ with the canonical document at https://seller-api.takealot.com/api-docs/swagger.json. Responses are returned as application/json, text/csv, application/pdf, or text/html depending on the operation, and every response carries the standard x-RateLimit-Limit / x-RateLimit-Remaining / x-RateLimit-Reset headers.

- **Human URL:** [https://seller-api.takealot.com/api-docs/](https://seller-api.takealot.com/api-docs/)
- **Base URL:** `https://seller-api.takealot.com`

#### Tags

- Marketplace
- Sellers
- Offers
- Stock
- Sales
- Orders
- Invoices

#### Properties

- [Documentation](https://seller-api.takealot.com/api-docs/)
- [OpenAPI](openapi/takealot-seller-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/takealot-seller.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/takealot-seller.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Swagger](https://seller-api.takealot.com/api-docs/swagger.json)
- [Seller Portal](https://sellers.takealot.com/)
- [A P I Key Management](https://seller.takealot.com/api/seller-api)
- [Authentication](https://seller-api.takealot.com/api-docs/)
- [Rate Limits](https://seller-api.takealot.com/api-docs/)

## Common Properties

- [Website](https://www.takealot.com)
- [Group Website](https://takealotgroup.com)
- [Seller Portal](https://sellers.takealot.com)
- [Seller A P I Documentation](https://seller-api.takealot.com/api-docs/)
- [Mr D](https://mrd.co.za)
- [Mr D Food](https://mrdfood.com)
- [Superbalist](https://superbalist.com)
- [Takealot Fulfilment Services](https://takealotgroup.com)
- [Help Centre](https://www.takealot.com/help-centre)
- [Careers](https://www.takealotgroup.com/careers)
- [Newsroom](https://takealotgroup.com/newsroom)
- [Contact](mailto:contactus@takealot.group)
- [Privacy Policy](https://www.takealot.com/help-centre/legal/privacy-policy)
- [Terms And Conditions](https://www.takealot.com/help-centre/legal/website-terms)
- [Git Hub](https://github.com/TAKEALOT)
- [Parent Company](https://www.naspers.com)
- [Prosus Group](https://www.prosus.com)
- [LinkedIn](https://www.linkedin.com/company/takealot-com)
- [Twitter](https://twitter.com/TAKEALOT)
- [Facebook](https://www.facebook.com/TAKEALOT)
- [Instagram](https://www.instagram.com/takealot)
- [YouTube](https://www.youtube.com/user/TAKEALOTdotcom)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
