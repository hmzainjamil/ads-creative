# Security and data handling

## Scope

This note covers the three bundled components. They have separate runtimes and data flows; no unified security boundary exists.

## Arcads API skill pack

- Authentication is configured locally through `ARCADS_BASIC_AUTH` or another source-supported credential path. Do not commit real credentials or paste them into prompts.
- Setup validates credentials against an external endpoint. Skill operations can send prompts, product/reference data, and generation requests to Arcads and incur account usage or charges.
- Local logs can contain asset/project identifiers, generation metadata, credit usage, and output URLs. The prior public tree included runtime log records; this branch removes that file and ignores future `logs/*.jsonl` files. Earlier commits, forks, caches, and clones may retain the records.
- Keep local generated media and `MASTER_CONTEXT.md` private. Confirm consent and rights for reference images, likenesses, trademarks, and product materials.

## Meta Ads utility

- Store `META_ACCESS_TOKEN` and `AIRTABLE_PAT` only in a protected local `.env`; never commit them. Grant the narrowest permissions required.
- The utility sends API requests to Meta, visits snapshot URLs using Selenium, downloads media for optional transcription, and can write ad records/media links to Airtable.
- Optional video transcription uses local Whisper after downloading source media; downloaded temporary files and resulting transcripts still need local privacy controls.
- The competitor-discovery tool requests a user-supplied URL. Do not use internal/private URLs; review network access and redirect behavior before running on untrusted input.

## Bundled Codex plugin snapshot

`codex-plugin-cc` is a separate Node.js project. Its original README, LICENSE, NOTICE, tests, and plugin files are retained. It can interact with Codex CLI/app-server and the caller's workspace. Review its upstream documentation and permission model before installation. This review did not run its tests or inspect it as a security audit.

## Evidence limits

No credential scanning of all Git history, live service calls, provider privacy review, legal review, or deployment test was performed. See [PROVENANCE.md](PROVENANCE.md) and [CONTENT_REVIEW.md](CONTENT_REVIEW.md).
