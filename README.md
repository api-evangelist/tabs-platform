# Tabs (tabs-platform)

Tabs (tabs.inc) is an AI-native revenue automation platform for B2B companies that unifies billing, collections, ASC 606 revenue recognition, and reporting on top of a contract-driven data model. Tabs ingests executed contracts, uses AI to extract commercial terms, automatically generates invoices, schedules ASC 606-compliant revenue, drives collections, and produces real-time ARR, cash, and AR reporting. The public Tabs Platform REST API (`https://api.tabsplatform.com`, documented at [docs.tabsplatform.com](https://docs.tabsplatform.com)) exposes the core data model - customers, contracts, items, revenue categories, obligations, invoices, payments, usage events, and performance obligations - so contract, billing, and revenue data can flow into the rest of the finance stack (ERP, CRM, payment, and tax systems). It supports subscription, usage-based, metered, and hybrid billing models.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/tabs-platform/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/tabs-platform/refs/heads/main/apis.yml)

## Access Model

- **Documentation is public.** The data model, authentication, and per-resource docs at docs.tabsplatform.com are readable without a login.
- **API calls are account-gated.** You authenticate with an API key created by an administrator in the Developers section of the Tabs app, passed directly in the `Authorization` header (`Authorization: YOUR_API_KEY` - no `Bearer` prefix). API access is included with a Tabs subscription; there is no separate metered API charge.
- **Pricing is by company size.** Starter is roughly $2,000/month for companies up to $5M annual revenue and up to ~100 active contracts; larger companies move to custom tiers quoted by sales. There is no public "percentage of billings" pricing.
- **Endpoint path shapes are modeled.** Tabs documents the base URL, API-key auth, and the resource groups and their operations, but does not publish a downloadable OpenAPI file or literal path strings. The OpenAPI in this repo models endpoint paths on standard REST conventions consistent with the documented operations (`endpointsModeled: true`). Verify concrete paths and schemas against the live console reference before building against them. See [`review.yml`](review.yml).

## Tags

- Revenue Recognition
- ASC 606
- Billing
- B2B Payments
- Accounts Receivable
- Invoicing
- Collections
- Usage-Based Billing
- Subscriptions
- Contracts
- Finance
- Revenue Automation

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Tabs Contracts API

Create, list, get, and update customer contracts, upload executed contract documents for AI ingestion, and manage the obligations and billing terms that drive invoicing and revenue recognition.

- **Human URL:** [https://docs.tabsplatform.com/docs/contracts](https://docs.tabsplatform.com/docs/contracts)
- **Base URL:** `https://api.tabsplatform.com`

#### Tags

- Contracts
- Obligations
- Billing Terms

#### Properties

- [Documentation](https://docs.tabsplatform.com/docs/contracts)
- [API Reference](https://docs.tabsplatform.com/docs/obligations)
- [OpenAPI](openapi/tabs-platform-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Tabs Invoices API

List, get, and update invoices and their line items, download invoice PDFs, and perform lifecycle actions (finalize, send, void, mark paid). Invoices are itemized requests for payment derived from contract obligations.

- **Human URL:** [https://docs.tabsplatform.com/docs/invoices](https://docs.tabsplatform.com/docs/invoices)
- **Base URL:** `https://api.tabsplatform.com`

#### Tags

- Invoicing
- Accounts Receivable
- Billing

#### Properties

- [Documentation](https://docs.tabsplatform.com/docs/invoices)
- [OpenAPI](openapi/tabs-platform-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Tabs Revenue Recognition API

List recognized revenue, search ASC 606 performance obligations, upsert a recognized-revenue schedule, and pull the ARR and cash-forecast reports. Invoices flow directly into ASC 606-compliant revenue recognition without manual spreadsheets.

- **Human URL:** [https://docs.tabsplatform.com/docs/the-tabs-data-model](https://docs.tabsplatform.com/docs/the-tabs-data-model)
- **Base URL:** `https://api.tabsplatform.com`

#### Tags

- Revenue Recognition
- ASC 606
- ARR

#### Properties

- [Documentation](https://docs.tabsplatform.com/docs/the-tabs-data-model)
- [OpenAPI](openapi/tabs-platform-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Tabs Payments API

Create, list, and get payments - the receipts (often bank-imported) that settle invoices - and apply them across a customer's open invoices.

- **Human URL:** [https://docs.tabsplatform.com/docs/payments](https://docs.tabsplatform.com/docs/payments)
- **Base URL:** `https://api.tabsplatform.com`

#### Tags

- Payments
- B2B Payments
- Collections

#### Properties

- [Documentation](https://docs.tabsplatform.com/docs/payments)
- [OpenAPI](openapi/tabs-platform-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Tabs Customers API

Create, list, get, update, and delete the businesses you bill, along with their contacts, addresses, external IDs, and custom fields, and read a customer's invoices and payments.

- **Human URL:** [https://docs.tabsplatform.com/docs/customers](https://docs.tabsplatform.com/docs/customers)
- **Base URL:** `https://api.tabsplatform.com`

#### Tags

- Customers
- Contacts
- CRM

#### Properties

- [Documentation](https://docs.tabsplatform.com/docs/customers)
- [OpenAPI](openapi/tabs-platform-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Tabs Usage Events API

Push, list, and delete usage events that track how customers consume usage-based and metered products, feeding quantity calculations for dynamic billing and forecasting.

- **Human URL:** [https://docs.tabsplatform.com/docs/usage-events-beta](https://docs.tabsplatform.com/docs/usage-events-beta)
- **Base URL:** `https://api.tabsplatform.com`

#### Tags

- Usage-Based Billing
- Metering
- Usage Events

#### Properties

- [Documentation](https://docs.tabsplatform.com/docs/usage-events-beta)
- [OpenAPI](openapi/tabs-platform-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [Authentication](authentication/tabs-platform-authentication.yml)
- [LinkedIn](https://www.linkedin.com/company/teamtabs)
- [Website](https://tabs.inc)
- [Documentation](https://docs.tabsplatform.com)
- [Plans](plans/tabs-platform-plans-pricing.yml)
- [Rate Limits](rate-limits/tabs-platform-rate-limits.yml)
- [Fin Ops](finops/tabs-platform-finops.yml)
- [Blog](https://www.tabs.com/blog)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
