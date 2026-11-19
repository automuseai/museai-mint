# MuseAI (AutoMuse) — Agent Mint Skill

> Contract (BNB Smart Chain, chainId 56):
> `0x4f468aff03ce7de1b6512ab044f338f92689ce2e`
> Source: AgentMintDualToken.sol — VERIFIED on Sourcify (exact match,
> creation + runtime, 2026-11-17). Read the source and compare it with
> the deployed bytecode before minting.
> Manifest: https://automuseai.github.io/mints.json
> Mint page: https://automuseai.github.io/ · Desk: https://automuseai.github.io/desk/

## What this is

A paid, two-lane mint for MuseAI (AutoMuse). 1 share = 1,000,000
AutoMuse. Total 1,000 shares (1,000,000,000 AutoMuse), first come first
served. Minting closes 30 November 2026 or when a lane sells out.

## Lanes

- **Agent lane** — `mintAgent(uint256 shares)`: requires a Binance Agent
  ID (canonical registry `0x60B9262456dE011F7d15a54CdD8c48bAaa8B022F`,
  `balanceOf(account) > 0`). Pool: 500 shares.
- **Public lane** — `mintPublic(uint256 shares)`: any wallet, no Agent
  ID needed. Pool: 500 shares.

## Rules

- Price: read `pricePerShare()` immediately before minting (0.000841 BNB
  per share at publish; owner-adjustable via `setPrice`). Send exactly
  `shares * pricePerShare()` BNB as msg.value — the contract reverts on
  any other amount.
- Max 15 shares per wallet ACROSS BOTH LANES combined.
- Before minting, read `mintingOpen()`, `agentSharesRemaining()` and
  `publicSharesRemaining()`. Simulate the transaction first and proceed
  only if it succeeds.
- Calldata for 1 share — agent lane:
  `0xe59c63390000000000000000000000000000000000000000000000000000000000000001`
  public lane:
  `0xefd0cbf90000000000000000000000000000000000000000000000000000000000000001`
  (For N shares, replace the final 32-byte word with N.)
- Binance Agentic Wallet agents: send the transaction from the Agent ID
  wallet with the baw CLI / agentic wallet tooling, value as above.
- This is a PAID mint. Execute only under your principal's standing
  authorization for paid mints, or after their explicit approval.

## Terms

Transfers are locked until the owner opens trading after the PancakeSwap
pool is created. No tax, no blacklist, no hidden mint, no proxy, no
upgrade path, no refunds. Supply is hard-capped in the verified source.
Nothing here is an investment offer; token value is not promised.
