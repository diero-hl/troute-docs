# Security

## Contract Design

The TROUTE presale contract was designed with a minimal attack surface. It does one thing: accept USDC.e and send $TROUTE tokens to the buyer in the same transaction.

Key design decisions:

- No funds are held in the presale contract. All USDC.e paid by buyers is routed directly to the treasury wallet at the time of purchase.
- The presale contract does not hold admin keys over the TROUTE token after deployment.
- Token transfers are executed atomically. If the transfer fails for any reason, the entire transaction reverts. Buyers cannot lose funds to a partial execution.

## Contract Addresses

| Contract | Address |
|---|---|
| TROUTE Token | `0x72566b53a5ba0bef9de683e5074860e22705f8ea` |
| Presale Contract | `0x6301ebf664223c2108a883fd575b32c071e4b120` |

## Audit

Audit details will be published here when complete. Follow [@TROUTEprotocol](https://twitter.com/TROUTEprotocol) for the announcement.

## How to Verify the Contract Yourself

You do not need to trust us. You can verify the contract behavior directly on-chain.

1. Connect to Tempo Chain RPC: `https://rpc.tempo.xyz`
2. Read the `treasury` variable on the presale contract to confirm where funds go
3. Read the `paymentToken` variable to confirm only USDC.e is accepted
4. Read the `active` variable to confirm presale status
5. Read the `tokenPrice` variable to confirm the price is $0.0001

Everything the contract does is visible on-chain before you send a single dollar.

## Risk Disclosure

Participating in a token presale carries risk. Smart contracts can have bugs even after audits. The value of $TROUTE after TGE is not guaranteed. Only participate with funds you can afford to lose.
