---
name: quicklearn
description: Rapidly master any technical concept through 7 progressive levels - from intuition to implementation
argument-hint: "<concept> e.g., auto-encoders, transformers, LSTM, gradient descent"
allowed-tools:
  - Read
  - Write
  - Bash
  - Glob
  - Grep
  - WebSearch
  - WebFetch
  - Task
---

# QuickLearn — Full Learning Path Generator

Generate a complete 7-level learning path for the given concept. This is the main entry point for the QuickLearn plugin.

## Process

1. **Create output directory**: `./quicklearn/<concept-name>/` and `./quicklearn/<concept-name>/code/`

2. **Research the concept** using WebSearch:
   - Search for the latest papers, tutorials, and explanations
   - Find the best analogies used by educators
   - Identify common misconceptions
   - Find real-world applications

3. **Generate all 7 levels as separate `.md` files**, following the templates and methodology from the `learning-methodology` skill:

   - `01-intuition.md` — Feynman-style explanation, real-world analogy, why it exists
   - `02-overview.md` — Architecture diagram (Mermaid), components, landscape positioning
   - `03-walkthrough.md` — Step-by-step trace with concrete numbers, sequence diagrams
   - `04-math.md` — Formal notation, derivations, loss functions, connecting math to intuition
   - `05-code-highlevel.md` — Explanation of the PyTorch implementation
   - `06-code-from-scratch.md` — Explanation of the NumPy-only implementation
   - `07-teach-notes.md` — IIT-student-ready teaching materials: lecture plan, misconceptions, exam questions

4. **Generate code files** as separate runnable Python scripts:
   - `code/01_<concept>_highlevel.py` — Full implementation using PyTorch/sklearn
   - `code/02_<concept>_from_scratch.py` — Implementation using only NumPy
   - Additional scripts for variations if relevant (e.g., `code/03_variational_ae.py`)

5. **Use the concept-explainer agent** (via Task tool) for structuring the knowledge across all levels.

6. **Use the code-scaffolder agent** (via Task tool) for generating both code files.

## Output Quality Standards

- Every `.md` file includes Mermaid diagrams where appropriate
- Every `.md` file ends with Key Takeaways and Checkpoint Questions
- Code files are runnable with `python <filename>` after installing dependencies
- Mathematical notation uses LaTeX in markdown (`$...$` and `$$...$$`)
- Include a "Further Reading" section with web links in relevant files
- Use breadth-first then depth approach within each level

## After Generation

Print a summary showing:
- All files created with brief descriptions
- Total word count across all `.md` files
- How to run the code files (pip install commands)
- Suggested reading order (which is just L1 through L7)
