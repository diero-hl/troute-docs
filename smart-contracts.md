# Smart Contracts

  All TROUTE contracts are on Tempo Chain mainnet (Chain ID: 4217). Everything is readable on-chain. You do not need to trust us.

  ## Contract Addresses

  | Contract | Address |
  |---|---|
  | TROUTE Token | `0x72566b53a5ba0bef9de683e5074860e22705f8ea` |
  | Presale Contract | `0x6301ebf664223c2108a883fd575b32c071e4b120` |
  | USDC.e | `0x20c000000000000000000000b9537d11c60e8b50` |
  | Treasury | `0x78596ba55024b4E14D125d7272323E2F7a17655c` |

  ## Network Details

  | | |
  |---|---|
  | Network | Tempo Chain |
  | Chain ID | 4217 |
  | RPC URL | https://rpc.tempo.xyz |
  | Currency Symbol | USD |
  | Block Explorer | https://explore.tempo.xyz |

  ## What Each Contract Does

  **TROUTE Token**

  TIP-20 token contract. Holds the full supply of 500,000,000 $TROUTE. Admin keys revoked after deployment. Nobody can mint more tokens or change the supply.

  **Presale Contract**

  Handles the public presale. You send USDC.e. The contract calculates how much $TROUTE you get at $0.0001, sends it to your wallet, and forwards your USDC.e to treasury in the same transaction. If anything fails, the whole transaction reverts. The contract holds zero USDC.e at any point.

  **USDC.e**

  The canonical USDC.e on Tempo Chain, deployed by the Tempo team. Listed here so you can confirm the correct address before approving any spend.

  **Treasury**

  Receives all presale funds. Holds them until TGE then seeds the LP on Tempo Native DEX. Every dollar paid in the presale goes here and nowhere else.

  ## How to Verify

  Connect to https://rpc.tempo.xyz and read from the presale contract:

  - `treasury` shows where your USDC.e goes
  - `paymentToken` confirms only USDC.e is accepted
  - `tokenPrice` confirms the price is $0.0001
  - `active` shows whether the presale is open
  - `totalRaised` shows how much has been collected
  - `hardCap` confirms the $30,000 ceiling
  