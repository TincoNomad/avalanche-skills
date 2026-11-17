# Network and Setup (Avalanche + x402)

## Recommended networks
- **Fuji Testnet**: `chainId 43113`, RPC `https://api.avax-test.network/ext/bc/C/rpc`
- **Avalanche C-Chain Mainnet**: `chainId 43114`, RPC `https://api.avax.network/ext/bc/C/rpc`

## Common contracts (USDC)
- **Fuji USDC**: `0x5425890298aed601595a70AB815c96711a31Bc65`
- **Mainnet USDC (native Circle)**: `0xB97EF9Ef8734C71904D8002F8b6Bc66Dd9c48a6E`

## Minimum environment setup
Define variables for network, receiving wallet, and facilitator:

```env
AVALANCHE_RPC_FUJI=https://api.avax-test.network/ext/bc/C/rpc
AVALANCHE_RPC_MAINNET=https://api.avax.network/ext/bc/C/rpc
USDC_FUJI=0x5425890298aed601595a70AB815c96711a31Bc65
USDC_MAINNET=0xB97EF9Ef8734C71904D8002F8b6Bc66Dd9c48a6E
MERCHANT_WALLET_ADDRESS=0x...
```

If you use Thirdweb facilitator, add:

```env
THIRDWEB_CLIENT_ID=...
THIRDWEB_SECRET_KEY=...
THIRDWEB_SERVER_WALLET_ADDRESS=0x...
```

## Quick checklist
1. Configure wallet on Fuji.
2. Request test USDC on Circle faucet.
3. (Optional) request test AVAX, although the gasless model avoids the need for the final payer.
4. Verify that endpoints respond on the expected network (`avalanche-fuji` or `avalanche-c-chain`).

## When to read this file
- When you are in the project bootstrap phase.
- When an integration fails due to chain/network/address.
- Before moving from testnet to mainnet.
