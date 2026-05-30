# ANCAP public docs

This is the public-safe documentation landing page for the future `ancap-docs` repository.

It is meant to be a standalone trust/integration surface:
- roadmap and status truth,
- architecture and whitepapers,
- ACP / wACP public explanations,
- bridge risk / verification / testnet guidance,
- governance and contribution documents.

The source monorepo still lives at:
- <https://github.com/dragoncattrx-hub/ancap>

## What this docs repo is for

Use this repo to:
- understand what ANCAP is and what is already shipped;
- inspect the public roadmap and current status truth;
- review architecture, tokenomics, and protocol-facing docs;
- verify public contract and bridge documentation;
- find public-safe integration examples and contract sources that still live in the source monorepo.

## Start here

Core truth:
- [Master roadmap](MASTER_ROADMAP.md)
- [Status matrix](docs/STATUS_MATRIX.md)
- [Open-source / GitHub transparency](docs/OPEN_SOURCE_GITHUB_TRANSPARENCY.md)
- [Docs repo bootstrap checklist](docs/ANCAP_DOCS_REPO_BOOTSTRAP.md)
- [Docs repo contributor intake seed](docs/ANCAP_DOCS_CONTRIBUTOR_INTAKE_SEED.md)
- [Docs repo label seed](docs/ANCAP_DOCS_LABEL_SEED.md)
- [Docs repo Discussions seed](docs/ANCAP_DOCS_DISCUSSIONS_SEED.md)
- [Docs repo milestone seed](docs/ANCAP_DOCS_MILESTONE_SEED.md)
- [Docs repo project board seed](docs/ANCAP_DOCS_PROJECT_BOARD_SEED.md)
- [Docs repo initial issues seed](docs/ANCAP_DOCS_INITIAL_ISSUES_SEED.md)
- [Docs repo settings seed](docs/ANCAP_DOCS_REPO_SETTINGS_SEED.md)
- [Docs repo update cadence seed](docs/ANCAP_DOCS_UPDATE_CADENCE_SEED.md)
- [Docs repo Dependabot seed](docs/ANCAP_DOCS_DEPENDABOT_SEED.md)
- Machine-readable bootstrap seeds: `../.github/bootstrap/` (see `../.github/bootstrap/README.md`)

Project/context docs:
- [Vision](docs/VISION.md)
- [Architecture layers](docs/ARCHITECTURE_LAYERS.md)
- [Plan L0 → L3](docs/PLAN_L0_TO_L3.md)
- [Reputation 2.0](docs/REPUTATION_2.md)
- [Staking](docs/STAKING.md)
- [Project whitepaper](docs/WHITEPAPER_PROJECT.md)
- [ACP whitepaper](docs/WHITEPAPER_ACP.md)
- [Legal terms template](docs/LEGAL_TERMS_TEMPLATE.md)

Public trust docs:
- [Bridge risk documentation](docs/BRIDGE_RISK_DOCUMENTATION.md)
- [Official contract-address index](docs/OFFICIAL_CONTRACT_ADDRESSES.md)
- [Contract verification guide](docs/CONTRACT_VERIFICATION_GUIDE.md)
- [Testnet deployment guide](docs/TESTNET_DEPLOYMENT_GUIDE.md)
- [Audit checklist](docs/AUDIT_CHECKLIST.md)
- [Public changelog](docs/CHANGELOG_PUBLIC.md)

## Public code and example surfaces

Those code surfaces currently live in the source monorepo and are linked directly from this docs bundle:
- [Public integration examples index](docs/PUBLIC_INTEGRATION_EXAMPLES.md)
- [Examples index](https://github.com/dragoncattrx-hub/ancap/blob/master/examples/README.md)
- [Stripe credit top-up example](https://github.com/dragoncattrx-hub/ancap/blob/master/examples/payment-integration/python_credit_topup.py)
- [Wallet connection example](https://github.com/dragoncattrx-hub/ancap/blob/master/examples/wallet-connection/python_wallet_login.py)
- [Bridge contract docs](https://github.com/dragoncattrx-hub/ancap/blob/master/contracts/bridge-bsc/README.md)
- [wACP contract source](https://github.com/dragoncattrx-hub/ancap/blob/master/contracts/bridge-bsc/src/WACP.sol)
- [Bridge gateway contract source](https://github.com/dragoncattrx-hub/ancap/blob/master/contracts/bridge-bsc/src/BridgeGateway.sol)

## What is intentionally not in this docs repo

Never publish here:
- private keys, mnemonics, webhook secrets, deploy tokens, or production `.env` data;
- bridge signer internals or hot-wallet operating procedures;
- private infrastructure/admin repos;
- abuse-sensitive thresholds or operator-only anti-fraud internals.

See also:
- [Security policy](SECURITY.md)
- [Contributing](CONTRIBUTING.md)
- [Code of conduct](CODE_OF_CONDUCT.md)
- [Current monorepo status page](https://github.com/dragoncattrx-hub/ancap/blob/master/STATUS.md)

## Why this split exists

The goal is simple: make ANCAP easier to audit, understand, and integrate without exposing the sensitive operator surface.

This landing page is generated into the export bundle by `scripts/export_ancap_docs.py`, so the future `ancap-docs` repo starts with a docs-focused front page instead of the full monorepo operations README.
