# Public changelog

Curated public-facing changelog for major ANCAP repository milestones.

For exhaustive implementation detail, see [LOG.md](https://github.com/dragoncattrx-hub/ancap/blob/master/LOG.md).

## 2026-05-30 — contract trust index + public examples index

- added `docs/OFFICIAL_CONTRACT_ADDRESSES.md` as the public-safe canonical index for ACP / `wACP` / `BridgeGateway` identities
- linked the official address index from trust, verification, pilot, deployment, and contract-doc surfaces so reviewers have one canonical public lookup path
- kept fake-contract / scam-warning guidance next to the official address list for the future `ancap-docs` trust surface
- added `docs/PUBLIC_INTEGRATION_EXAMPLES.md` as a contributor-friendly index for publishable payment, wallet, and bridge-facing example surfaces
- linked that new examples index from repo/docs landing surfaces so the seeded public integration backlog no longer depends on browsing the monorepo tree manually

## 2026-05-27 — release + transparency + deployment-story cleanup

- added a tag-driven GitHub release workflow with draft release generation and release-gate checks
- published public integration examples for Stripe-backed credit top-up and wallet-auth flow
- linked public `wACP` / `BridgeGateway` contract sources more clearly from repo-facing docs
- removed the abandoned Cloudflare Workers repo path so Docker/nginx remains the single declared production deployment path

## 2026-05-27 — Stripe / payouts / deploy hardening

- shipped Stripe-backed ANCAP credit top-up adapter surfaces
- shipped payout request workflow
- fixed a real production-like Alembic migration defect exposed during live deploy
- tightened CI so frontend e2e reruns on backend/migration changes
- cleaned repo/dev docs/config around bundled Postgres default-secret scanning false positives

## 2026-05-24 — mobile SDK native helper exports

- expanded `ancap-mobile` SDK native helper exports
- synchronized mobile roadmap status with actual shipped capability

## 2026-04-30 — ACP wallet balance correctness

- corrected creator-vesting labeling and genesis vout layout assumptions
- improved ACP balance presentation and integer-safe amount handling

## 2026-04-29 — frontend audit and local ACP chain bring-up

- landed a frontend UX/a11y/privacy/SEO audit pass
- brought up local ACP chain/genesis flow for real wallet balance visibility
- repaired backend test suite and fixed several production bugs surfaced by tests

## Notes

This changelog is intentionally selective and public-facing.
It should summarize meaningful external milestones, while [LOG.md](https://github.com/dragoncattrx-hub/ancap/blob/master/LOG.md) remains the detailed internal change log for reproducibility.
