# QuickLearn

Rapidly master any technical concept through progressive complexity — from intuition to implementation.

A Claude Code plugin that generates structured learning paths with markdown notes, Mermaid diagrams, runnable Python code, quizzes, and flashcards. Designed for learners and educators (especially for IIT-level teaching).

## Features

- **7-Level Progressive Learning**: Intuition → Overview → Walkthrough → Math → Code (High-Level) → Code (From Scratch) → Teaching Notes
- **Separate Outputs**: `.md` files for study, `.py` files for code — clean and organized
- **Research-Backed Techniques**: Feynman Method, Spiral Learning, Analogy Bridges, Active Recall
- **Web-Enhanced**: Uses web search to enrich content with latest papers and resources
- **Teaching Materials**: Lecture plans, assignments, assessments designed for IIT students

## Installation

```bash
claude plugin add https://github.com/thrivikram52/QuickLearn
```

Or install locally for development:

```bash
git clone https://github.com/thrivikram52/QuickLearn.git
claude --plugin-dir /path/to/QuickLearn
```

## Commands

| Command | Description |
|---------|-------------|
| `/quicklearn <concept>` | Generate full 7-level learning path with code |
| `/quicklearn:deep-dive <sub-topic>` | Drill deeper into a specific sub-topic |
| `/quicklearn:teach <concept>` | Generate IIT-student-ready teaching materials |
| `/quicklearn:quiz <concept>` | Generate active recall quiz (21 questions, 7 levels) |
| `/quicklearn:flashcards <concept>` | Generate 30-40 flashcards for spaced repetition |

## Example Usage

```
/quicklearn auto-encoders
```

This generates:

```
quicklearn/auto-encoders/
├── 01-intuition.md          # Why auto-encoders exist (analogy-driven)
├── 02-overview.md           # Architecture diagrams and component breakdown
├── 03-walkthrough.md        # Step-by-step with concrete numbers
├── 04-math.md               # Loss functions, derivations, formal notation
├── 05-code-highlevel.md     # PyTorch implementation explained
├── 06-code-from-scratch.md  # NumPy implementation explained
├── 07-teach-notes.md        # Lecture plan, misconceptions, exam questions
└── code/
    ├── 01_autoencoder_highlevel.py
    ├── 02_autoencoder_from_scratch.py
    └── 03_variational_ae.py
```

Then deepen your understanding:

```
/quicklearn:deep-dive KL divergence in VAEs
/quicklearn:quiz auto-encoders
/quicklearn:flashcards auto-encoders
/quicklearn:teach auto-encoders
```

## Learning Methodology

QuickLearn applies proven learning techniques at every level:

| Technique | Application |
|-----------|-------------|
| **Feynman Method** | Level 1 — explain simply, find gaps, add complexity |
| **Spiral Learning** | All levels — revisit concepts at increasing depth |
| **Analogy Bridges** | Levels 1,3 — connect new ideas to known concepts |
| **Visual Thinking** | All levels — Mermaid diagrams throughout |
| **Active Recall** | Every level ends with checkpoint questions |
| **Concrete Before Abstract** | Levels 3,5,6 — examples before generalization |

## Progressive Complexity

The philosophy: **breadth first, then depth**.

1. **Use existing tools first** — Level 5 builds with PyTorch/sklearn
2. **Then build from scratch** — Level 6 rebuilds with only NumPy
3. **Then teach others** — Level 7 synthesizes into teaching materials

## Requirements

- Claude Code CLI
- Python 3.8+ (for running generated code)
- Common ML libraries: `pip install torch numpy matplotlib scikit-learn`

## Author

**Thrivikram** — [GitHub](https://github.com/thrivikram52)

## License

MIT
