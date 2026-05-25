# Takealot

South Africa's largest online retailer and flagship brand of the Takealot Group — a Cape Town-headquartered e-commerce holding company majority-owned (~96%) by Naspers via Prosus. The Group operates Takealot.com (general merchandise marketplace), Mr D (on-demand food and grocery delivery), and TFS (Takealot Fulfilment Services). Superbalist.com was divested to a South African consortium in September 2024.

Takealot.com is a hybrid 1P + 3P marketplace. The public developer surface is the **Takealot Seller API** — a Swagger 2.0 REST API at `seller-api.takealot.com` used by Marketplace sellers (and the integration ecosystem around them: Stock2Shop, Wherehouse, Flowgear, OrderEazi) to manage offers, stock health, and sales reporting.

## APIs

### Takealot Seller API

- Documentation: <https://seller-api.takealot.com/api-docs/>
- OpenAPI / Swagger 2.0: [openapi/takealot-seller-openapi.yml](openapi/takealot-seller-openapi.yml) ([source](https://seller-api.takealot.com/api-docs/swagger.json))
- Base URL: `https://seller-api.takealot.com`
- Seller Portal (API key management): <https://seller.takealot.com/api/seller-api>
- Authentication: per-seller API key in `Authorization` header
- Rate limits: surfaced via `x-RateLimit-Limit` / `x-RateLimit-Remaining` / `x-RateLimit-Reset` headers
- Surface area (12 paths): Offers (get / count / get-by-identifier / update / create-from-barcode / batch up to 10,000 items / batch status), Stock health (`stock_counts`, `stock_health_stats`), Sales (`sales`, `sales/summary`, `sales/orders`, `sales/orders/{order_id}/customer_invoices`)
- Content types: `application/json`, `text/csv`, `application/pdf`, `text/html`

## Group

- Takealot Group: <https://takealotgroup.com>
- Takealot.com: <https://www.takealot.com>
- Mr D: <https://mrd.co.za>
- Mr D Food: <https://mrdfood.com>
- Superbalist (divested 2024): <https://superbalist.com>
- Parent: Naspers (<https://www.naspers.com>) via Prosus (<https://www.prosus.com>)

## Notes

- No public buyer-side / catalog API. No OAuth flow, no webhooks, no SDKs, no CLI, no developer forum.
- GitHub org (`TAKEALOT`) is a small set of archived infrastructure forks (Diamond, statsite, kafka-connect-bigquery, protoc-gen-bq-schema, Newtonsoft.Json, Lithium) — not a maintained developer platform.
- The Seller API is the single canonical API artifact to profile for Takealot.
