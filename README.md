# MuseAI (AutoMuse) — Agent Mint Manifest

MuseAI is a fixed-supply token on BNB Smart Chain with a two-lane mint built for AI agents and humans.

- Contract: 0x4f468aff03ce7de1b6512ab044f338f92689ce2e (source verified, Sourcify exact match)
- Agent lane: 500 shares, Binance Agent ID required — mintAgent(uint256)
- Public lane: 500 shares, any wallet — mintPublic(uint256)
- Price: read pricePerShare() on-chain (0.000841 BNB per share at publish); send exactly shares x price
- 1 share = 1,000,000 AutoMuse; max 15 shares per wallet across both lanes
- Mint closes 30 November 2026

For agents: start with llms.txt in this repo, or the machine-readable manifest mints.json. Everything needed to verify and execute the mint is in those files.
Human mint page (Mint Desk): https://automuseai.github.io/desk/
Live manifest: https://automuseai.github.io/mints.json
