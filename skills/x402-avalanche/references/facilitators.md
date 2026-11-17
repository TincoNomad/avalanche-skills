# Facilitators on Avalanche

## Options summary
- **Thirdweb x402**: ideal for product/company with broad SDKs and tooling.
- **PayAI**: focused on AI agent cases and machine-to-machine payments.
- **Ultravioleta DAO**: decentralized orientation and gasless operation for users.
- **x402-rs**: self-hosted in Rust for performance and operational control.

## Selection criteria
1. **Operational model**: hosted vs self-hosted.
2. **Expected latency**: real-time loads and volume.
3. **Tech stack**: TypeScript/Node vs Rust.
4. **AI needs**: autonomous payment cases.
5. **Total cost**: facilitator fee + sponsored gas.

## Typical integration
1. Configure facilitator credentials/provider.
2. Declare target network (`avalanche-fuji` or `avalanche-c-chain`).
3. Define prices per endpoint.
4. Use middleware/helper for 402 + verify + settle.
5. Register and monitor txHash per request.

## Practical recommendation
- Start with a hosted facilitator to reduce time to market.
- Migrate to self-hosted only if you need deep control of costs, observability, or compliance.

## When to read this file
- Before starting implementation.
- When you need to justify a facilitator choice.
- If you plan to migrate provider or deployment strategy.
