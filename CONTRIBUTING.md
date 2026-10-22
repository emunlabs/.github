# Contributing to Emun Labs

Every `emunlabs` repository uses these defaults unless it has its own `CONTRIBUTING.md`. **Each repo's own `LICENSE` and `CONTRIBUTING` govern** and take precedence over this file.

## Workflow

1. Members create a branch in the repo. Outside contributors fork it first, and only where the repo says it accepts outside contributions.
2. Name branches `<type>/<short-description>`, for example `feat/artifact-upload`, `fix/manifest-hash` or `docs/delivery-overview`. If there's a tracker ID, include it, for example `ROG-1234-short-description`.
3. Keep each PR small and focused on one change. Split unrelated work into separate PRs.
4. Tests are required. New behavior needs tests, and bug fixes need a test that reproduces the bug. CI must pass.
5. [Conventional Commits](https://www.conventionalcommits.org/) are recommended (`feat:`, `fix:`, `docs:`, `refactor:`, `test:`, `chore:`; `!` or `BREAKING CHANGE:` for breaking changes).

## Semantic versioning (mandatory)

Every versioned project follows [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html):

- **MAJOR** for incompatible (breaking) changes to the public API.
- **MINOR** for backwards-compatible new features.
- **PATCH** for backwards-compatible bug fixes.

Before 1.0.0 (`0.y.z`), the public API isn't stable yet. A breaking change bumps **MINOR** (`0.y` → `0.(y+1)`), and features and fixes bump **PATCH**. Mark breaking changes clearly anyway. Go to `1.0.0` once the API is relied on in production.

Every release:

- is tagged `vX.Y.Z` (for example `v1.4.2`)
- has an entry in `CHANGELOG.md` in [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) format (`Added`, `Changed`, `Deprecated`, `Removed`, `Fixed`, `Security`).

### Who decides the version

Contributors don't pick version numbers or edit the changelog. Just describe what your PR changes and answer the template's question about whether it changes how the artifact API or MCP behaves. The maintainers decide the major, minor or patch bump and write the changelog entry when they cut a release.

### Artifact API and MCP

The artifact API and the MCP tool interfaces are public contracts. Any **breaking** change to them is a **MAJOR** bump (from 1.0.0 onward; before 1.0, a MINOR bump with the break called out). If your PR changes how either behaves, say so in the PR template and include migration notes, so the maintainers can version the release correctly.

## Code review

- Every PR needs **at least one approval** before it's merged.
- Describe breaking changes and give migration notes in the PR.

## Data and secrets

- **Never commit secrets:** API keys, tokens, private keys, `.env` / `.dev.vars` files, credentials. Use the platform's secret store.
- **Never commit real company data** from Rogue Machine (RM) or Emun: case files, evidence, testimony, personal data, customer or internal records. Use synthetic fixtures only.
- If something sensitive gets committed, report it right away. Rotate the secret and purge it from history. Deleting it in a later commit isn't enough.

## Technology

- **Backend is Rust-first** (including Rust/WASM on Cloudflare Workers via `workers-rs`).
- **TypeScript is only for the browser.** Don't write new backend services in Node/TypeScript.
- Any exception needs to be recorded and approved.

## License

- Each repo's own `LICENSE` file governs.
- Unless a repo says otherwise, its code is **proprietary to Emun Labs, Inc.** and doesn't accept outside contributions.
- Keep third-party license notices and keep any `NOTICE` / third-party files up to date.
