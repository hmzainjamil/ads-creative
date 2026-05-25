# ads-creative

> **AI-powered ads creative generation skill for Claude Code — Meta/Google ad copy and visuals**

![Status](https://img.shields.io/badge/status-active-brightgreen?style=flat)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat)
![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-FF6B35?style=flat)
![Stars](https://img.shields.io/github/stars/hmzainjamil/ads-creative?style=flat)
![Last Commit](https://img.shields.io/github/last-commit/hmzainjamil/ads-creative?style=flat)

---

## CONCEPTS

| Concept | Description |
|---|---|
| **Ads** | Core primitive of ads creative — fundamental building block |
| **Creative** | Execution layer handling creative operations and state |
| **Meta** | Integration point connecting meta to external services |
| **Google** | Configuration schema for google behavior and routing |
| **Copy** | Optimization layer reducing copy overhead and latency |
| **Claude Code** | Anthropic's CLI — agentic coding and task execution environment |
| **MCP** | Model Context Protocol — standard for tool/resource exposure to Claude |
| **Skill** | Self-contained Claude Code module loaded for domain-specific tasks |
| **Context Window** | Token budget Claude uses per session — managed carefully |
| **Async Agent** | Background task running without blocking main Claude session |

---

## 🔥 Hot Commands

```bash
# Load skill in Claude Code
/skills load ads-creative

# Check skill status
/skills list | grep ads

# Clone and explore locally
gh repo clone hmzainjamil/ads-creative
cd ads-creative

# Run with Claude Code (invoke skill directly)
claude -p "use ads creative skill to handle my task"

# Check README and skill manifest
cat SKILL.md 2>/dev/null || cat README.md | head -50
```

## ■ tip
> **Always check `SKILL.md`** before invoking — it defines exact triggers, required context, and output format. Mismatched context = degraded results.

---

## ☠️ STARTUPS / BUSINESSES

- **Digital agencies** — automate ads workflows, cut delivery time 10×
- **SaaS founders** — plug into existing Claude Code setup, zero infra overhead
- **Freelancers** — use as force-multiplier for client work in creative + meta
- **AI engineers** — extend with custom skills, fork and adapt to your stack

---

## Features

- **Plug-and-play** — works immediately with Claude Code, no custom config
- **Composable** — chain with other skills via `/skills load` pipeline
- **Token-efficient** — designed around context compression and caveman-mode output
- **Tier-0 routing** — delegates sub-tasks to Groq/Ollama to preserve Claude quota
- **Memory-aware** — reads/writes to `~/.claude/` session memory automatically
- **Async capable** — heavy tasks spawned as background agents, non-blocking
- **Production-tested** — used in live agency workflows at hmzainjamil

---

## Installation

```bash
# Option 1: Clone directly
git clone https://github.com/hmzainjamil/ads-creative.git
cd ads-creative

# Option 2: Install as Claude Code skill
cp -r . ~/.claude/skills/ads-creative/

# Option 3: Via gh CLI
gh repo clone hmzainjamil/ads-creative ~/.claude/skills/ads-creative
```

---

## Usage

### Basic

```bash
# Activate in Claude Code session
/skills load ads-creative

# Verify loaded
/skills list
```

### Advanced

```python
# Programmatic invocation via Claude API
import anthropic

client = anthropic.Anthropic()
response = client.messages.create(
    model="claude-sonnet-4-5",
    max_tokens=4096,
    system="You are using the ads-creative skill. AI-powered ads creative generation skill for Claude Code — Meta/Google ad copy and visuals",
    messages=[{"role": "user", "content": "Run the primary workflow"}]
)
print(response.content[0].text)
```

### With MAE Pipeline

```bash
# Route through MAE for parallel execution
mae run "ads creative - execute primary workflow"

# Blast across multiple models
tcc blast "task1 for ads" "task2 for creative" "task3 for meta"
```

---

## Configuration

```yaml
# .claude/skills/ads-creative/config.yaml
skill:
  name: ads-creative
  version: "1.0.0"
  triggers:
    - "ads"
    - "creative"
    - "meta"
  model_routing:
    primary: groq/llama-3.3-70b
    fallback: ollama/qwen2.5:7b
    synthesis: claude-opus
  context:
    max_tokens: 8000
    compression: caveman-mode
```

---

## Architecture

```
User Intent
    │
    ▼
Skill Router ──► Trigger Match ──► ads-creative
                                       │
                    ┌──────────────────┼──────────────────┐
                    ▼                  ▼                   ▼
              Groq (fast)        Ollama (local)     Claude (synthesis)
                    │                  │                   │
                    └──────────────────┴──────────────────►│
                                                     Final Output
```

---

## Integration Examples

### n8n Workflow

```json
{
  "nodes": [
    {
      "name": "ads-creative Trigger",
      "type": "n8n-nodes-base.webhook",
      "parameters": {
        "path": "/ads-hook"
      }
    },
    {
      "name": "Claude Code Skill",
      "type": "n8n-nodes-base.httpRequest",
      "parameters": {
        "url": "http://localhost:3100/api/run-skill",
        "body": {{"skill": "ads-creative", "input": "{{$json.body}}"}}
      }
    }
  ]
}
```

### Python SDK

```python
import subprocess

def run_skill(task: str) -> str:
    result = subprocess.run(
        ['claude', '-p', f'using ads-creative skill: {task}'],
        capture_output=True, text=True
    )
    return result.stdout

output = run_skill("ads analysis for my project")
print(output)
```

---

## Performance

| Metric | Value |
|---|---|
| Avg response time | < 2s (Tier 0) / < 8s (Claude) |
| Token usage | ~500-2000 per invocation |
| Context window | 8K tokens per task |
| Parallel agents | Up to 8 concurrent |
| Cost per run | $0.00 (Tier 0) / ~$0.01 (Claude) |

---

## Related Skills

| Skill | Use Case |
|---|---|
| `caveman` | Compress all outputs — faster, fewer tokens |
| `compact-guard` | Prevent context window overflow |
| `model-routing` | Route to cheapest capable model |
| `context-compression` | Reduce context before heavy tasks |
| `launch-optimized` | Start sessions with full skill stack loaded |
| `find-skills` | Discover skills matching your intent |

---

## Contributing

1. Fork this repo
2. Create feature branch: `git checkout -b feature/ads-improvement`
3. Add/update `SKILL.md` with new capabilities
4. Test: `claude -p "test ads-creative skill"`
5. PR with before/after token usage comparison

---

## Changelog

### v1.0.0
- Initial release with core ads functionality
- Tier-0 model routing (Groq + Ollama)
- Context compression enabled by default
- MAE pipeline integration

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=hmzainjamil/ads-creative&type=Date)](https://star-history.com/#hmzainjamil/ads-creative&Date)

---

## 📜 License

MIT — use freely, attribute appreciated.

---

<div align="center">
  <sub>Built by <a href="https://github.com/hmzainjamil">hmzainjamil</a> · Powered by Claude Code · Part of the OpenClaw ecosystem</sub>
</div>
