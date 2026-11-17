# AI Agent Payment Patterns

## Problem x402 solves for agents
AI agents don't fit well in traditional flows (KYC/manual approval/API key sprawl). x402 enables autonomous per-request payments with cryptographic authorization.

## Pattern 1: `exact` for fixed-cost services
Use it when each call costs the same (e.g., one-time query to premium API).
- Advantage: simple to operate and predictable.
- Recommended for autonomous agent MVP.

## Pattern 2: `upto` for variable cost (LLM tokens)
Use it when cost depends on actual consumption.
- The user/agent authorizes maximum.
- Only the consumed value is settled.
- Protects from overcharging and maintains fluid UX.

## Agent wallet architecture
- Agent wallet separate from main wallet.
- Pre-funded budget with spending limits.
- Automatic signing by the agent, no popups per request.
- Withdrawal of remaining balance when task ends.

## Recommended operation rules
1. Small budgets per session.
2. Limits per command/task.
3. Monitoring of accumulated spending.
4. Rotation or reinitialization of wallet for long cycles.

## When to read this file
- When building agents that pay for APIs without human intervention.
- When defining budget governance and limits.
- When implementing chat/token billing with `upto` scheme.
