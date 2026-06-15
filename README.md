# Takealot (takealot)

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
