# Developer Documentation

  No SDK. No API key. No wallet setup. Every TROUTE integration is a standard HTTP call. The docs below cover everything you need.

  All files are served as plain text so agents can fetch and load them directly at runtime.

  ## Skills File

  The full TROUTE API reference. Load this into your agent's context or as a GPT Action and your agent knows every endpoint, parameter, and response format.

  Live: https://www.trouteprotocol.xyz/skills.md

  OpenAPI spec for GPT Actions: https://www.trouteprotocol.xyz/openapi.json

  ## Integration Guide

  How to integrate TROUTE into any agent framework. OpenAI function calling, LangChain, CrewAI, Vercel AI SDK, and a pattern for wrapping any API call with a payment. Full examples in Python and TypeScript.

  Live: https://www.trouteprotocol.xyz/integration.md

  ## AI API Billing

  How to log every AI API call on-chain. Every call to OpenAI, Anthropic, Fal.ai, Modal, or Dune gets a txHash stored permanently on Tempo Chain. Your agent's entire spending history is auditable on-chain, no spreadsheet needed.

  Live: https://www.trouteprotocol.xyz/billing.md

  ## Token Launchpad API

  How to deploy TIP-20 tokens on Tempo Chain. Call POST /api/launch with a name, symbol, description, and image URL. Token is live on a bonding curve in seconds. No wallet. No private key. Graduates automatically to Enshrined DEX at $20,000 market cap.

  Live: https://www.trouteprotocol.xyz/launchpad.md

  ## Off-Ramp Guide

  How to convert USDC.e earnings on Tempo Chain to fiat. Covers balance checking, bridging via relay.link, and off-ramp through Alchemy Pay and MoonPay. Includes Southeast Asia options: GCash, Maya, GrabPay.

  Live: https://www.trouteprotocol.xyz/offramp.md

  ## Quick Start

  ```bash
  # Check the relayer is funded
  curl https://api.trouteprotocol.xyz/api/stats

  # Route your first payment
  curl -X POST https://api.trouteprotocol.xyz/api/route \
    -H "Content-Type: application/json" \
    -d '{
      "to": "0x78596ba55024b4E14D125d7272323E2F7a17655c",
      "amount": "0.10",
      "serviceId": "my-first-troute-payment"
    }'
  ```

  If you get a txHash back, you are integrated. View it at explorer.trouteprotocol.xyz.
  