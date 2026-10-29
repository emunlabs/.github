<p>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/emunlabs/.github/main/profile/banner-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/emunlabs/.github/main/profile/banner-light.svg">
  <img src="https://raw.githubusercontent.com/emunlabs/.github/main/profile/banner-dark.svg" alt="emun. Agent audit infrastructure for enterprise Git. The autonomous workforce needs an immutable audit trail. Design partners onboarding now." width="100%">
</picture>
</p>

Software is now written by people and AI agents working side by side in the same repositories. **Emun** gives that work a chain of custody. Every change carries the cryptographic identity of whoever made it, every merge is checked against the authority that person or agent was actually given, and every decision leaves a record your auditors can verify without taking our word for it.

We're onboarding design partners now. **[Become a design partner →](mailto:hello@emunlabs.com?subject=Design%20partner)**

### The proof travels with the code

There's no sidecar database and no new namespace to trust. Emun writes identity, consensus, authority and time into the native Git commit object, so every proof stays with the code it proves.

<p>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/emunlabs/.github/main/profile/commit-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/emunlabs/.github/main/profile/commit-light.svg">
  <img src="https://raw.githubusercontent.com/emunlabs/.github/main/profile/commit-dark.svg" alt="An illustrative Git commit as git cat-file prints it. The author line and SSH signature show who wrote it (Ed25519). An X-tBLS-Aggregate trailer shows who agreed to it (a tBLS quorum). X-BBS-ZK-Proof and X-Revealed-Claims trailers show what it is cleared to do (BBS+ zero-knowledge claims). X-Punch-In and X-Punch-Out trailers show when, as signed times." width="100%">
</picture>
</p>

### What we're building

- **Identity.** Each person and each agent signs with its own key. No shared bot tokens and no anonymous commits.
- **Quorum.** Sensitive paths can need several sign-offs. Threshold BLS folds them into a single signature, checked against the exact revision being merged.
- **Authority.** A mandate sets what an agent is allowed to touch, and BBS+ proofs show its clearance without revealing anything else. Work outside the mandate stops at a required check before merge.
- **Metering.** Agent work is time-stamped and tied to the compute behind it, so every change has its time and cost on the record. You decide what counts as billable.

When an agent steps outside its mandate, the gate reports it on the pull request:

```diff
  emun/gate   pull request #482 · agent:deps-11
+ identity    ed25519 · key held by agent:deps-11
+ revision    e44a0c1 · signature verified
- mandate     deps/** only · touches auth/session.ts
- result      held for review · merge blocked
```

*Illustrative: the commit above and this report show sample values, not customer data.*

### Open by default

The cryptography is free. Every tier gets the full SDK, covering Ed25519, BLS, threshold BLS and BBS/BBS+, and you can use it without ever talking to us. What we charge for is the managed part: the merge gate, the governance record and the receipt.

Emun is in private build. Developer documentation is coming soon, and our first open repositories will appear here as they're ready.

### In this organisation

This [`.github`](https://github.com/emunlabs/.github) repository holds the defaults every Emun repository inherits: the [contributing guide](https://github.com/emunlabs/.github/blob/main/CONTRIBUTING.md), pull request and issue templates, and an opt-in DCO check. A repository's own `LICENSE` and `CONTRIBUTING` take precedence.

### Security

Found a vulnerability? Please report it privately to **security@emunlabs.com**. Please don't open a public issue.

To encrypt your report, use our PGP key:

- Fingerprint: `B47E 9F58 829D A2E5 3E7F  8B74 3816 94AE 61AD 7421`
- Public key: [security-emunlabs-pubkey.asc](https://github.com/emunlabs/.github/blob/main/security-emunlabs-pubkey.asc)

See our [security policy](https://github.com/emunlabs/.github/blob/main/SECURITY.md) for scope and what to expect.

---

[emunlabs.com](https://emunlabs.com) &nbsp;·&nbsp; [hello@emunlabs.com](mailto:hello@emunlabs.com)

**Emun** (אמון) is Hebrew for *trust*. Rearrange the letters and you get `enum`, a fixed set in which every value is accounted for.

<sub>Emun Labs, Inc. · Austin, Texas</sub>
