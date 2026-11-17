# Security and Settlement

## Critical security controls
- **Unique nonce** per authorization (random `bytes32`) for anti-replay.
- **Short time window** (`validAfter`, `validBefore`) (5-10 min).
- **EIP-712 validation** of signer against `authorization.from`.
- **Strict verification** of `network`, `asset`, `payTo`, `value`.
- **Idempotency** with tracking of `txHash` and used nonces.

## On-chain settlement
In x402 on EVM, settlement relies on `transferWithAuthorization` (EIP-3009):
1. Signature and payload are validated.
2. Facilitator sends tx on-chain (sponsored gas).
3. It is confirmed and returns `txHash`.

On Avalanche, the full flow usually takes ~1.5-2.3s.

## Recommended monitoring
- Verify on-chain even if you use facilitator webhooks.
- Save settlement receipts for auditing and support.
- Apply rate limiting per wallet/IP to reduce abuse.

## Failures you must simulate
- Corrupt signature or different signer.
- Reused nonce.
- Expired authorization.
- Amount lower than required.
- Incorrect token or network.

## When to read this file
- When implementing backend validations.
- When designing observability and auditing.
- During security reviews or hardening.
