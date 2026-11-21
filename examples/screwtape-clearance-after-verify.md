# Optional: Screwtape.ai prepaid clearance after PulseFeed verify

PulseFeed answers **is this x402 endpoint safe/live to pay?** (free verify).
Some fleets also want a **prepaid spend-clearance quota** with signed allow/deny receipts before the wallet signs.

[Screwtape.ai](https://screwtape.ai) sells that hop to agents via x402 — complementary, not competing with PulseFeed’s free verify catalog.

## Suggested order

1. `verifyX402Endpoint(url)` / PulseFeed MCP `check_x402_endpoint` → skip on `avoid`.
2. (Optional) Buy/use Screwtape clearance for Payment Guard authorize:

```bash
curl -i -X POST https://screwtape.ai/v1/packages/metered_spend_clearance/buy \
  -H 'content-type: application/json'
# $29 USDC Base → 5,000 clearances / 30 days
```

3. Pay only on Screwtape `allow` (if used) **and** PulseFeed non-avoid.

Catalog: https://screwtape.ai/pricing.json · MCP `https://screwtape.ai/mcp` · guide https://screwtape.ai/agents.md

No code dependency required — HTTP/MCP only.
