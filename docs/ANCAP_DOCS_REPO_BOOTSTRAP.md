# ANCAP docs repo bootstrap checklist

Status: active prep for the future public `ancap-docs` repository.

This checklist turns the in-repo export bundle into a predictable first public repo setup once GitHub ownership/access is available.

## Goal

Create the public docs repo quickly without improvising repo settings, contributor surfaces, or security/trust baseline steps.

## Preconditions

Before creating the repo, confirm:

- the final owner/name decision is made (`ANCAP`, `ancap-network`, or another approved fallback);
- the current export bundle is generated with `python scripts/export_ancap_docs.py --target <path> --clean`;
- the generated bundle was spot-checked for public-safe scope (`EXPORT_MANIFEST.md`, root `README.md`, governance files, docs links);
- no private infra notes, secrets, or operator-only runbooks were added to the export set.

## Repo creation sequence

1. Create a new public GitHub repo for `ancap-docs` under the chosen owner.
2. Prefer creating it empty so the exported bundle can become the first real repo state without merge noise.
3. If the helper is being used for the first public launch, `python scripts/bootstrap_ancap_docs_repo.py --repo <owner>/ancap-docs --apply --create-repo` can perform the empty repo creation step before the follow-up settings/labels/milestones pass.
4. Copy the generated export bundle into a clean working directory.
5. Commit and push the exported files as the initial public-safe docs seed.
6. Verify that the root `README.md` is the docs-focused landing page, not the monorepo operations README.

## GitHub settings baseline

After the first push:

- set the repo description to a docs/trust/integration summary rather than an operator/internal description;
- add the project homepage (`https://ancap.cloud/`) if the public launch scope still points there;
- enable branch protection on the default branch;
- enable secret scanning and push protection if available for the owner/account plan;
- keep the repo docs-only unless a later approved split intentionally adds more public-safe assets.
- prefer applying the repo metadata / labels / milestone bootstrap from `python scripts/bootstrap_ancap_docs_repo.py --repo <owner>/ancap-docs` in the source monorepo so the first launch settings come from the checked-in seeds instead of hand-clicking.
- for the very first launch, the same helper can create the empty public repo with `--apply --create-repo`, but do not combine that creation pass with `--apply-branch-protection` before the initial exported bundle is pushed.
- ship the exported `.github/workflows/docs-ci.yml` workflow on the first push so the public repo immediately has a lightweight Docs CI baseline.
- the default required-check context is seeded as `Docs CI / docs-bundle` via `docs/ANCAP_DOCS_CI_SEED.md` and `.github/bootstrap/ancap-docs-ci.json`.
- once the public docs repo has stable CI status-check context names, prefer applying the default-branch protection payload from the same helper with `--apply-branch-protection --status-check-context <context>` so required checks are documented and reproducible too.

## Community baseline

The exported seed already includes contributor-safe issue/PR templates, `docs/ANCAP_DOCS_CONTRIBUTOR_INTAKE_SEED.md`, `.github/bootstrap/ancap-docs-contributor-intake.json`, a baseline `.github/CODEOWNERS` file, a copy-ready `.github/workflows/docs-ci.yml`, a docs-repo-specific `.github/dependabot.yml`, `docs/ANCAP_DOCS_REPO_SETTINGS_SEED.md`, `docs/ANCAP_DOCS_CI_SEED.md`, `docs/ANCAP_DOCS_DEPENDABOT_SEED.md`, and machine-readable `.github/bootstrap/*.json` metadata for the first public setup. The source monorepo now also carries `scripts/bootstrap_ancap_docs_repo.py` as a dry-run/apply helper for repo settings, labels, milestones, and the default-branch protection payload once public CI status-check names exist. After repo creation, also:

