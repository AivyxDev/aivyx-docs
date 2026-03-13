# Skills Guide

Aivyx includes 22 built-in skills — structured workflows that produce professional results.

## Using Skills

```bash
aivyx run assistant --skill code-review
aivyx skill list
```

## Built-in Skills

| Skill | Description |
|-------|-------------|
| `code-review` | Systematic code review with security and style feedback |
| `deep-research` | Multi-source research with synthesis and citations |
| `security-audit` | Security vulnerability assessment |
| `data-analysis-workflow` | Structured data analysis pipeline |
| `technical-writing` | Professional technical document creation |
| `debugging-systematic` | Step-by-step debugging methodology |
| `project-planning` | Project decomposition into milestones |
| `risk-assessment` | Risk identification, scoring, and mitigation |
| `competitive-analysis` | Market and competitor analysis |
| `report-writing` | Structured report generation |
| `financial-analysis` | Financial data analysis and modeling |
| `content-strategy` | Content planning and strategy |
| `compliance-frameworks` | Regulatory compliance assessment |
| `incident-response` | Incident triage and response playbook |
| `test-strategy` | Test plan development |
| `peer-review-protocol` | Structured peer review process |
| `source-evaluation` | Source credibility assessment |
| `structured-output` | Formatted output generation |
| `task-decomposition` | Break complex goals into steps |
| `delegation-strategy` | Multi-agent delegation planning |
| `multi-source-synthesis` | Combine sources into coherent analysis |
| `aivyx-conventions` | Internal coding conventions |

## Custom Skills

Create TOML manifests in `~/.aivyx/skills/`:

```toml
name = "my-skill"
description = "My custom workflow"

[[steps]]
prompt = "Analyze the input"
tools = ["file_read", "web_search"]
```
