# ads-creative

> **AI ads creative system — generate high-converting ad copy and creatives with Claude**

![Status](https://img.shields.io/badge/status-active-brightgreen?style=flat)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat)
![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-FF6B35?style=flat)
![Stars](https://img.shields.io/github/stars/hmzainjamil/ads-creative?style=flat)
![Last Commit](https://img.shields.io/github/last-commit/hmzainjamil/ads-creative?style=flat)

---

## CONCEPTS

| Concept | Description |
|---|---|
| **Ad Copy** | Platform-specific copy with psychological triggers |
| **Creative Brief** | Visual direction for designer/AI generation |
| **Hook** | Attention-grabbing opening lines |
| **CTA** | Conversion-optimized call-to-action variations |
| **Angle** | 10+ unique message angles per product |
| **Audience** | Copy tailored per ICP segment |
| **A/B Variants** | Automatic variant generation for testing |
| **Compliance** | Platform policy checks before publish |

---

## 🔥 Hot Commands

```bash
# Activate skill
claude --skill ads-creative 'your task'

# Quick workflow
claude 'ads automation task'

# Get capabilities
claude 'what can ads-creative do?'
```

## ■ tip
> Mention **ads** or **creative** in your prompt to auto-activate this skill.

---

## ☠️ STARTUPS / BUSINESSES

- **Agencies**: automate ads workflows for clients at scale
- **Founders**: ship creative features 10x faster
- **Freelancers**: deliver copy work with AI precision

---

## Features

- Ads automation
- Creative automation
- Copy automation
- Campaign automation
- Meta automation
- Google automation

---

## Installation

```bash
git clone https://github.com/hmzainjamil/ads-creative.git
cd ads-creative
```

---

## Usage

```bash
# Activate skill in Claude Code
claude --skill ads-creative "your task here"

# Quick workflow
claude "ads automation task"

# Get help
claude "what can ads-creative do?"
```

---

## Configuration

| Variable | Description | Default |
|---|---|---|
| `API_KEY` | Primary API key | Required |
| `MODEL` | AI model to use | claude-3-5-sonnet |
| `DEBUG` | Enable verbose debug | false |
| `MAX_TOKENS` | Max token budget | 8192 |
| `TIMEOUT` | Request timeout (sec) | 30 |
| `LOG_LEVEL` | Logging verbosity | info |

---

## Architecture

```
ads-creative/
├── README.md           # Documentation
├── SKILL.md            # Claude Code skill definition
├── scripts/            # Automation scripts
├── templates/          # Output templates
├── examples/           # Usage examples
└── docs/               # Extended documentation
```

---

## Examples

### Basic

```bash
# Simple task
claude --skill ads-creative "ads task"

# Verbose
claude --skill ads-creative --verbose "detailed creative task"
```

### Advanced Pipeline

```bash
# Chain skills
claude --skill ads-creative "step 1" | claude --skill summarize

# Batch run
for item in $(cat list.txt); do
  claude --skill ads-creative "process $item"
done
```

---

## Troubleshooting

| Issue | Cause | Fix |
|---|---|---|
| Auth fails | Invalid API key | Re-export key in shell profile |
| Timeout | Network or large payload | Increase TIMEOUT value |
| Empty output | Prompt too vague | Add more context |
| Rate limit | Too many requests | Add delay between calls |
| Model error | Unsupported version | Update MODEL variable |
| Import error | Missing dependency | Run pip install -r requirements.txt |

---

## Comparison

| Feature | This Skill | Alt A | Alt B |
|---|---|---|---|
| Claude Code native | ✅ | ❌ | ✅ |
| Auto-activation | ✅ | ✅ | ❌ |
| Free to use | ✅ | ❌ | ✅ |
| Production ready | ✅ | ✅ | ❌ |
| Active maintenance | ✅ | ❌ | ❌ |

---

## Changelog

| Version | Changes |
|---|---|
| v2.0 | Claude 4 support, auto-activation |
| v1.5 | Added keyword triggers |
| v1.0 | Initial release |

---

## Contributing

1. Fork → feature branch → commit → PR
2. Follow conventional commits: `feat:`, `fix:`, `docs:`
3. Add tests for new features

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=hmzainjamil/ads-creative&type=Date)](https://star-history.com/#hmzainjamil/ads-creative&Date)

---

## 📜 License

MIT — free to use, modify, distribute.

---

Made with ❤️ by [@hmzainjamil](https://github.com/hmzainjamil)
