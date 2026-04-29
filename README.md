# UATU — Ultimate AI Text Unslop

A Claude skill for rewriting and auditing AI-generated text in Russian and English so it reads like strong editorial work, not generated filler.

## What it does

Removes 36+ AI writing patterns across 5 categories:

- **A. Content** — inflated significance, vague attributions, promo language
- **B. Language** — AI vocabulary, copula avoidance, filler words, synonym cycling
- **C. Structure** — em-dash overuse, chatbot openings, uniform rhythm, over-structuring
- **D. Communication** — chatbot replies, sycophancy, reasoning artifacts
- **E. Meta** — uniform paragraph lengths, absence of dates/numbers/names, no authorial position

Includes a 3-tier word replacement table (~100 slop words), rewrite-vs-patch threshold logic, and a two-pass audit.

## Modes

| Mode | Trigger | What it does |
|---|---|---|
| REWRITE | default | Rewrites the draft, returns: issues found → rewritten text → change summary → second-pass audit |
| DETECT | `detect:` prefix | Flags problems only, no edits — use when author wants to decide what to change |
| Voice Calibration | attach 2–3 paragraphs of your writing | Matches your sentence length, connectors, register, and punctuation habits before rewriting |

## How to use

Place `skill__uatu.md` in your `.claude/skills/` directory (or reference it directly in your project's CLAUDE.md).

Then in Claude Code:

```
/uatu
```

Or reference it directly in your prompt: *"use the uatu skill to rewrite this"*.

## Based on

- Wikipedia "Signs of AI writing" (WikiProject AI Cleanup) — foundation
- [blader/humanizer](https://github.com/blader/humanizer) — voice calibration, second-pass audit
- [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) — 3-tier replacement table, structured report, rewrite-vs-patch threshold
- Custom RU layer — verifiability, academic register, fact-density checks

---

*v1.1 — 2026-04-28*