- apply the repo metadata / feature-toggle / branch-protection baseline from `docs/ANCAP_DOCS_REPO_SETTINGS_SEED.md` and `.github/bootstrap/ancap-docs-repo-settings.json` before opening broader public contribution, preferably via `python scripts/bootstrap_ancap_docs_repo.py --repo <owner>/ancap-docs` for the gh-driven parts, then add `--apply-branch-protection --status-check-context <context>` once the final public CI checks are known;
- review `.github/CODEOWNERS` and replace the single-maintainer fallback with org teams or additional maintainers once the final GitHub owner/team structure exists;
- enable GitHub Discussions for ideas and technical questions using `docs/ANCAP_DOCS_DISCUSSIONS_SEED.md` as the initial category/pinning/moderation baseline and `.github/bootstrap/ancap-docs-discussions.json` as the copy/paste or scripting source for category descriptions plus copy-ready pinned-topic bodies;
- verify that the exported issue templates and PR template still match `docs/ANCAP_DOCS_CONTRIBUTOR_INTAKE_SEED.md` and `.github/bootstrap/ancap-docs-contributor-intake.json` before opening the repo to broader public contribution, especially the security-report routing and PR verification checklist;
- seed the baseline labels from `docs/ANCAP_DOCS_LABEL_SEED.md` so the first public issue taxonomy matches the roadmap/community model, and use `.github/bootstrap/ancap-docs-labels.json` when creating them in bulk or `scripts/bootstrap_ancap_docs_repo.py` when applying them from the source monorepo:
  - `good first issue`
  - `help wanted`
  - `security`
  - `wallet`
  - `bridge`
  - `docs`
  - `sdk`
  - `contracts`
  - `frontend`
- seed the baseline public milestones from `docs/ANCAP_DOCS_MILESTONE_SEED.md` so roadmap/release-tracking buckets are explicit on day one, and use `.github/bootstrap/ancap-docs-milestones.json` when creating them in bulk or `scripts/bootstrap_ancap_docs_repo.py` when applying them from the source monorepo;
- create a lightweight public roadmap board using `docs/ANCAP_DOCS_PROJECT_BOARD_SEED.md` so fields/views/grouping do not need to be improvised during launch, with `.github/bootstrap/ancap-docs-project-board.json` as the machine-readable field/view reference;
- apply the public communication cadence from `docs/ANCAP_DOCS_UPDATE_CADENCE_SEED.md` so monthly development updates and release-note structure are explicit from day one, use `.github/bootstrap/ancap-docs-update-cadence.json` for copy-ready starter templates, and keep that JSON seed aligned if the cadence changes;
- treat `docs/ANCAP_DOCS_CI_SEED.md` and `.github/bootstrap/ancap-docs-ci.json` as the source of truth for the first public Docs CI workflow/job names and required-check context;
- keep the exported `.github/dependabot.yml` aligned with `docs/ANCAP_DOCS_DEPENDABOT_SEED.md` and `.github/bootstrap/ancap-docs-dependabot.yml` so the docs repo only tracks dependency surfaces that actually exist there, and let the exported Docs CI guard catch byte-for-byte drift between those two files inside the public docs repo seed;
- verify that issue forms/templates render without asking contributors for secrets or private infrastructure details.

## Post-push verification

Before calling the repo bootstrap complete, verify:

- the root `README.md` renders correctly on GitHub;
- the exported docs bundle has no broken relative links;
- source-monorepo fallback links open correctly for files intentionally kept outside `ancap-docs`;
- `LICENSE`, `SECURITY.md`, `CONTRIBUTING.md`, and `CODE_OF_CONDUCT.md` are visible at repo root;
- issue templates, PR template, baseline CODEOWNERS routing, the exported Docs CI workflow, the docs-repo-specific Dependabot config, Discussions, milestones, the first public roadmap board, and the first public update/release-note cadence are live;
- the machine-readable `.github/bootstrap/*.json` seeds still match the human-readable Markdown docs after any launch-time tweaks, including `.github/bootstrap/ancap-docs-contributor-intake.json` vs `docs/ANCAP_DOCS_CONTRIBUTOR_INTAKE_SEED.md`, and `scripts/bootstrap_ancap_docs_repo.py --repo <owner>/ancap-docs` still renders the expected bootstrap plan after those tweaks;
- the repo settings / feature toggles / branch-protection baseline still match `docs/ANCAP_DOCS_REPO_SETTINGS_SEED.md` after any launch-time changes, including any `--status-check-context` names used when applying the protection payload, and the default `Docs CI / docs-bundle` context stays aligned with `docs/ANCAP_DOCS_CI_SEED.md` plus `.github/bootstrap/ancap-docs-ci.json` if workflow/job names change;
- the exported public `.github/dependabot.yml` still matches `.github/bootstrap/ancap-docs-dependabot.yml` byte-for-byte after any launch-time tweaks to docs-repo dependency automation;
- the repo still contains only public-safe material.

## Definition of done for the bootstrap guide

This guide is doing its job when repo creation no longer depends on memory or ad-hoc setup choices: the initial push order, baseline settings, labels, community surfaces, dependency-update automation, and first pinned/update post copy are all documented in one public-safe place.
