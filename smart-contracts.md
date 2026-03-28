# Smart Contracts

  All TROUTE protocol contracts are deployed on Tempo Chain mainnet (Chain ID: 4217). Every contract is permissionless and fully verifiable on-chain. You can read every variable and confirm exactly how each contract behaves before sending a single dollar.

  ---

  ## Contract Addresses

  | Contract | Address |
  |---|---|
  | TROUTE Token | `0x72566b53a5ba0bef9de683e5074860e22705f8ea` |
  | Presale Contract | `0x6301ebf664223c2108a883fd575b32c071e4b120` |
  | USDC.e (Payment Token) | `0x20c000000000000000000000b9537d11c60e8b50` |
  | Treasury | `0x78596ba55024b4E14D125d7272323E2F7a17655c` |

  ---

  ## Network Details

  | | |
  |---|---|
  | Network | Tempo Chain |
  | Chain ID | 4217 |
  | RPC URL | https://rpc.tempo.xyz |
  | Currency Symbol | USD |
  | Block Explorer | https://explore.tempo.xyz |

  ---

  ## What Each Contract Does

  **TROUTE Token**

  The TIP-20 token contract for $TROUTE. It holds the total supply of 500,000,000 tokens and manages all transfers and approvals in the standard TIP-20 format used by Tempo Chain. The contract was funded at deployment and admin keys were revoked immediately after. No address can mint new tokens or modify the supply at any point going forward. The contract is immutable.

  **Presale Contract**

  The contract that handles the public presale. When you send USDC.e, the contract calculates the correct $TROUTE amount at the fixed price of $0.0001, transfers $TROUTE directly to your wallet, and forwards your USDC.e to the treasury, all in the same atomic transaction. If any step fails, the entire transaction reverts. You cannot receive a partial fill and you cannot lose USDC.e to a failed transfer. The contract holds no USDC.e at any point. Every dollar passes through to treasury instantly at the moment of purchase.

  **USDC.e**

  The bridged stablecoin native to Tempo Chain. This is not a TROUTE contract. It is the canonical USDC.e token deployed by the Tempo Chain team and used as the settlement currency across the entire Tempo ecosystem. It is listed here so you can verify you are approving the correct token address before interacting with the presale. Always confirm this address matches before signing any approval.

  **Treasury**

  The wallet that receives all presale funds. USDC.e raised during the presale is held here until TGE, at which point it is used entirely to seed the liquidity pool on Tempo Native DEX. You can verify on-chain that every USDC.e paid through the presale contract flows directly to this address and nowhere else.

  ---

  ## How to Verify on Chain

  Connect to the Tempo Chain RPC at https://rpc.tempo.xyz and read the following variables directly on the presale contract before you send any funds:

  - `treasury` confirms exactly where your USDC.e goes after purchase
  - `paymentToken` confirms that only USDC.e is accepted, nothing else
  - `tokenPrice` confirms the price is fixed at $0.0001 per $TROUTE
  - `active` confirms whether the presale is currently open
  - `totalRaised` confirms the total USDC.e collected so far
  - `hardCap` confirms the presale ceiling is $30,000 USDC.e

  Every transaction is also visible in real time on the Tempo Chain block explorer at explore.tempo.xyz.
  