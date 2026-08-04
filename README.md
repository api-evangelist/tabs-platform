# Tabs (tabs-platform)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
