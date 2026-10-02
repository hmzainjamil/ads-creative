# Arcads skill pack

This directory contains an assistant skill and scripts for the Arcads external API. It can request image/video assets, poll their status, and use local reference images. It is separate from the Meta Ads utility and the nested Codex plugin.

## Setup

From this directory, the source-supported setup entry point is:

```sh
./scripts/setup.sh
```

The script creates a local `.env` from the example, prompts for Arcads Basic authentication, validates it against the configured Arcads endpoint, creates `MASTER_CONTEXT.md`, synchronizes skill copies, and checks connectivity. This setup command has not been run in this review.

Before running it, review the current Arcads API terms, credentials, account permissions, and credit charges. Keep credentials and local context files private. The API example file contains no usable credential; provide your own through the setup prompt or protected local configuration.

## Contents

- `skills/arcads-external-api/`: API and prompting instructions.
- `scripts/setup.sh`: local setup and optional API connectivity check.
- `scripts/check-arcads-env.sh`: credential and connectivity check.
- `shared/scripts/sync-skill.sh`: syncs canonical skill files to generated locations.
- `references/`: tracked sample/reference images. Confirm image rights and permitted use before generation.
- `logs/`: runtime logs belong on the local machine and are ignored by Git. Do not commit API operation history, asset identifiers, URLs, or customer prompts.

The skill's model and endpoint notes are implementation guidance, not a guarantee of current Arcads availability or credit pricing.

## Source and maintenance

`shared/README.md` marks the shared subtree as upstream-managed; do not edit files there directly. Update the upstream source and use the documented sync process when appropriate. Repository-level source and asset provenance still need maintainer confirmation; see the parent [provenance register](../PROVENANCE.md).
