# LinkedIn Mindmapper

Research-driven LinkedIn content ideation for B2B SaaS founders.

## What it does

1. **Deep Research** — Takes a founder's name and company, then autonomously researches their background, industry, and public content
2. **Adaptive Interview** — Conducts a structured ~10-round interactive interview using yes/no and choice-based questions to extract the founder's thinking, experiences, mental models, and spicy takes
3. **Content Mindmap** — Generates an extensive list of LinkedIn post ideas organized by content pillar, each tailored to the founder's unique voice and expertise

## Install

```bash
claude /install linkedin@andorlabs
```

Or load for a single session:
```bash
claude --plugin-dir /path/to/linkedin-mindmapper
```

## Usage

```
/linkedin:mindmap [founder name, company]
```

The skill guides you through the entire process interactively. No long-form writing required — all input is choice-based.

## Components

- **Skill: `mindmap`** — Main orchestrator that runs the full 3-phase workflow
- **Agent: `founder-researcher`** — Autonomous research agent for deep background analysis
