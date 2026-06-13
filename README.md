# Chime

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
