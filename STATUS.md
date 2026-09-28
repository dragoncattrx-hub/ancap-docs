# ANCAP Status (public docs mirror)

> Updated: 2026-09-28  
> Fast truth for the public docs repo. Execution detail lives in [MASTER_ROADMAP.md](MASTER_ROADMAP.md) and [docs/STATUS_MATRIX.md](docs/STATUS_MATRIX.md).

## Current truth

ANCAP is **largely built**, but it is **not fully release-complete end-to-end**.

**Work-stop blockers: none.**

**ACP “mining” clarification:** there is **no PoW mining pool**. The lean-chain miner is a fee-packed block assembler. Staking bootstrap emission is ledger staking, not hash mining. Do not market “mine ACP” as energy-intensive PoW.

**Safe-launch controls (2026-09-28, monorepo):** auth cookie policy is `SameSite=Lax` with prod `CORS_ORIGINS`; free ACP distribution has a 1M cap kill-switch; registration anti-sybil quarantines free grants; Theodore promo script is visible/portable with no spend keys; Terms §3 has a residency draft pending counsel; wACP mint preflight + MetaMask education page shipped in the monorepo.

## Read this next

1. [MASTER_ROADMAP.md](MASTER_ROADMAP.md)
2. [docs/STATUS_MATRIX.md](docs/STATUS_MATRIX.md)
3. [docs/OPEN_SOURCE_GITHUB_TRANSPARENCY.md](docs/OPEN_SOURCE_GITHUB_TRANSPARENCY.md)
4. [docs/OFFICIAL_CONTRACT_ADDRESSES.md](docs/OFFICIAL_CONTRACT_ADDRESSES.md)
5. Monorepo source: https://github.com/dragoncattrx-hub/ancap

## Rule

If any document conflicts with `MASTER_ROADMAP.md`, trust `MASTER_ROADMAP.md`.
