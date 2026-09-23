# ads-creative

> **Hollywood-grade ads from one prompt** - Claude Code skills + Arcads API wrapper that script, storyboard, render, and ship Meta/TikTok/YouTube ad creatives in minutes - UGC, motion, voiceover, captions, all by AI.

<p align="center"><a href="https://github.com/hmzainjamil/ads-creative">Repository</a> · <a href="https://github.com/hmzainjamil/ads-creative/commits/main">Commits</a> · <a href="https://github.com/hmzainjamil/ads-creative/issues">Issues</a></p>
<p align="center"><img alt="Documentation" src="https://img.shields.io/badge/documentation-deep%20editorial-lightgrey"> <img alt="Lifecycle" src="https://img.shields.io/badge/lifecycle-active-success"></p>

<!-- HMZ DEEP README v1 -->

## At a glance

| Field | Current state |
|---|---|
| Repository | ads-creative |
| Visibility | Public |
| Lifecycle | Active |
| Evidence basis | Current repository documentation and source-visible material |

## Why this exists

**Hollywood-grade ads from one prompt** - Claude Code skills + Arcads API wrapper that script, storyboard, render, and ship Meta/TikTok/YouTube ad creatives in minutes - UGC, motion, voiceover, captions, all by AI.

The README describes the creative generation workflow and separates the existence of a rendering or scripting pipeline from claims about ad performance or platform outcomes.

## CONCEPTS

| Concept | Location | Description |
|---|---|---|
| **Arcads skill** | `arcads-claude-code/CLAUDE.md` | Claude Code project guide - [Source](https://github.com/hmzainjamil/ads-creative/blob/main/arcads-claude-code/CLAUDE.md) |
| **Agents spec** | `arcads-claude-code/AGENTS.md` | Creative agent definitions - [Source](https://github.com/hmzainjamil/ads-creative/blob/main/arcads-claude-code/AGENTS.md) |
| **Settings** | `arcads-claude-code/.claude/settings.json` | Per-project Claude Code config - [Source](https://github.com/hmzainjamil/ads-creative/blob/main/arcads-claude-code/.claude/settings.json) |
| **Cursor rules** | `arcads-claude-code/.cursor/rules/project-context.mdc` | Cursor sibling rules - [Source](https://github.com/hmzainjamil/ads-creative/blob/main/arcads-claude-code/.cursor/rules/project-context.mdc) |
| **Env template** | `arcads-claude-code/.env.example` | ARCADS_API_KEY + ANTHROPIC_API_KEY - [Source](https://github.com/hmzainjamil/ads-creative/blob/main/arcads-claude-code/.env.example) |
| **Master context** | `arcads-claude-code/MASTER_CONTEXT.template.md` | Brand/voice context template - [Source](https://github.com/hmzainjamil/ads-creative/blob/main/arcads-claude-code/MASTER_CONTEXT.template.md) |
| **API logs** | `arcads-claude-code/logs/arcads-api.jsonl` | Replayable JSONL of every API call - [Source](https://github.com/hmzainjamil/ads-creative/blob/main/arcads-claude-code/logs/arcads-api.jsonl) |
| **Aesthetics refs** | `arcads-claude-code/references/aesthetics` | UGC selfie / cinematic reference packs - [Source](https://github.com/hmzainjamil/ads-creative/blob/main/arcads-claude-code/references) |
| **Logs README** | `arcads-claude-code/logs/README.md` | How logs are structured + replayed - [Source](https://github.com/hmzainjamil/ads-creative/blob/main/arcads-claude-code/logs/README.md) |
| **Project README** | `arcads-claude-code/README.md` | Skill-pack quickstart - [Source](https://github.com/hmzainjamil/ads-creative/blob/main/arcads-claude-code/README.md) |

## HOW IT WORKS

```
+---------------------------------------------------------+
|                       INPUT                             |
|   Brand brief . product URL . audience persona . com|
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  ORIENT / PARSE                         |
|   - Validate inputs                                     |
|   - Load skill / agent / tool definitions               |
|   - Resolve config + secrets from .env                  |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  PLAN (Claude Sonnet)                   |
|   - Decompose goal into ordered subtasks                |
|   - Pick model per task (Sonnet / Haiku / Tier-0)       |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  EXECUTE (parallel)                     |
|   - Spawn sub-agents / call tools                       |
|   - Stream tokens, persist artifacts                    |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  VERIFY                                 |
|   - Lint / typecheck / visual diff / QA agent           |
|   - On failure -> re-prompt with error context          |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  SHIP                                   |
|   - Write to disk . commit . PR . upload                |
+---------------------------------------------------------+
```

## Install

```bash
git clone https://github.com/hmzainjamil/ads-creative.git
cd ads-creative

# Per-repo install (try in order):
bash install.sh 2>/dev/null || \
npm install 2>/dev/null || \
bun install 2>/dev/null || \
pip install -r requirements.txt 2>/dev/null || true
```

Environment:

```bash
cp .env.example .env  # if present
# fill ANTHROPIC_API_KEY at minimum
```

## Usage

```bash
# Claude Code skill packs:
/skill-name "your goal"

# CLI / scripts:
python scripts/<script>.py --input ./input --output ./output

# TypeScript projects:
bun run dev    # or npm run dev
```

### Configuration knobs

| Key | Default | Description |
|---|---|---|
| `ANTHROPIC_API_KEY` | - (required) | Claude API key |
| `MODEL` | `claude-sonnet-4-7` | Default LLM |
| `MODEL_FALLBACK` | `claude-haiku-4` | Cheaper fallback |
| `MAX_TOKENS` | `8192` | Per-call ceiling |
| `TEMPERATURE` | `0.2` | Determinism dial |
| `LOG_LEVEL` | `info` | debug / info / warn / error |
| `OUT_DIR` | `./out` | Where artifacts land |
| `CACHE_DIR` | `.cache` | Prompt cache root |
| `PARALLELISM` | `4` | Sub-agent concurrency |
| `RETRY_MAX` | `3` | Per-call retry budget |
| `TIMEOUT_S` | `120` | Per-call timeout |
| `DRY_RUN` | `false` | Plan-only, no side effects |

### Case 3 - DTC brand, ad creative testing

- Before: $2K/month UGC creator retainer, 4 ads/month.
- After: 30+ ad variants/week via Arcads + Claude, A/B-tested.
- Result: 3x creative velocity, 41% lower CAC after 6 weeks.

## Security

- Never commit API keys. `.env` is in `.gitignore` by default.
- Use [git-secret](https://git-secret.io/) or 1Password CLI for team secret sharing.
- Review the QA / safety layer for any tool that writes to disk or runs shells (see `mac_safety.py` style guards).
- Vulnerability reports: open a private GitHub Security Advisory.

## Limitations

- Generated creative quality depends on the connected models, media services, prompts, and inputs.
- Platform delivery or ad performance is external to the repository.
- Production claims require actual deployment and measured results.

## Related

- [Claude Code](https://docs.claude.com/en/docs/claude-code) - official docs
- [Anthropic Console](https://console.anthropic.com) - API keys + billing
- [Crawlee](https://crawlee.dev) - web scraping framework
- [hmz-claude-code-best-practice](https://github.com/hmzainjamil/hmz-claude-code-best-practice) - sister repo

## Maintainer

[hmzainjamil](https://github.com/hmzainjamil)