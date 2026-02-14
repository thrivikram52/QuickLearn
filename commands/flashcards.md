---
name: flashcards
description: Generate flashcard tables for rapid review and spaced repetition on a technical concept
argument-hint: "<concept> e.g., auto-encoders, transformers, attention mechanism"
allowed-tools:
  - Read
  - Write
  - Bash
  - Glob
  - Grep
  - WebSearch
---

# QuickLearn — Flashcard Generator

Generate flashcards for rapid review and spaced repetition. Output as a markdown table for easy reading in VS Code / Obsidian.

## Process

1. **Check for existing QuickLearn content**: Look in `./quicklearn/` for the concept to extract key facts.

2. **Generate flashcard file**: `./quicklearn/<concept>/flashcards.md`

3. **Structure the flashcards**:

```markdown
# <Concept> — Flashcards

> Use these for spaced repetition. Cover the "Answer" column and test yourself.
> Review daily for 3 days, then weekly for 3 weeks for long-term retention.

## Core Concepts

| # | Question | Answer |
|---|----------|--------|
| 1 | What is <concept>? | [Concise answer] |
| 2 | ... | ... |

## Key Formulas

| # | Formula Name | Formula | When to Use |
|---|-------------|---------|-------------|
| 1 | [Name] | $formula$ | [Context] |

## Architecture & Components

| # | Component | Role | Key Detail |
|---|-----------|------|------------|
| 1 | [Name] | [What it does] | [Important property] |

## Code Patterns

| # | Pattern | Code Snippet | Purpose |
|---|---------|-------------|---------|
| 1 | [Name] | `code` | [Why] |

## Common Confusions

| # | Confusion | Clarification |
|---|-----------|---------------|
| 1 | [Misconception] | [Correct understanding] |

## Comparisons

| # | This Concept | vs. | Key Difference |
|---|-------------|-----|----------------|
| 1 | [Concept] | [Alternative] | [Difference] |
```

4. **Flashcard counts**:
   | Category | Target Count |
   |----------|-------------|
   | Core Concepts | 8-10 |
   | Key Formulas | 5-8 |
   | Architecture | 4-6 |
   | Code Patterns | 4-6 |
   | Common Confusions | 3-5 |
   | Comparisons | 3-4 |
   | **Total** | **~30-40 flashcards** |

5. **Quality standards**:
   - Each answer should be 1-2 sentences maximum (flashcard-sized)
   - Questions should be specific, not vague
   - Include the most important 20% of knowledge (Pareto principle)
   - Formulas should use LaTeX notation
   - Code snippets should be minimal (1-3 lines max)

6. **Include a spaced repetition schedule** at the top:
   - Day 1: Review all cards
   - Day 3: Review cards you got wrong on Day 1
   - Day 7: Review all cards
   - Day 14: Review cards you got wrong
   - Day 30: Final review

## If No Parent Concept Exists

Generate flashcards based on general knowledge. Note that running `/quicklearn <concept>` first produces richer, more contextual flashcards.
