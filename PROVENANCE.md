# Provenance register

Reviewed 2026-10-02. This register records the boundaries visible from tracked paths and repository metadata. It does not establish copyright ownership or license compatibility for every file and image.

| Component | Evidence | Provenance status |
|---|---|---|
| Root `ads-creative` | Root has no license file or source manifest | Maintainer should declare repository ownership, origin, and reuse terms |
| `arcads-claude-code` | Arcads API endpoint and Arcads links appear in source; no upstream commit/source URL or license record found | Origin and redistribution rights not established. Ask maintainer to record source and license |
| `codex-plugin-cc` | Package name `@openai/codex-plugin-cc`, Apache-2.0 license and NOTICE are tracked. Upstream [openai/codex-plugin-cc](https://github.com/openai/codex-plugin-cc) exists | Compared bundled subtree with upstream `main` on 2026-10-02: 56 of 81 local file blobs matched; no extra local paths; two upstream paths absent; other content differed. Preserve bundled LICENSE/NOTICE and README; record the intended source commit before syncing |
| `meta-ads-spy` | Python implementation and API docs are tracked; no license or upstream source record found | Origin and reuse rights not established |
| Reference and sample images | Tracked image files under Arcads references; no per-asset source, license, consent, or likeness record found | Rights, model releases, product permissions, and synthetic/real status require maintainer review |

Do not merge upstream changes wholesale. Compare changes, preserve local modifications, licenses, notices, and project-specific instructions. Update the README and changelog when the recorded upstream baseline changes.
