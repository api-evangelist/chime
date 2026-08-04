# Chime

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

Chime is a neobank and fintech platform offering fee-free checking and savings accounts, early paycheck access, credit building, and peer-to-peer payment features for consumer banking. Based in San Francisco, California, Chime serves millions of members through mobile-first banking services provided in partnership with The Bancorp Bank, N.A. and Stride Bank, N.A.

## Products

- **Checking Account** - Fee-free checking with no minimum balance and access to 47,000+ fee-free ATMs
- **Savings Account** - High-yield savings with up to 3.75% APY (Chime Prime members)
- **SpotMe** - Fee-free overdraft protection up to $200
- **MyPay** - Early wage access of up to $500 of pay on demand
- **Early Paycheck Access** - Receive paychecks up to two days early with direct deposit
- **Credit Builder** - Credit-building card with no credit check, no interest, no annual fee
- **Pay Anyone** - Peer-to-peer payment transfers between Chime members

## Developer API

Chime offers a Partner API for fintech developers and businesses. The API provides programmatic access to:

- User account information
- Transaction history (across all accounts or per account)
- Account balances and statements
- Payment initiation
- OAuth 2.0 authorization flows

**Developer Portal:** https://developer.chime.com/

### Authentication

The Chime Partner API supports two authentication methods:

- **OAuth 2.0** (recommended for new integrations) - Supports Authorization Code Flow and PKCE
- **Legacy Partner Auth** - Available for existing integrations only

### Key Endpoints

| Endpoint | Description |
|----------|-------------|
| `GET /users/:id` | User account information |
| `GET /users/:id/transactions` | All transactions for a user (max 2000 per account per request) |
| `GET /users/:id/accounts/:account_id/transactions` | Transactions for a specific account |
| `GET /users/:id/accounts/:account_id/statement` | Account statement |
| `POST /users/auth_token` | Legacy authentication |
| `POST /oauth/authorize` | OAuth 2.0 authorization |
| `POST /oauth/tokens` | OAuth 2.0 token exchange and refresh |

### Base URL

`https://api.chimebank.com/chime/v1`

## Links

- **Website:** https://www.chime.com/
- **Developer Portal:** https://developer.chime.com/
- **API Documentation:** https://developer.chime.com/docs/chime-apis
- **Status Page:** https://status.chime.com/
- **Blog (Life at Chime):** https://medium.com/life-at-chime
- **GitHub:** https://github.com/chimehq
- **LinkedIn:** https://www.linkedin.com/company/chime-card

## APIs.json

This repository contains an APIs.json 0.19 profile for Chime, maintained by [Kin Lane](mailto:kin@apievangelist.com) as part of the [API Evangelist](https://apievangelist.com) catalog.
