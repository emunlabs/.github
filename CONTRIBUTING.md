# Welcome to the Emun Labs contributing guide

Thanks for helping out. This guide walks you through the contribution workflow, from opening an issue to getting your pull request (PR) merged.

Every `emunlabs` repository uses these defaults unless it has its own `CONTRIBUTING.md`. **Each repo's own `LICENSE` and `CONTRIBUTING` govern** and take precedence over this file.

## New contributor guide

- Read the repo's `README` to see what the project does and how to run it.
- Check the repo's `LICENSE`. Unless a repo says otherwise, its code is **proprietary to Emun Labs, Inc.** and doesn't accept outside contributions. Open-source repos say so in their `README` and `LICENSE`.
- Helpful background: [Collaborating with pull requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests) and [Conventional Commits](https://www.conventionalcommits.org/).

## Getting started

### Issues

#### Create a new issue

If you find a bug or want a feature, search the existing issues first. If nothing matches, open a new one with the bug report or feature request template.

#### Solve an issue

Look through the open issues for one you'd like to take. Comment on it before you start so work isn't duplicated.

### Make changes

1. Members create a branch in the repo. Outside contributors fork it first, and only where the repo accepts outside contributions.
2. Name branches `<type>/<short-description>`, for example `feat/artifact-upload`, `fix/manifest-hash` or `docs/delivery-overview`. If there's a tracker ID, include it, for example `ROG-1234-short-description`.
3. Keep each change small and focused. Split unrelated work into separate PRs.
4. Follow the technology rules: **the backend is Rust-first** (including Rust/WASM on Cloudflare Workers via `workers-rs`), and **TypeScript is only for the browser**. Any exception needs to be recorded and approved.
5. Tests are required. New behavior needs tests, and a bug fix needs a test that reproduces the bug.

### Commit your update

Use [Conventional Commits](https://www.conventionalcommits.org/) where you can (`feat:`, `fix:`, `docs:`, `refactor:`, `test:`, `chore:`).

- **Never commit secrets:** API keys, tokens, private keys, `.env` / `.dev.vars` files, credentials. Use the platform's secret store.
- **Never commit real company data** from Rogue Machine (RM) or Emun: case files, evidence, testimony, personal data, customer or internal records. Use synthetic fixtures only.
- If something sensitive gets committed, report it right away. The secret gets rotated and purged from history; deleting it in a later commit isn't enough.

### Pull request

When you're done, open a PR and fill in the template:

- Describe what changed and why, and link the issue.
- If the repo has a public API or MCP interface, say whether your change affects how it behaves, and add migration notes if it does.
- List the tests you ran. CI must pass.

Every PR needs **at least one approval** before it's merged. A reviewer may ask for changes; push them to the same branch.

You don't pick a version number or edit the changelog. That's done at release time (see below).

### Your PR is merged

Thanks for contributing. Your change ships in the next release.

## Releases and versioning (maintainers)

Every versioned project follows [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html), always. **The maintainers decide the version when they cut a release**, not the PR author.

- **MAJOR** for incompatible (breaking) changes to the public API.
- **MINOR** for backwards-compatible new features.
- **PATCH** for backwards-compatible bug fixes.

Before 1.0.0 (`0.y.z`), a breaking change bumps **MINOR** and features and fixes bump **PATCH**. Go to `1.0.0` once the API is relied on in production.

Where a repo has an artifact API or MCP tool interface, those are public contracts: any breaking change to them is a **MAJOR** bump (from 1.0.0 onward; before 1.0, a MINOR bump with the break called out).

Every release is tagged `vX.Y.Z` (for example `v1.4.2`) and gets a `CHANGELOG.md` entry, written by the maintainers, in [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) format (`Added`, `Changed`, `Deprecated`, `Removed`, `Fixed`, `Security`).

## License

- Each repo's own `LICENSE` file governs.
- Unless a repo says otherwise, its code is **proprietary to Emun Labs, Inc.**
- Keep third-party license notices and any `NOTICE` / third-party files up to date.
