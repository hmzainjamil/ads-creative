# ads-creative

> **AI ads creative — generate high-converting ad copy and campaigns with Claude**

![Status](https://img.shields.io/badge/status-active-brightgreen?style=flat)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat)
![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-FF6B35?style=flat)
![Stars](https://img.shields.io/github/stars/hmzainjamil/ads-creative?style=flat)
![Last Commit](https://img.shields.io/github/last-commit/hmzainjamil/ads-creative?style=flat)

---

## CONCEPTS

| Concept | Description |
|---|---|
| **Ads** | Core ads capability for ads-creative workflows |
| **Creative** | Core creative capability for ads-creative workflows |
| **Copy** | Core copy capability for ads-creative workflows |
| **Campaign** | Core campaign capability for ads-creative workflows |
| **Meta** | Core meta capability for ads-creative workflows |
| **Google** | Core google capability for ads-creative workflows |
| **Social** | Core social capability for ads-creative workflows |
| **Conversion** | Core conversion capability for ads-creative workflows |

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
- **Founders**: ship creative features 10x faster with Claude
- **Freelancers**: deliver copy work with AI-assisted precision

---

## Features

- Ads automation and orchestration
- Creative automation and orchestration
- Copy automation and orchestration
- Campaign automation and orchestration
- Meta automation and orchestration
- Google automation and orchestration

---

## Installation

```bash
git clone https://github.com/hmzainjamil/ads-creative.git
cd ads-creative
```

---

## Usage

```bash
# In Claude Code
/ads-creative
claude 'ads task here'
```

---

## Configuration

| Variable | Description | Default |
|---|---|---|
| `API_KEY` | Primary API key for service access | Required |
| `MODEL` | AI model to use | claude-3-5-sonnet |
| `DEBUG` | Enable verbose debug output | false |
| `MAX_TOKENS` | Max token budget per request | 8192 |
| `TIMEOUT` | Request timeout in seconds | 30 |
| `LOG_LEVEL` | Logging verbosity | info |

---

## Architecture

```
ads-creative/
├── README.md           # This file
├── SKILL.md            # Claude Code skill definition
├── scripts/            # Automation and utility scripts
├── templates/          # Output and prompt templates
├── examples/           # Usage examples and demos
├── tests/              # Unit and integration tests
└── docs/               # Extended documentation
    ├── setup.md        # Setup guide
    ├── api.md          # API reference
    └── faq.md          # Frequently asked questions
```

---

## Examples

### Basic Usage

```bash
# Activate in Claude Code
claude --skill ads-creative "your task here"

# With options
claude --skill ads-creative --verbose "detailed task"
```

### Advanced Workflow

```bash
# Chain with other skills
claude --skill ads-creative "step 1" | claude --skill summarize

# Batch processing
for item in list; do
  claude --skill ads-creative "process $item"
done
```

---

## Troubleshooting

| Issue | Cause | Fix |
|---|---|---|
| Auth fails | Invalid/expired API key | Re-export key in shell profile |
| Timeout error | Network latency or large payload | Increase TIMEOUT value |
| Empty output | Prompt too vague | Add more context to request |
| Rate limit hit | Too many requests | Add delay between calls |
| Model error | Unsupported model version | Update MODEL variable |
| Import error | Missing dependency | Run pip install -r requirements.txt |

---

## Comparison

| Feature | This Skill | Alternative A | Alternative B |
|---|---|---|---|
| Claude Code native | ✅ | ❌ | ✅ |
| Auto-activation | ✅ | ✅ | ❌ |
| Free to use | ✅ | ❌ | ✅ |
| Production ready | ✅ | ✅ | ❌ |
| Active maintenance | ✅ | ❌ | ❌ |

---

## Contributing

1. Fork this repo
2. Create feature branch: `git checkout -b feat/your-feature`
3. Commit changes: `git commit -m 'feat: add feature'`
4. Push: `git push origin feat/your-feature`
5. Open PR

---

## Changelog

| Version | Changes |
|---|---|
| v2.0 | Major refactor, Claude 4 support |
| v1.5 | Added auto-activation keywords |
| v1.0 | Initial release |

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=hmzainjamil/ads-creative&type=Date)](https://star-history.com/#hmzainjamil/ads-creative&Date)

---

## 📜 License

MIT — free to use, modify, and distribute.

---

Made with ❤️ by [@hmzainjamil](https://github.com/hmzainjamil)
