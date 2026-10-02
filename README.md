# ads-creative

This repository groups three separate advertising tools. It is not one integrated creative pipeline, and no end-to-end workflow has been tested.

| Component | What the tracked files contain |
|---|---|
| [Arcads skill pack](arcads-claude-code/README.md) | Claude/Cursor guidance and scripts that authenticate to the Arcads external API, request media generation, and poll results. |
| [Codex plugin snapshot](codex-plugin-cc/README.md) | Nested Node.js plugin project for using Codex from Claude Code. It carries its own package, tests, license, and upstream documentation. |
| [Meta Ads utility](meta-ads-spy/README.md) | Python utilities that query Meta's Ad Library API, extract creatives from snapshot pages, write JSON, and optionally write records to Airtable. |

## Current status

Reviewed 2026-10-02 against the full default-branch tree (340 entries; not truncated).

- The root directory has no shared runtime, installer, dependency manifest, or root license.
- Arcads setup calls an external service and creates local configuration. API usage and credit costs depend on the account and provider.
- Meta utility dependencies are listed in its own `requirements.txt`; no lock file is present there.
- The nested Codex plugin has its own package scripts and test files. No tests or installs were run for this review.
- Image/reference provenance and rights are not documented for every tracked asset. See [content review](CONTENT_REVIEW.md) and [provenance](PROVENANCE.md).

## Start with a component guide

There is no root-level install command. Read the component guide and its security notes before setting credentials or using live accounts:

- [Arcads skill pack](arcads-claude-code/README.md)
- [Meta Ads utility](meta-ads-spy/README.md)
- [Bundled project provenance](PROVENANCE.md)
- [Security and data handling](SECURITY.md)

The Codex plugin README is preserved with the nested upstream project. Its subtree is not an exact copy of the current upstream revision; the recorded comparison is in [PROVENANCE.md](PROVENANCE.md).

## Scope limits

No ad account publishing, campaign mutation, provider credential, Meta API query, Arcads generation, Airtable write, or deployment was verified. Platform access rules, vendor API behavior, available models, pricing, and legal requirements can change and must be checked with current official sources before use.

## Maintainer

[hmzainjamil](https://github.com/hmzainjamil)
