# Smart Contracts

All TROUTE protocol contracts are deployed on Tempo Chain mainnet (Chain ID: 4217).

## Contract Addresses

| Contract | Address |
|---|---|
| TROUTE Token | `0x72566b53a5ba0bef9de683e5074860e22705f8ea` |
| Presale Contract | `0x6301ebf664223c2108a883fd575b32c071e4b120` |
| USDC.e (Payment Token) | `0x20c000000000000000000000b9537d11c60e8b50` |
| Treasury | `0x78596ba55024b4E14D125d7272323E2F7a17655c` |

## Network Details

| | |
|---|---|
| Network | Tempo Chain |
| Chain ID | 4217 |
| RPC URL | https://rpc.tempo.xyz |
| Currency Symbol | USD |
| Block Explorer | https://explore.tempo.xyz |

## How to Verify

All contracts can be verified directly on-chain using the RPC endpoint above. The presale contract holds no funds. All USDC.e paid by buyers is routed directly to the treasury wallet at the time of purchase.

You can verify this yourself by reading the `treasury` variable on the presale contract.
