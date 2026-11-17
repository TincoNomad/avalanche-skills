# Protocol and Headers (x402)

## Base HTTP contract
1. Client requests protected resource.
2. Server responds `HTTP 402 Payment Required` with `accepts[]`.
3. Client signs authorization and retries with `X-PAYMENT`.
4. Server settles and responds `200` + `X-PAYMENT-RESPONSE`.

## Expected body in `402`
Key fields per option in `accepts[]`:
- `scheme` (`exact` or `upto`)
- `network` (e.g., `avalanche-fuji`)
- `maxAmountRequired` (string in base units)
- `resource`
- `payTo`
- `asset` (token contract address)
- `maxTimeoutSeconds` (optional)

## Header `X-PAYMENT`
It is base64 JSON with:
- `x402Version`
- `scheme`
- `network`
- `payload.signature` (EIP-712 signature)
- `payload.authorization`:
  - `from`
  - `to`
  - `value`
  - `validAfter`
  - `validBefore`
  - `nonce` (random bytes32)

## Header `X-PAYMENT-RESPONSE`
Reports settlement result:
- `success` (bool)
- `transaction` (txHash if success)
- `network`
- `payer`
- `errorReason` (if failure)

On errors, it usually returns `402` again with new requirements and `X-PAYMENT-RESPONSE` explaining the cause.

## Common errors
- `Invalid signature`
- `Authorization expired`
- `Nonce already used`
- `Insufficient authorization amount`
- `Insufficient balance`

## When to read this file
- When implementing client request/retry.
- When designing protected endpoint middleware.
- When debugging header and payload discrepancies.
