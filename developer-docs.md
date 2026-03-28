# Developer Documentation

  TROUTE is designed for zero-friction integration by AI agents. No SDK, no API key, no wallet required. Every integration is a standard HTTP call. The developer docs below cover everything from routing your first payment to launching tokens and converting earnings to fiat.

  All docs are also served as plain-text files so AI agents can fetch and parse them directly at runtime.

  ---

  ## Skills File (Full API Reference)

  The master reference for all TROUTE capabilities. Load this into your agent's system prompt or GPT Action to give your agent complete knowledge of every TROUTE endpoint, parameter, and example.

  Live URL: https://www.trouteprotocol.xyz/skills.md

  OpenAPI spec (for GPT Actions): https://www.trouteprotocol.xyz/openapi.json

  ---

  ## Payment Routing Integration

  How to integrate TROUTE into any agent framework. Covers the full integration path from loading the skills file to routing your first payment. Includes examples for OpenAI function calling, LangChain, CrewAI, Vercel AI SDK, and a pattern for wrapping any API call with a payment.

  Live URL: https://www.trouteprotocol.xyz/integration.md

  ---

  ## AI API Billing (On-Chain Audit Trail)

  How to use TROUTE to log every AI API call your agent makes on-chain. Each call to OpenAI, Anthropic, Fal.ai, Modal, or Dune generates a txHash stored permanently on Tempo Chain. Your agent's entire API spending history becomes publicly auditable and immutable with no spreadsheet required.

  Live URL: https://www.trouteprotocol.xyz/billing.md

  ---

  ## Token Launchpad API

  How to deploy TIP-20 tokens on Tempo Chain via TROUTE. Any AI agent can call POST /api/launch with a name, symbol, description, and image URL and have a token live on a bonding curve in seconds. No wallet, no private key, no manual chain interaction. Tokens graduate to Enshrined DEX automatically at a $20,000 market cap.

  Live URL: https://www.trouteprotocol.xyz/launchpad.md

  ---

  ## Off-Ramp Guide (USDC.e to Fiat)

  How an AI agent converts USDC.e earnings on Tempo Chain to fiat currency. Covers checking balance on-chain, bridging USDC.e to Ethereum via relay.link, and generating off-ramp URLs for Alchemy Pay and MoonPay including Southeast Asia methods (GCash, Maya, GrabPay).

  Live URL: https://www.trouteprotocol.xyz/offramp.md

  ---

  ## Quick Start

  Read the skills file and make your first payment in under 5 minutes:

  ```bash
  # 1. Fetch the full skills file
  curl https://www.trouteprotocol.xyz/skills.md

  # 2. Check the relayer is funded
  curl https://api.trouteprotocol.xyz/api/stats

  # 3. Route your first payment
  curl -X POST https://api.trouteprotocol.xyz/api/route \
    -H "Content-Type: application/json" \
    -d '{
      "to": "0x78596ba55024b4E14D125d7272323E2F7a17655c",
      "amount": "0.10",
      "serviceId": "my-first-troute-payment"
    }'
  ```

  If you get back a txHash, your integration is working.

  View it live: https://explorer.trouteprotocol.xyz
  