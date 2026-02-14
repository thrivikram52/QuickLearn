---
name: learning-methodology
description: This skill should be used when the user asks to "learn a concept", "understand a topic", "explain a technical concept", "teach me about", "quicklearn", "master a concept", or "break down a concept". Also triggers when preparing teaching materials for IIT students or creating progressive educational content.
version: 0.1.0
---

# QuickLearn Learning Methodology

Use this framework to rapidly master any technical concept through progressive complexity. Designed for learners and educators who need deep understanding in short timeframes.

## Core Philosophy

**Breadth first, then depth.** Map the full landscape of a concept before drilling into any single area. This prevents the common trap of getting lost in details before understanding the big picture.

**Progressive complexity through 7 levels.** Every concept is broken down into levels that build on each other, from pure intuition to teaching-ready mastery.

## The 7-Level Progressive Framework

### Level 1: Intuition
Build gut-level understanding through analogy and metaphor. Answer: "Why does this exist? What problem does it solve?" Connect to concepts the learner already knows. Use real-world analogies, not technical jargon.

### Level 2: Overview
Map the architecture and components. Show where this concept fits in the broader landscape. Identify the key building blocks and how they relate. Use Mermaid diagrams for visual architecture.

### Level 3: Walkthrough
Step-by-step trace through a concrete example. Show data/information flowing through each stage. Use Mermaid sequence and flow diagrams. Annotate each step with what happens and why.

### Level 4: Mathematics
Present formal notation, loss functions, derivations, and theorems. Start from the simplest mathematical statement and build up. Show how math connects to the intuition from Level 1. Include step-by-step derivations, not just final formulas. Skip this level for concepts without a mathematical component (e.g., design patterns).

### Level 5: Code (High-Level)
Implement using existing frameworks and libraries (PyTorch, sklearn, NumPy). Focus on the architecture and flow, not low-level details. Include inline comments explaining what each block does. Generate as separate `.py` script files.

### Level 6: Code (From Scratch)
Reimplement core components without framework abstractions. Build from NumPy or pure Python. Show what the frameworks hide. This cements understanding of the mechanics. Generate as separate `.py` script files.

### Level 7: Teach Mode
Generate teaching-ready materials for IIT students. Include: concept progression, common misconceptions, exam-worthy questions, whiteboard-friendly explanations, and discussion prompts.

## Output Structure

Generate all files in `./quicklearn/<concept-name>/`:

```
quicklearn/<concept-name>/
├── 01-intuition.md
├── 02-overview.md
├── 03-walkthrough.md
├── 04-math.md
├── 05-code-highlevel.md
├── 06-code-from-scratch.md
├── 07-teach-notes.md
└── code/
    ├── 01_<concept>_highlevel.py
    ├── 02_<concept>_from_scratch.py
    └── (additional scripts as needed)
```

## Learning Techniques to Apply

Apply these techniques throughout all levels:

1. **Feynman Method** — Explain simply first, identify gaps, then add complexity
2. **Spiral Learning** — Revisit the same concept at increasing depth across levels
3. **Analogy Bridges** — Connect every new idea to something already known
4. **Visual Thinking** — Mermaid diagrams at every level (flow, sequence, architecture)
5. **Active Recall** — End each level with 2-3 checkpoint questions
6. **Concrete Before Abstract** — Always show a specific example before generalizing
7. **Chunking and Sequencing** — Break complex concepts into digestible, dependency-ordered chunks
8. **Interleaving** — Mix related concepts to strengthen distinctions and build connected knowledge

For detailed descriptions of each technique, consult `references/learning-techniques.md`.

## Partial Execution

If the user requests specific levels only, generate just those levels. Always include Level 1 (Intuition) as a preamble unless the user explicitly skips it. Adjust the output directory structure accordingly. Not all concepts require all 7 levels — skip levels that do not apply (e.g., skip Level 4 for non-mathematical concepts).

## Markdown File Guidelines

Each `.md` file follows a consistent structure:

```markdown
# <Concept Name> — Level N: <Level Title>

> **One-line summary** of what this level covers

## Prerequisites
What to know before reading this level.

## Content
(Level-specific content with Mermaid diagrams where appropriate)

## Key Takeaways
- Bullet-point summary of this level

## Checkpoint Questions
1. Question to verify understanding
2. Question to verify understanding
```

For detailed templates for each level, consult `references/output-templates.md`.

## Code File Guidelines

Each `.py` file follows a consistent structure:

- Module docstring explaining what this script demonstrates
- Clearly separated sections with comment headers
- Inline comments explaining the "why", not just the "what"
- A `main()` function with a runnable example
- Print statements showing intermediate results for learning
- Type hints for clarity

For detailed code guidelines, consult `references/code-guidelines.md`.

## Web Search Integration

If web search is available, use it to:
- Find the latest papers and resources on the concept
- Discover real-world applications and case studies
- Verify mathematical formulations
- Find the best analogies used by educators
- Include source links in a "Further Reading" section of each `.md` file

## Additional Resources

### Reference Files

For detailed guidance, consult:
- **`references/learning-techniques.md`** — Detailed breakdown of each learning technique with examples
- **`references/output-templates.md`** — Full templates for each of the 7 levels' markdown output
- **`references/code-guidelines.md`** — Detailed guidelines for generating progressive Python code
