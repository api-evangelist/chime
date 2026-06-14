# Chime Financial GraphQL Schema

## Overview

Chime is a neobank and fintech platform offering fee-free checking and savings accounts, early direct deposit access, credit building, and peer-to-peer payment features for consumer banking. The Chime Partner API is limited to authorized partners and accessed via OAuth 2.0. This GraphQL schema is a conceptual representation of the data types, relationships, and operations that reflect Chime's known product surface area, derived from public documentation, product disclosures, and API partner reference materials.

## Schema Source

This schema is conceptual. Chime does not publish a public GraphQL API. The types and operations below are modeled from:

- Chime Partner API documentation at https://developer.chime.com/docs/chime-apis
- Chime product feature descriptions (SpotMe, Credit Builder, AutoSave, Pay Anyone)
- Public developer and partner onboarding materials

## Types Summary

The schema covers 60+ named GraphQL types organized into the following domains:

### Account Domain
- `Account` — root user financial account
- `SpendingAccount` — fee-free checking account
- `SavingsAccount` — high-yield savings account
- `CreditBuilderAccount` — secured credit account for building credit
- `AccountDetails` — extended account metadata
- `AccountBalance` — composite balance object
- `AvailableBalance` — real-time spendable balance
- `PendingBalance` — balance held for pending transactions
- `InternationalDeposit` — inbound international deposit record
- `DirectDeposit` — direct deposit enrollment and history

### Card Domain
- `DebitCard` — physical debit card details
- `CardDetails` — card metadata (PAN, expiry, CVV reference)
- `CardStatus` — card lifecycle state
- `CardFreeze` — temporary card freeze record
- `CardBlock` — permanent card block record
- `VirtualCard` — virtual card provisioning
- `DisableCard` — card disable action

### Transaction Domain
- `CardTransaction` — debit card transaction record
- `SpenderTransaction` — enriched spending transaction
- `CashBack` — cash-back reward on eligible purchases

### Transfer Domain
- `Transfer` — base transfer type
- `InternalTransfer` — between Chime accounts (spending ↔ savings)
- `FriendTransfer` — Pay Anyone / Pay Friend transfer
- `BankTransfer` — external bank transfer
- `ACHTransfer` — ACH pull or push transfer
- `InstantTransfer` — faster/instant payment transfer
- `PayFriend` — peer-to-peer payment to another Chime member

### Savings Domain
- `Savings` — savings summary
- `SavingsGoal` — named savings target
- `SavingsRule` — rule governing auto-save behavior
- `Rounding` — round-up rule for spare change savings
- `AutoSave` — automatic savings configuration
- `AutoSaveSetting` — specific auto-save parameters

### Credit Builder Domain
- `CreditBuilder` — credit builder account wrapper
- `CreditBuilderDetails` — detailed credit builder state
- `CreditLimit` — current credit limit
- `SecurityDeposit` — secured deposit backing credit limit

### Bill Pay Domain
- `BillPayment` — bill payment record
- `BillPayee` — registered payee
- `ScheduledPayment` — future-dated payment

### Alerts and Notifications Domain
- `Notification` — push or in-app notification
- `Alert` — user-configured alert
- `BalanceAlert` — threshold-based balance alert
- `TransactionAlert` — transaction-triggered alert

### ATM and Network Domain
- `ATMLocator` — ATM search result container
- `ATMDetails` — individual ATM location details
- `CheckNetwork` — check deposit network record

### Overdraft and Fee Policy Domain
- `SpotMe` — SpotMe overdraft protection details
- `OverdraftProtection` — overdraft protection settings
- `FeePolicy` — fee schedule (mostly $0 for Chime)
- `InternationalPayment` — cross-border payment record

### Auth Domain
- `APIKey` — partner API key record
- `Token` — OAuth 2.0 token metadata

## Query Operations

- `account(userId: ID!)` — fetch root account for a user
- `spendingAccount(userId: ID!)` — fetch spending account details
- `savingsAccount(userId: ID!)` — fetch savings account
- `creditBuilderAccount(userId: ID!)` — fetch credit builder account
- `accountBalance(accountId: ID!)` — fetch composite balance
- `transactions(accountId: ID!, limit: Int, offset: Int)` — list transactions
- `transfer(transferId: ID!)` — fetch a specific transfer
- `transfers(accountId: ID!)` — list transfers
- `savingsGoals(userId: ID!)` — list savings goals
- `autoSaveSettings(userId: ID!)` — fetch auto-save configuration
- `creditBuilder(userId: ID!)` — fetch credit builder details
- `billPayees(userId: ID!)` — list registered payees
- `scheduledPayments(userId: ID!)` — list scheduled payments
- `notifications(userId: ID!)` — list notifications
- `alerts(userId: ID!)` — list user alerts
- `atmLocator(lat: Float!, lng: Float!, radius: Int)` — find nearby ATMs
- `spotMe(userId: ID!)` — fetch SpotMe eligibility and limit
- `debitCard(userId: ID!)` — fetch debit card details
- `virtualCard(userId: ID!)` — fetch virtual card

## Mutation Operations

- `freezeCard(cardId: ID!)` — temporarily freeze a card
- `unfreezeCard(cardId: ID!)` — unfreeze a card
- `blockCard(cardId: ID!)` — permanently block a card
- `initiateTransfer(input: TransferInput!)` — initiate a transfer
- `payFriend(input: PayFriendInput!)` — send money to another Chime user
- `createSavingsGoal(input: SavingsGoalInput!)` — create a savings goal
- `updateAutoSave(input: AutoSaveInput!)` — update auto-save rules
- `scheduleBillPayment(input: BillPaymentInput!)` — schedule a bill payment
- `setBalanceAlert(input: BalanceAlertInput!)` — configure a balance alert
- `enrollDirectDeposit(userId: ID!)` — initiate direct deposit enrollment

## Authentication

All operations require OAuth 2.0 Bearer token authentication. The Partner API uses Authorization Code Flow with PKCE. Scopes control access to account, transaction, card, and payment resources.

## References

- Chime Developer Portal: https://developer.chime.com/
- Chime Partner API Docs: https://developer.chime.com/docs/chime-apis
- Chime Product Overview: https://www.chime.com/
