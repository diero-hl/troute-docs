# Security

  ## Contract Design

  The TROUTE presale contract was designed with a minimal attack surface. It does one thing: accept USDC.e and send $TROUTE tokens to the buyer in the same atomic transaction. There is no complex logic, no admin function that can rug, and no way for the contract to hold funds.

  Key design decisions:

  - No funds are held in the presale contract. All USDC.e paid by buyers is forwarded directly to the treasury wallet at the moment of purchase. The contract balance is always zero.
  - The presale contract does not hold admin keys over the TROUTE token after deployment. No address can mint additional tokens or modify the supply after launch.
  - Token transfers are executed atomically. If the USDC.e transfer or the $TROUTE transfer fails for any reason, the entire transaction reverts. Buyers cannot lose funds to a partial execution.
  - The contract accepts only USDC.e at the address `0x20c000000000000000000000b9537d11c60e8b50`. No other token is accepted, and this is enforced at the contract level.

  ---

  ## Contract Addresses

  | Contract | Address |
  |---|---|
  | TROUTE Token | `0x72566b53a5ba0bef9de683e5074860e22705f8ea` |
  | Presale Contract | `0x6301ebf664223c2108a883fd575b32c071e4b120` |

  ---

  ## Audit

  The TROUTE presale contract is a minimal TIP-20 exchange contract with no external calls, no admin functions post-deployment, and no fund custody. A formal third-party audit is in progress. Results will be published here and announced on Twitter at @TROUTEprotocol when complete.

  In the meantime, the contract is small enough that any developer familiar with EVM contracts can read it in full in under 10 minutes. We encourage you to do so before participating.

  ---

  ## How to Verify the Contract Yourself

  You do not need to trust us. You can verify the contract behavior directly on-chain before sending any funds.

  1. Connect to Tempo Chain RPC: `https://rpc.tempo.xyz`
  2. Read the `treasury` variable on the presale contract to confirm where your USDC.e goes
  3. Read the `paymentToken` variable to confirm only USDC.e is accepted
  4. Read the `active` variable to confirm the presale is open
  5. Read the `tokenPrice` variable to confirm the price is exactly $0.0001
  6. Read the `hardCap` variable to confirm the ceiling is $30,000 USDC.e

  Every dollar that goes into the presale is traceable on-chain from your wallet to the treasury. Nothing is hidden.

  ---

  ## Risk Disclosure

  Participating in a token presale carries risk. Smart contracts can have bugs even after audits. The value of $TROUTE after TGE is not guaranteed and may go to zero. The TROUTE protocol is early-stage software and may change. Only participate with funds you can afford to lose entirely.

  This is not financial advice.
  