---
name: mindmap
description: This skill should be used when the user asks to "generate LinkedIn post ideas", "mine LinkedIn content ideas", "brainstorm LinkedIn posts for a founder", "build a personal brand content plan", "create a LinkedIn content strategy", "mindmap LinkedIn content", "founder thought leadership content", "personal brand strategy for a founder", mentions "LinkedIn Mindmapper", or wants help with "what should I post on LinkedIn". Conducts deep research and an adaptive interview to generate extensive, personalized LinkedIn post ideas for B2B SaaS founders. This skill generates ideas and prompts, not full post drafts.
argument-hint: [LinkedIn profile URL]
allowed-tools: ["Agent", "AskUserQuestion", "Read", "WebSearch", "WebFetch", "Grep", "Glob", "TaskCreate", "TaskUpdate", "TaskList"]
---

# LinkedIn Mindmapper

Generate extensive, personalized LinkedIn post ideas for B2B SaaS founders through deep research and adaptive interviewing.

## Overview

This skill runs a 3-phase workflow:

1. **Research** — Deep-dive into the founder's background, company, and industry
2. **Interview** — ~10 rounds of adaptive, choice-based questions extracting thinking, experience, and voice
3. **Generation** — Extensive, pillar-organized list of post ideas tailored to this specific founder

The goal: generate as many post ideas as possible WITHOUT diluting the founder's unique voice. Every idea should feel like something only THIS founder could write.

## Phase 1: Research

### Collect LinkedIn URL

If no URL was provided as an argument, ask via AskUserQuestion:

"To get started, share the LinkedIn profile URL of the founder you want to create a content mindmap for."

### Dispatch Research Agent

Launch the `founder-researcher` agent with the LinkedIn URL. The agent performs autonomous deep research and returns a structured profile covering: career background, company overview, industry context, public content, and interview angles.

While the agent works, inform the user:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  RESEARCHING — Deep-diving into background,
  company, and industry. This takes 1-2 minutes.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Present Research Summary

When research completes, display findings in a clean summary: name, role, company description, career background highlights, industry context, and anything notable found.

Then ask via AskUserQuestion: "Is this roughly accurate?"
- Looks good, let's start the interview
- A few things to correct
- Major gaps — let me fill you in

Incorporate any corrections before proceeding.

## Phase 2: Adaptive Interview

Read `references/interview-guide.md` for the full question bank and adaptive logic. Follow it precisely.

### Core Rules

1. **One question at a time** via AskUserQuestion. Present clear, concrete options — never expect long written answers from the founder.
2. **Show progress** at the start of each round:
   ```
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
     ROUND X of Y │ [Topic Name]
     ▓▓▓▓▓▓░░░░░░░░░░░░░░
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   ```
   Use ▓ for completed rounds, ░ for remaining.
3. **Round 1 sets gates** — company stage, team size, and funding determine which later rounds are active. Calculate total active rounds after Round 1 and adjust progress accordingly.
4. **Personalize with research** — customize option text using specific details from the research phase. Reference actual companies, roles, industry trends, and competitors found.
5. **2-3 questions per round** — keep focused. If a response is especially strong (founder picks a rich option), ask one brief follow-up before moving on.
6. **Skip gated rounds** — if solo founder, skip Round 9 (Team & Culture). If pre-revenue, skip Round 8 (GTM). Adjust numbering and progress bar.
7. **Read the energy** — "nothing comes to mind" or "not my style" responses mean move on quickly. Rich selections mean probe slightly deeper.

### Interview Rounds

Rounds 1-10 covering: Company Context, Your Story, Beliefs & Values, Industry POVs, Lessons & Mistakes, Mental Models, Product & Customers, Go-to-Market, Team & Culture, and Content Preferences. Gating logic and all question options are defined in the interview guide — follow it precisely.

After the final round:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  INTERVIEW COMPLETE
  Generating your content mindmap...
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

## Phase 3: Idea Generation

Read `references/content-pillars.md` for the full theme taxonomy with context requirements, and `references/post-formats.md` for format templates.

### Synthesis

Before generating, compile:

1. **Founder profile**: Research + interview responses merged into a clear picture of who this person is and what makes them unique.
2. **Strongest pillars**: Rank by richness — prioritize pillars where the founder showed strong opinions, specific stories, unique perspective, or enthusiasm.
3. **Skip list**: Remove pillars where context requirements aren't met, the founder showed discomfort, responses were generic, or topics are off-limits (from Round 10).
4. **Voice markers**: Note preferred style from Round 10 (teaching / storytelling / hot takes / data / mix) and apply throughout.

### Generation Rules

- **Volume**: At least 5 ideas per strong pillar, ideally 8-12. 2-5 for secondary pillars. Maximize total without diluting voice.
- **Specificity**: Every idea MUST reference something specific to THIS founder — their industry, company, stated beliefs, or experiences. If an idea could apply to any founder, it's too generic. Make it specific or cut it.
- **Mixed detail level**: One-liner prompts for obvious/simple ideas. 3-4 line briefs (hook + angle + key points) for ideas that need more context.
- **Format tags**: Tag each idea with a recommended format from `references/post-formats.md`.
- **Voice fidelity**: Every idea should sound like it comes from someone with this founder's specific background, beliefs, and communication style.

### Output Format

Present ideas grouped by content pillar, strongest first:

```
## [Pillar Name]

1. **[One-liner idea]** → *[Format]*

2. **[Idea title]** → *[Format]*
   Hook: "[Suggested opening line]"
   Angle: [What to cover and why it's unique to them]
   Key points: [Bullets of what to include]

3. **[One-liner idea]** → *[Format]*

[...continue...]
```

### Closing

After presenting all ideas:

"That's your content mindmap — **[X] ideas** across **[Y] pillars**. Want me to expand any of these into a full draft, or go deeper on a specific pillar?"

## Reference Files

- **`references/content-pillars.md`** — Full taxonomy of 50+ LinkedIn content themes organized by pillar, with context requirements for each
- **`references/interview-guide.md`** — Complete adaptive interview structure: all 10 rounds, questions, choice options, gating logic, and synthesis process
- **`references/post-formats.md`** — 12 LinkedIn post format templates with structure, hooks, and a format selection guide
